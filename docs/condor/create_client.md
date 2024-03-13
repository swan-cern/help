# Create the Dask client

Once the Dask HTCondor cluster has been created, one or more clients can connect to it to request the execution of tasks. Such clients can be created from a Python notebook or from a Python process running in the SWAN terminal. In the case of notebooks, the Dask JupyterLab extension provides a convenient drag & drop feature to add the client creation code to a notebook -- just grab the desired `SwanHTCondorCluster` with your mouse and drop it into a notebook cell.

![][condor_create_client]

The Dask client can be used to directly invoke the Dask API or, alternatively, it can be provided to an analysis framework that can leverage Dask, e.g. ROOT (RDataFrame) or coffea. In the latter case, the user produces one or more notebooks with RDataFrame / coffea analyses where a Dask client is used to generate their computations. Please refer to the [RDataFrame](https://root.cern/doc/master/classROOT_1_1RDataFrame.html#distrdf) and [coffea](https://coffeateam.github.io/coffea/) documentation to know how to provide those frameworks with a Dask client.