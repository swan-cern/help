# Resuming work after a pause

The previous steps in this documentation summarise how a user can run a distributed analysis interactively. In addition, a semi-interactive use case is also supported, meaning that the user can pause their use of SWAN for a few hours. Such a pause can be done after launching a distributed computation, perhaps even closing the browser after that. When the user comes back (i.e. connects to their SWAN session again with the browser), the SWAN interface reconnects to the Dask monitoring dashboard, so the user can see an updated status of the execution.

Note, however, that if the analysis is being executed from a notebook, the notebook interface will not reconnect to the underlying running (client) process; in other words, any output produced by that process since the browser was closed will not be fed into the corresponding cell output, although running another cell will reconnect the interface to the process. This is a limitation of the Jupyter interface itself and it is part of our future work to find a solution for it.