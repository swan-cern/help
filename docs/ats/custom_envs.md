# Custom software environments

In the ATS SWAN prototype, the software available in a user session can come from one of two sources:

1. [LCG release](https://lcginfo.cern.ch): a software stack maintained by the EP department at CERN, containing hundreds of packages distributed via [CVMFS](https://cernvm.cern.ch/fs/).
2. [Custom software environment (CSE)](https://docs.python.org/3/library/venv.html): a virtual environment defined by the user, containing a specific set of Python packages.

While (1) is the traditional way of providing software in SWAN, (2) is a new feature implemented in the ATS SWAN prototype. The next subsections describe how to create and use CSEs.

## Creating an environment

A CSE is created by specifying the following parameters in the SWAN form:

1. A **Git repository URL**, which must contain the package requirements for the environment. This repository may also contain notebooks or other files intended for use within the environment. Note that multiple users can base their CSEs on the same Git repository and potentially contribute new content.
2. An **Acc-Py release**,  which serves as the base environment. The user-specified packages are installed on top of this base layer.

## Specifying requirements

Package requirements for a CSE must be defined using requirement files placed at the root of the Git repository. Two types of requirements file are supported:

1. `requirements.in`: a high-level specification listing only the direct dependencies of the user's code. It follows the [pip requirements file format](https://pip.pypa.io/en/stable/reference/requirements-file-format/#requirements-file-format). Example:

```txt
matplotlib
ipympl
widgetsnbextension
```

2. `requirements.txt`: a fully resolved list of all dependencies and their versions. After creating a CSE from a `requirements.in` file, the user can generate a `requirements.txt` from within the environment using `pip freeze --local > requirements.txt`. Example:

```txt
contourpy==1.3.1
cycler==0.12.1
fonttools==4.57.0
ipympl==0.9.7
ipywidgets==8.1.6
jupyterlab_widgets==3.0.14
kiwisolver==1.4.8
matplotlib==3.10.1
pillow==11.2.1
pyparsing==3.2.3
widgetsnbextension==4.0.14
```

!!! note
    If both `requirements.in` and `requirements.txt` are present, the latter is used. Using `requirements.txt` usually speeds up environment creation.

## Managing repositories

During session startup, the selected Git repository is used to build the CSE. On first use, SWAN clones the repository into the user's CERNBox directory under:

```bash
$HOME/SWAN_projects/name_of_the_repository
```

SWAN then uses the repository's requirements to construct the environment. Once ready, the user is directed to the [JupyterLab](https://jupyter.org/) interface, where notebooks and terminals have been configured to use the packages of the environment.

SWAN includes the [JupyterLab Git extension](https://github.com/jupyterlab/jupyterlab-git), enabling users to manage the repository through the web interface — pulling updates, committing, and pushing changes — without needing to use the command line.

!!! note
    After a repository is cloned into the user's CERNBox space, it is the user's responsibility to keep it synchronized with upstream changes if desired. Re-selecting the same repository will reuse the existing clone without automatically pulling updates.

## Private / internal repositories

In addition to public Git repositories, CSEs can also be created from private or internal ones. To do this, users must first configure Git access credentials within their SWAN session so that the `git clone` command can authenticate successfully. Here we describe two alternatives that can be applied to repositories hosted on `gitlab.cern.ch`:

1. Personal access tokens: create a token via GitLab's web interface (instructions [here](https://docs.gitlab.com/user/profile/personal_access_tokens/), then configure Git in the SWAN terminal to use such token:

```bash
echo "https://$USER:${TOKEN_VALUE_HERE}$@gitlab.cern.ch" >> $HOME/.git-credentials
git config --global credential.helper store
```

2. SSH keys: configure Git to use SSH for authentication. See [these instructions](https://docs.gitlab.com/user/ssh/) for details.

Once configured, Git credentials will be reused automatically in future sessions.

## NXCALS integration

The ATS SWAN prototype supports NXCALS users submitting computations to the NXCALS Hadoop cluster from within a CSE. To enable this:

1. Include the `nxcals` Python package in the requirements file of the CSE.
2. Select the NXCALS cluster under "External Computing Resources" → "Spark clusters", in the SWAN form.

In such sessions, SWAN automatically installs the `SparkConnector` and `SparkMonitor` JupyterLab extensions, thus allowing users to connect to the NXCALS cluster and monitor Spark jobs directly from their notebook.