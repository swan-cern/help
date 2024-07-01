# AlmaLinux 9 and JupyterLab

SWAN offers an AlmaLinux9 user image, which is now selected as default when users start their sessions. This is in the context of the migration away from CentOS7, which reached its [end of life](https://cern.service-now.com/service-portal?id=outage&n=OTG0145248) in June 2024.

The Alma9 image allows users to select a new interface, [JupyterLab](https://jupyterlab.readthedocs.io/en/latest/) as an alternative to the classic one. Such interface integrates notebooks, terminals and a file browser in the same workspace, and its modular design allows for extensions to be deployed to enrich functionality. Users are expected to progressively move to JupyterLab instead of the classic SWAN UI, especially as the former becomes more feature-complete, although both interfaces will be available for some time (at least during 2024).

To start a session with Alma9, please select the LCG 105 release (or newer) in the web form, and ensure "AlmaLinux 9" is selected as the Platform. Furthermore,
if you also wish to use the new JupyterLab interface, please tick the field at the top of the form that says "Try the new JupyterLab interface (experimental)".

This image integrates with all of the SWAN existing features, including access to GPUs, Spark clusters and HTCondor.

## New features

- The JupyterLab UI gives more flexibility regarding the location of notebooks. While the classic UI enforces the creation of Projects, which contain notebooks and other files, JupyterLab users can work with any folder in their CERNBox.
- In JupyterLab-Alma9, interactive analysis on HTCondor resources is supported via [Dask](https://www.dask.org/) and its [lab extension](https://github.com/dask/dask-labextension). More documentation on this topic is coming soon!

## Current limitations

- The CERNBox sharing functionality available in the classic SWAN UI is not yet available in JupyterLab. The SWAN team is working on providing a JupyterLab extension that allows to share notebooks / folders from SWAN via CERNBox.