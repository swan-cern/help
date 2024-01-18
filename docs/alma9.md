# AlmaLinux 9 and JupyterLab

SWAN now offers an experimental AlmaLinux9 user image, which users can select when starting their sessions. This is in the context of the migration away from CentOS7, which will reach its [end of life](https://cern.service-now.com/service-portal?id=outage&n=OTG0145248) in June 2024.

The new Alma9 image shows by default the latest Jupyter interface, [JupyterLab](https://jupyterlab.readthedocs.io/en/latest/). Such interface integrates notebooks, terminals and a file browser in the same workspace, and its modular design allows for extensions to be deployed to enrich functionality. Users are expected to progressively move to JupyterLab instead of the classic SWAN UI, especially as the former becomes more feature-complete, although both interfaces will be available for some time (at least during 2024).

To start a session with Alma9 and JupyterLab, please select the LCG 105 release (or newer) in the web form, and choose "AlmaLinux 9" as Platform.

## New features

- The JupyterLab UI gives more flexibility regarding the location of notebooks. While the classic UI enforces the creation of Projects, which contain notebooks and other files, JupyterLab users can work with any folder in their CERNBox.
- In JupyterLab-Alma9, interactive analysis on HTCondor resources is supported via [Dask](https://www.dask.org/) and its [lab extension](https://github.com/dask/dask-labextension). More documentation on this topic is coming soon!

## Current limitations

- The Spark clusters are not accessible from the SWAN Alma9 image at the moment. During 2024, the SWAN and the Hadoop services at CERN will coordinate to migrate to Alma9, so that SWAN Alma9 clients can submit Spark jobs to the migrated Hadoop/Spark clusters.
- The CERNBox sharing functionality available in the classic SWAN UI with CentOS7 is not yet available in Alma9 with JupyterLab. The SWAN team is working on providing a JupyterLab extension that allows to share notebooks / folders from SWAN via CERNBox.

## Using the classic UI

JupyterLab is launched by default when selecting Alma9 as platform, but the classic UI is also available in an Alma9 session. To select it, go to the menu `Help->Launch the Classic SWAN UI` or, from a notebook, click on the button `Classic UI`.