# Manage a Dask cluster

Once the SWAN session starts, the user is shown the JupyterLab interface, which includes the [Dask JupyterLab extension](https://github.com/dask/dask-labextension). The extension allows to graphically create a `SwanHTCondorCluster`, which represents the set of HTCondor resources that will run the analysis tasks.

![][condor_create_cluster]

Once created, the cluster can be scaled up to the number of desired worker cores. This triggers the submission of HTCondor jobs, which will execute the Dask worker processes. Before scaling a cluster, please run `kinit` from the SWAN terminal in order to create the necessary credentials for job submission. It is expected that this requirement will be removed in the future with the introduction of automatically generated tokens.

The jobs belonging to a given cluster and their status can be inspected with the `condor_q` command from the SWAN terminal. When the jobs start running, the corresponding Dask worker processes contact the Dask scheduler (which runs on the SWAN side) to announce that they are available to run tasks.

![][condor_scale_cluster]

Multiple clusters can be created. At the moment, a maximum of 5 clusters can exist at the same time.

When they are no longer used, clusters should be shut down via the Dask JupyterLab extension. This terminates the corresponding HTCondor jobs that run the Dask workers. In the current setup, the maximum lifetime of a Dask worker job is 24 hours; this means that, if a cluster is not shut down, its jobs will automatically finish 24 hours after being created.

## Configuring the Dask cluster

Dask allows to configure HTCondor clusters with parameters that are applied to the workers. From SWAN, this can be achieved by providing a Dask configuration file at the location `$HOME/.config/dask/jobqueue-cern.yaml`. An example of such file can be found below:

```yaml
jobqueue:
  cern:
    # Resource requests per job (i.e. per worker)
    cores: 4
    memory: "12 GiB"

    # Directory where Dask worker logs are stored when the cluster is shut down
    log-directory: "/eos/user/s/someuser/dask_logs"
```

Note that, after the Dask configuration file has been created / modified, the SWAN session needs to be restarted for Dask to pick the new configuration.