# Known issues

* If you're having troubles opening notebooks, please make sure that, from a SWAN terminal, you remove this temporary directory in your CERNBox: `~/.local/share/jupyter`. The latest deployment of SWAN implements an optimisation which makes it redundant.
* When you open the Sharing Panel on a already shared project, you will notice that you no longer see the names of the people you shared with, only the usernames.
* If you open a notebook inside an EOS Project space, once you click the save button you will get a warning stating that `Checkpoint failed`. **Your notebook is saved**, but you won't have access to previous versions of it. This is due to a limitation of old EOS Project and should disapear once your project gets migrated to the new infrastructure.