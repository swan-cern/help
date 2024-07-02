# Install packages in CERNBox

LCG releases on CVMFS incorporate new packages quite frequently, so if you think there is a missing package that can be 
potentially useful for a significant number of users, please open a ticket to the [EP-SFT librarians](https://sft.its.cern.ch/jira/projects/SPI)
and ask them to install the package in the LCG releases.

On the other hand, you can install packages on your CERNBox and, if necessary, configure your environment to pick them 
up in SWAN. 

## Python

A typical case is the installation of Python packages, which requires to run pip from a SWAN terminal:

   `pip install --user package_name`

If this fails because you are trying to install an updated version of a package that already exists in CVMFS, you will need to add the `--upgrade` flag.

After the desired Python packages have been installed on CERNBox, they need to be added to the PYTHONPATH when starting a SWAN session. This can be easily 
achieved by selecting the option "Use Python packages installed on CERNBox" under the "Software stack" section of the SWAN web form.

![][user_python_packages]

As a result of performing the aforementioned steps, the package will be installed on your CERNBox and it will be picked by 
any notebook you open after that. Since the package is on your CERNBox, it will be also available in any new session 
you start in SWAN.

## R

You can also install R packages on your CERNBox. For that, from a SWAN terminal, create a subdirectory on your CERNBox home directory using the next command:
`mkdir -p ~/Rpackages`

Next, still from the SWAN terminal, open the R interpreter and run the next command to install your package (replace "package_here" by the name of your package):
`install.packages('package_here', repos='http://cran.rstudio.com/',lib = '~/Rpackages')`

Finally, from your R notebook, you will be able to use your package after running the following two commands in a cell:
`.libPaths(c(.libPaths(), "~/Rpackages"))`
`require(installed_pkg,lib='~/Rpackages',character.only = TRUE)`

[user_python_packages]: ../images/user_python_packages.png "User installed Python packages"