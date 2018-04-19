# Install packages in CERNBox

LCG releases on CVMFS incorporate new packages quite frequently, so if you think there is a missing package that can be 
potentially useful for a significant number of users, please [let the SWAN team know](mailto:swan-talk@cern.ch) and 
[contact the librarians directly](https://sft.its.cern.ch/jira/projects/SPI).

On the other hand, you can install packages on your CERNBox and, if necessary, configure your environment to pick them 
up in SWAN. A typical case is the installation of Python packages, which requires to run pip from a SWAN terminal:

   `pip install --user package_name`

If this fails because you are trying to install an updated version of a package that already exists in CVMFS, you will need to add the `--upgrade` flag.

Then, it would be necessary to add the local installation path to `PYTHONPATH`, by creating a bash startup script that configures that variable (don't forget to call this startup script in the session configuration menu):

    export PYTHONPATH=$CERNBOX_HOME/.local/lib/python3.5/site-packages:$PYTHONPATH

As a result of performing the aforementioned steps, the package will be installed on your CERNBox and it will be picked by 
any notebook you open after that. Since the package is on your CERNBox, it will be also available in any new session 
you start in SWAN.
