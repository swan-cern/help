# Running Spark on CERN Clusters

SWAN also allows to submit computations to Spark Clusters located at CERN. If you are interested in accessing these clusters, please let us know at [ai-hadoop-admins@cern.ch](mailto:ai-hadoop-admins@cern.ch), as you need to be added to a specific e-group.

### Selection of a Spark Cluster

In order to access a particular Spark cluster from SWAN, the first thing you need to do is select that cluster from the "Spark cluster" option of the form, when starting your SWAN session.

Recommended usage of Spark Clusters:

* analytix - General Purpose Cluster
* nxcals - Dedicated for BEAMS NXCals Project
* cloud containers - analysis accessing data from external storage systems e.g EOS, S3, Kafka, HDFS (analytix)

![][spark_clusters]

### Spark Connector

Once your session is started, you will be able to access the Spark cluster you selected from a Python notebook. You are allowed to connect from 2 different notebooks. If you need to connect from a different notebook, please shutdown one of the opened ones. You can also restart the kernel of your current notebook if you want to kill the current connection and re-connect from the same notebook.

You will notice that, if you selected a cluster before starting your session, a new Spark button will appear in the toolbar:

![][spark_toolbar]

Once the kernel is ready, you will be able to click on it. When you do, a panel will appear on the right, showing the Spark configuration menu. Here you can add extra Spark configuration options, such as number of cores or memory to use in the Spark executors.

![][spark_options]

When specifying the value of an option, you can use environment variables with the following syntax: {VAR_NAME}.

You can inline-edit an option already added, by clicking in the option name or value. To remove it, click in the X that appears when hovering over it. If it finds any problem with your configuration, it will display a warning. Hover over the highlighted option to read the reason.

After clicking on "Connect", the connection will be established. This may take some time, but you can follow the logs to see what is happening. Once the connection process has finished, there will be two new variables available in your notebook for you to use:

*   **sc** = [SparkContext](https://spark.apache.org/docs/latest/api/python/pyspark.html#pyspark.SparkContext)
*   **spark** = [SparkSession](https://spark.apache.org/docs/latest/api/python/pyspark.sql.html#pyspark.sql.SparkSession)

You are now ready to start submitting your Spark jobs!

SWAN also provides automatic saving of Spark configuration options: any option added in the configuration menu will be saved in the notebook metadata. This means that every time you open that notebook and use the Spark connector, the configurations will load automatically, so that you do not have to type them again! If you modify them, the changes will be saved.

Please note that **only 2 Spark connections from a user session are supported**. If you open 2 notebooks and connect to a Spark cluster as described above, you cannot open a third notebook and connect again. You can only open a new connection with the cluster if you restart your spark session (via Spark button and click on `Restart Spark Session`).

### HDFS Connector

Once your session is started, you will be able to access the Hadoop HDFS cluster you selected from a Python notebook. A new Hadoop button (elephant) will appear in the Jupyter Notebook toolbar. 

This allows you to browse the HDFS directory structure

### Example Spark Notebooks Gallery

Check out [Getting Started Spark Notebooks](https://swan.web.cern.ch/content/apache-spark) 

[spark_clusters]: ../images/spark_clusters.png "Choose Spark Cluster"
[spark_toolbar]: ../images/spark_toolbar.png "Spark Connector button"
[spark_auth]: ../images/spark_auth.png "Spark Connector authentication"
[spark_options]: ../images/spark_options.png "Spark Connector options"
