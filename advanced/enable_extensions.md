# Install and enable notebook extensions

SWAN provides a set of common notebook extensions, whose description can be found at:
[https://github.com/ipython-contrib/jupyter_contrib_nbextensions](https://github.com/ipython-contrib/jupyter_contrib_nbextensions). 
You can also find the Nbextensions configuration panel in the top right menu (under "∙∙∙").

![][nbextensions]

In addition, ipywidgets can also be used: [https://github.com/ipython/ipywidgets](https://github.com/ipython/ipywidgets).

Most notebook extensions enrich the notebook interface with new JavaScript features and, therefore, they need to be 
activated before opening a notebook. In order to activate an extension, you can go to the NBExtensions configuration panel 
open a SWAN Terminal and execute the 
following command: `jupyter nbextension enable extension_name`
For example, in the case of ipywidgets you could do:

![][terminal_ext]

Any notebook you open after activating an extension will show that particular extension. Note that you could also do the 
activation inside a notebook cell (Python or C++), like in the following example for the spellchecker extension; 
in this case, you will need to refresh your notebook page after the activation to see the extension.

![][spellchecker_nb]

If you want a subset of extensions to be activated every time you open a new session in SWAN, you can include the 
activation commands in your customization script.

[nbextensions]: ../images/nbextensions.png "Nbextensions configuration panel"
[terminal_ext]: ../images/terminal_ext.png "Extension activation on terminal"
[spellchecker_nb]: ../images/spellchecker_nb.png "Extension activation inside a notebook"