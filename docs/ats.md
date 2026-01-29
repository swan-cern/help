# Introduction

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

In ATS SWAN, the software available in a user session can come from one of two sources:

1. [LCG release](https://lcginfo.cern.ch): a software stack maintained by the EP department at CERN, containing hundreds of packages distributed via [CVMFS](https://cernvm.cern.ch/fs/).
2. [Custom software environment (CSE)](https://docs.python.org/3/library/venv.html): a virtual environment defined by the user, containing a specific set of Python packages.

While (1) is the traditional way of providing software in SWAN, (2) is a new feature implemented in ATS SWAN. The next subsections describe how to create and use CSEs.

## Creating an environment

A CSE is created by specifying the following parameters in the SWAN form:

1. A **Git repository URL**, which must contain the package requirements for the environment. This repository may also contain notebooks or other files intended for use within the environment. Note that multiple users can base their CSEs on the same Git repository and potentially contribute new content.
2. An **Acc-Py release**,  which serves as the base environment. The user-specified packages are installed on top of this base layer.

## NXCALS integration

ATS SWAN supports NXCALS users submitting computations to the NXCALS Hadoop cluster from within a CSE. To enable this:

1. Include the `nxcals` Python package in the requirements file of the CSE.
2. Select the NXCALS cluster under "External Computing Resources" → "Spark clusters", in the SWAN form.

In such sessions, SWAN automatically installs the `SparkConnector` and `SparkMonitor` JupyterLab extensions, thus allowing users to connect to the NXCALS cluster and monitor Spark jobs directly from their notebook.