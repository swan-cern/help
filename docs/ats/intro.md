# Introduction

As part of a joint project — called "SWAN on the TN" — between the ATS and IT departments at CERN, a specialized SWAN instance has been deployed to meet the specific needs of the ATS sector. This ATS SWAN instance is available at:

<https://ats.swan.cern.ch>

The access to this instance is restricted to members of the `acc-all` e-group.

## Main features

The main user-facing features introduced by ATS SWAN are:

- [Custom sofware environments](custom_envs.md): create software environments based on an Acc-Py release when launching a SWAN session.
- [URLs with arguments](url_args.md): generate URLs that pre-configure user sessions (e.g., software stack, memory allocation, etc.).
- Version control of notebooks: use the [jupyterlab-git](https://github.com/jupyterlab/jupyterlab-git) extension to manage Git repositories with notebooks from JupyterLab.

## Network access

ATS SWAN runs on CERN's General Purpose Network (GPN), but it is **exposed to CERN's Technical Network (TN)**. Such exposure is bidirectional, in other words:

1. User sessions can query devices located in the TN.
2. Users located in the TN can connect to ATS SWAN and create sessions.

Furthermore, user sessions in ATS SWAN **do not have Internet connectivity**.