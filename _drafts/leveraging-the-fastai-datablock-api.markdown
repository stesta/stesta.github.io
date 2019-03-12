---
layout: post
title: Leveraging the fast.ai DataBlock API 
date: 2019-03-11
---

The fast.ai apis make great attempt at providing loaders for many common scenarios. In the vision api, for instance, it is trivial to create an `ImageDataBunch` with labels from folders, or a csv file, pandas dataframe, regex, etc. There is even a convenient method to load in labels via a lambda function if you truly need a more complex solution. The caveat is that it is expected the actual image files reside on disk. What happens when that is not the case?

Take a real example from a Kaggle competition, the Digit Recognizer competition is an ongoing beginner competition. The goal is simple - train a model to recognize handwritten digits based on the MNIST dataset. Fast.ai already provides easy access to the MNIST dataset by default. It would be easy enough to pull in the data that way, but for the purposes of the competition I wanted to use the data in the format provided. 

The images themselves reside within a csv file. In the training set the first column of each row represents the correct category/label for the image and the next 784 columns represent pixel value intensities for a single channel 28x28 gray scale image of the handwritten digit. Most of the fast.ai solutions (if not all of them) that I've looked at take the approach of first converting that data to images on disk and then susequently loading them in via one of the already provided methods. While that is certainly a viable approach it didn't sit right with me that the already available data would be essentially duplicated. A better solution instead would be to load in the csv pixel values directly into an `ImageDataBunch` 

## Enter the fast.ai DataBlock API 

The DataBlock API provides the ability to customize the base `ImageList` for just this type of scenario. In this case, the process itself is relatively straight forward: 

1) Create a new class that inherits from the `ImageList`
2) Define the class method that will load in the custom data 
3) Implement the `open` method to indicate how the custom format can be converted to an `Image`

Here's the implementation:  
Credit goes to [Erik Man][1] for pointing out the floating point conversion for the pixel values which allowed the gray scale images to render properly when displaying items from the batch.  

```python
class CustomImageList(ImageList):
    def open(self, fn):
        img = fn.reshape(28,28)
        img = np.stack((img,)*3, axis=-1) # convert to 3 channels
        return Image(pil2tensor(img, dtype=np.float32))

    @classmethod
    def from_csv_custom(cls, path:PathOrStr, csv_name:str, imgIdx:int=1, header:str='infer', **kwargs)->'ItemList':
        df = pd.read_csv(Path(path)/csv_name, header=header)
        res = super().from_df(df, path=path, cols=0, **kwargs)
        # convert pixels to an ndarray
        res.items = df.iloc[:,imgIdx:].apply(lambda x: x.values / 255.0, axis=1).values
        return res
```

Basic Usage:

```python 
tfms = get_transforms(do_flip=False)
data = (CustomImageItemList.from_csv_custom(path='./data', csv_name='train.csv')
                           .random_split_by_pct(.2)
                           .label_from_df(cols='label')
                           .transform(tfms)
                           .databunch(bs=64, num_workers=0)
                           .normalize(imagenet_stats))
```

I have also made working examples available both as a [Kaggle Kernel][2] that you can fork and also via [GitHub][3]. 

[1]: https://www.kaggle.com/goodbyte
[2]: https://www.kaggle.com/steventesta/digit-recognizer-fast-ai-custom-databunch
[3]: https://github.com/stesta/kaggle/blob/master/digit-recognizer/digit-recognizer.ipynb
