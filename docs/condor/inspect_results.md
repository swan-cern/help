# Inspect the results of the analysis

when the distributed execution finishes, the aggregated final results (e.g. histograms) are transferred back to the Dask client. This means that the user can display those results in the notebook and inspect them. After inspection, the user might decide to change some parameters of their analysis and start a new distributed computation, thus going back to the execution and monitoring step.

![][condor_inspect_results]