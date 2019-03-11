If you're doing anything related to machine learning then it's pretty much a given that you're using a [jupyter notebook](). Here are few extensions that are sure to help make your life easier.  

**tl;dr**
```bash
pip install jupyter_contrib_nbextensions && jupyter contrib 
nbextension install 
```

### jupyter_contrib_nbextensions

As they state explicitly on their site, the `jupyter_contrib_nbextensions` package contains a collection of community-contributed unofficial extensions that add functionality to the Jupyter notebook. All of the extensions mentioned in this post are available via this package. 

```bash
pip install jupyter_contrib_nbextensions
jupyter contrib nbextension install --user
```

[Full Installation Documentation](https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/install.html)

### jupyter_nbextensions_configurator

The `jupyter_nbextensions_configurator` is a really convenient way to install and enable and extensions that are included as part of the `jupyter_contrib_nbextensions` package. I highly recommend installing the configurator. It also makes for a convenient way to browse new extensions that may be of interest.

```bash
pip install jupyter_nbextensions_configurator
jupyter nbextensions_configurator enable --user
```

[Full Installation Documentation](https://github.com/Jupyter-contrib/jupyter_nbextensions_configurator)

Extensions for Machine Learning
-------------------------------

(in no particular order of importance) 

### Codefolding 

Readability is inversely proportional to the the length of code. Code folding allows the developer to collapse blocks of code to keep the important semantics in context while maintaining a readable code base.   

![](/assets/images/blog/code-folding.gif)

### Collapsible Headings

As complexity increases so will your notebook. Even if you're diligent about breaking up code into small digestible cells such that it diminishes the need for codefolding, headings via markdown cells are available to better organize and describe code.  

![](/assets/images/blog/collapsible-headings.gif)

### Freeze

One of the reasons notebooks have become so popular in the realm of data science is their experimental and iterative nature. Notebooks are not always execute in a linear fashion. Freezing a cell provides a mechanism to prevent a cell from executing when it is run. 

### Notify

Notify is a great plugin to let you know when those long running processes have finished. Think about when training a model. Often it can take a decent bit of time for your GPU to chew through a model fit. I don't know about you, but I take this opportunity to get *other work done* (read: twitter). These notifications are a handy way to let me know a process has finished. 

### Scratchpad

Think of the Scratchpad plugin like any other cell within your notebook (because it is just that). Scratchpad, however, makes it convenient to run quick little bits of code in a way that doesn't pollute the flow of the  notebook. 

### Zen Mode

This one is just kind of for fun. Zen mode provides a distraction free interface that adds some nice styling and a pleasant background while you're working. You can even choose your own backgrounds if you like. 


**What extensions did I miss? Let me know in the comments below!**