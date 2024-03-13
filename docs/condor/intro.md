# Introduction

SWAN can be used as an entry point to execute jobs on the HTCondor pool at CERN. This can be done from the command line in the SWAN terminal, i.e. by means of batch jobs that are submitted and monitored via the HTCondor CLI (more information [here](https://batchdocs.web.cern.ch/local/submit.html)).

Furthermore, SWAN also allows to exploit HTCondor resources via [Dask](https://www.dask.org/), a library for parallel and distributed computing in Python. Dask has a modular design, where adaptors for different computing infrastructures can be plugged, including common job queuing systems such as HTCondor. Hence, with Dask, one can programmatically reserve HTCondor resources and spawn worker processes on them, which are in charge of running distributed tasks.

Dask also offers a [graphical extension](https://github.com/dask/dask-labextension) for [JupyterLab](https://jupyter.org/), the latest interface for web-based interactive development proposed by the Jupyter project. With the Dask JupyterLab extension, users can graphically create Dask clusters (e.g. on HTCondor) that can be used to run distributed computations, from e.g. Jupyter notebooks or Python scripts executed in a terminal.

The integration of SWAN and HTCondor via Dask is fundamental to support interactive distributed analysis for HEP: the two most popular HEP analysis frameworks, [ROOT](https://root.cern/) (RDataFrame) and [coffea](https://coffeateam.github.io/coffea/), rely on Dask to execute the analysis computation workflows that they generate on a set of distributed resources. Consequently, users can write their analysis in the framework of their choice, or even mix them, and run that analysis on HTCondor resources at CERN from SWAN.

The next subsections describe the steps to be followed in order to run a distributed analysis with SWAN and HTCondor at CERN.