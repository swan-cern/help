# ATS SWAN

As part of a joint project — called "SWAN on the TN" — between the ATS and IT departments at CERN, a specialized SWAN instance has been deployed to meet the specific needs of the ATS sector. This ATS SWAN instance is available at:

<https://ats.swan.cern.ch>

The access to this instance is restricted to members of the `acc-all` e-group.

## Main features

The main user-facing features introduced by ATS SWAN are:

- [Acc-Py environments](accpy_envs.md): create software environments based on an Acc-Py release when launching a SWAN session.
- [URLs with arguments](../session/url_args.md): generate URLs that pre-configure user sessions (e.g., software stack, memory allocation, etc.).
- Version control of notebooks: use the [jupyterlab-git](https://github.com/jupyterlab/jupyterlab-git) extension to manage Git repositories with notebooks from JupyterLab.

## Network access

ATS SWAN runs on CERN's General Purpose Network (GPN), but it is **exposed to CERN's Technical Network (TN)**. Such exposure is bidirectional, in other words:

1. User sessions can query devices located in the TN.
2. Users located in the TN can connect to ATS SWAN and create sessions.

Furthermore, user sessions in ATS SWAN **do not have Internet connectivity**.

# Acc-Py environments

In ATS SWAN, the custom software environments are available in a user session can come from three different Acc-Py builder versions (`2020.11`, `2021.12`, `2023.06`). The user-specified packages are installed on top of this base layer.

## NXCALS integration

ATS SWAN supports NXCALS users submitting computations to the NXCALS Hadoop cluster from within a CSE. To enable this:

1. Include the `nxcals` Python package in the requirements file of the CSE.
2. Select the NXCALS cluster under "External Computing Resources" → "Spark clusters", in the SWAN form.

In such sessions, SWAN automatically installs the `SparkConnector` and `SparkMonitor` JupyterLab extensions, thus allowing users to connect to the NXCALS cluster and monitor Spark jobs directly from their notebook.
