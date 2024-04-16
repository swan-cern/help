# Matplotlib

## Introduction

[Matplotlib](https://matplotlib.org/stable/) is a Python library used to create static, animated and interactive visualizations, including different types of figures and plots. It is possible to become familiar with these different types of visualizations [here](https://matplotlib.org/stable/plot_types/index.html) and learn more with their tutorials [here](https://matplotlib.org/stable/tutorials/index.html).

## Backends

The library uses different [backends](https://matplotlib.org/stable/users/explain/figure/backends.html) to create the several types of figures and plots in different ways. For instance, different backends may be used to create an interactive plot or a static figure.
These backends can be specified and changed through the use of the `%matplotlib <backend>` line magic in your SWAN notebook.

In SWAN, you can use different backends in notebooks, including:
- `%matplotlib inline` - This is the default and will render images as PNGs;
- `%matplotlib widget` - This generates an interactive ipywidget;
- `%matplotlib notebook` - This is also a supported option to have an interactive display.

For more information, please consult the [documentation of Matplotlib](https://matplotlib.org/stable/users/explain/quick_start.html#a-simple-example).
