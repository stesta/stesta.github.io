If you're doing anything related to machine learning then it's pretty much a given that you're using a [jupyter notebook]. Here are few extensions that are sure to help make your life easier.  

### jupyter_contrib_nbextensions

As they state explicitly on their site, the `jupyter_contrib_nbextensions` package contains a collection of community-contributed unofficial extensions that add functionality to the Jupyter notebook. All of the extensions mentioned in this post are avaiable via this package. 

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

### Code Folding 

### Notify

Notify is a great plugin to let you know when those long running processes have finished. Think about when training a model. Often it can take a decent bit of time for your GPU to chew through a model fit. I don't know about you, but I take this opportunity to get *other work done* (read: twitter). These notifications are a handy way to let me know a process has finished. 

### Scratchpad


### Freeze


Bonus: Hotkeys
--------------

