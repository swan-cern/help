# Select a configuration

Once you connect to https://swan.cern.ch and authenticate with your CERN username and password, you are prompted with a configuration form to customize your SWAN session.

![][config_panel]

In the configuration form you have the following options:

* **Software stack**: [LCG release](http://lcginfo.cern.ch/) that will be used to configure your environment. From your session, you will have available all the software packages included in the LCG release that you selected.
* **Platform**: GCC compiler version.
* **Environment script**: path to a script with extra environment configuration (see more below).
* **Number of cores** allocated to your session.
* **Memory** (in GB) allocated to your session.
* **Spark cluster** that you want to plug to your session.

The environment script is a **bash shell script** that you can write to define your environment variables or to perform 
other configuration actions. You can locate this script in your CERNBox and access it by using the
 `CERNBOX_HOME` environment variable, that automatically resolves to your home directory in SWAN, i.e. your CERNBox.

After selecting the values that you want, click on **`Start my Session`** to begin working with SWAN!

[config_panel]: ../images/config_panel.png "Configuration panel"
