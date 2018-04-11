# Select a configuration

SWAN provides personalized sessions for each user. A single lightweight container image is instantiated,
while CVMFS is exploited to provide all the software needed.

Before you start, you will need to provide some configuration. But default values are already given.

![][config_panel]

In the configuration menu you have the following options:
* **Software stack**: the [LCG release](http://lcginfo.cern.ch/) that defines the software packages that will be available;
* **Platform**: available for older LCG releases, it provides the options for the GCC compiler;
* **Environment script**: path to a script that will run during the configuration of the session;
* **Number of cores**;
* **Memory**;
* **Spark cluster**: the Spark cluster that will be available inside the session.

The environment script is a **bash shell script** that you can write to define your environment variables or to perform 
other configuration actions. You can locate this script in your CERNBox (or EOS), and access it by using the
 CERNBOX_HOME environment variable, that automatically resolves to your home directory in EOS.

After selecting the values you want, click "Start my Session" and SWAN will create and configure a session.
If no interaction with the Jupyter interface is made for 6h, the session will be terminated. If you had an open window, 
you will need to refresh it to login and start a session again. 

If, for any reason, you have an unsaved notebook, open swan in another window (to be able to login and start a session), 
and try again to save the notebook. This way, you won't loose your work. 


[config_panel]: ../images/config_panel.png "Configuration panel"