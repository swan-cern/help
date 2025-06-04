# Introduction

As part of a joint project — called "SWAN on the TN" — between the ATS and IT departments at CERN, a specialized SWAN instance is being developed to meet the specific needs of the ATS sector. A prototype of this ATS SWAN is already available for testing at:

<https://ats.swan.cern.ch>

The access to this prototype is restricted to members of the `TBD` e-group.

## Main features

The main user-facing features introduced by ATS SWAN are:

- [Custom sofware environments](custom_envs.md): create software environments based on an Acc-Py release when launching a SWAN session.
- [URLs with arguments](url_args.md): generate URLs that pre-configure user sessions (e.g., software stack, memory allocation, etc.).
- Version control of notebooks: use the [jupyterlab-git](https://github.com/jupyterlab/jupyterlab-git) extension to manage Git repositories with notebooks from JupyterLab.