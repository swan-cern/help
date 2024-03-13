# Execute and monitor an interactive distributed analysis

Users can execute their Dask-based RDataFrame / coffea analysis by running the cells of their notebook or by executing a Python script from the SWAN terminal. As a result, RDataFrame / coffea send tasks to the Dask scheduler, which schedules them on the Dask workers.

In order to monitor the progress of the distributed execution, the Dask JupyterLab extension provides a dashboard. Multiple tabs with different kinds of information can be opened as part of such a dashboard: task graph that represents the analysis workflow, progress bars for the different task types, task stream that shows an execution trace of the analysis tasks, CPU / memory utilisation in the workers used in the workers, etc. Instructions on how to configure the layout of the Dask dashboard can be found [here](https://github.com/dask/dask-labextension?tab=readme-ov-file#configuring-a-default-layout).

![][condor_execute_and_monitor]