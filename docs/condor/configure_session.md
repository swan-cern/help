# Configure the SWAN session

In order to benefit from the integration of SWAN and HTCondor the user needs to select in the SWAN web form, when starting their session. that they would like to use the HTCondor pool at CERN. Moreover, to use the JupyterLab interface, they need to choose AlmaLinux9 as `Platform`.

![][condor_select_pool]

Regarding the software to be used in the analysis, notably ROOT RDataFrame and coffea, users should select a `Software stack` that provides the package versions that they would like to use. The default stack is the one with the most recent versions of all packages.

[condor_select_pool]: ../images/condor_select_pool.png "Selection of HTCondor pool at CERN when starting a SWAN session"