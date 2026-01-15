# Introduction

The **Rucio JupyterLab Extension** brings scientific data management directly into your JupyterLab environment, allowing to discover, access, and analyze datasets from Rucio data lakes without leaving the notebook interface. 

## How It Works

While spawning the session, you can choose to activate the extension; associated to that, a dedicated form allows you to choose which experiment's cluster to setup, as well as a dedicated Rucio Storage Element (RSE) to be used as local storage for the files.
Please notice that the extension leverages the already existing (RSEs) provided by the experiment and present on the CERN Tier0 infrastructure.

From the JupyterLab sidebar, you can **browse Rucio datasets**, **search for specific data** using pattern matching, and **replicate data with a single click**. 
The extension automatically resolves file paths and can inject these paths directly into your notebooks as variables, streamlining your analysis workflow.

Authentication is flexible, supporting username/password credentials, X.509 certificates or proxy certificates, and OIDC tokens (still experimental), with full VO (Virtual Organization).

The next subsections describe the steps to be followed in order to enable and use the Rucio extension in SWAN.