# Install and enable notebook extensions

SWAN provides a set of common notebook extensions, whose description can be found [here](https://github.com/ipython-contrib/jupyter_contrib_nbextensions). The Nbextensions configuration panel can be accessed from the top right menu (under **`∙∙∙`**).

![][nbextensions]

In addition, [ipywidgets](https://github.com/ipython/ipywidgets) can also be used.

Most notebook extensions enrich the notebook interface with new JavaScript features and, therefore, they need to be 
activated before opening a notebook. In order to activate an extension, you can go to the Nbextensions configuration panel, 
open a SWAN terminal and execute the following command:

   `jupyter nbextension enable extension_name`

For example, in the case of ipywidgets you could do:

![][terminal_ext]

Any notebook you open after activating an extension will show that particular extension. Note that you could also do the 
activation inside a notebook cell (Python or C++), like in the following example for the spellchecker extension; 
in this case, you will need to refresh your notebook page after the activation to see the extension.

![][spellchecker_nb]

If you want a subset of extensions to be activated every time you open a new session in SWAN, you can include the 
activation commands in your user enviroment script.

[nbextensions]: ../images/nbextensions.png "Nbextensions configuration panel"
[terminal_ext]: ../images/terminal_ext.png "Extension activation on terminal"
[spellchecker_nb]: ../images/spellchecker_nb.png "Extension activation inside a notebook"


# Enable Jupyter extension not provided by SWAN.

It is also possible to install and enable a Jupyter extension which is not provided by default by SWAN. The following commands show how that can be done, from the SWAN terminal:

```shell
pip install --user extension_name
export JUPYTER_DATA_DIR=$CERNBOX_HOME/.local/share/jupyter
jupyter nbextension install --py --symlink --user extension_name
jupyter nbextension enable extension_name --user --py
```

Please note that the `--user` option is important to ensure the extension is installed on CERNBox.
  
