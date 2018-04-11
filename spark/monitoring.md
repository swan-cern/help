# Spark Monitoring

If you are running Spark jobs, either locally or on a cluster, you can now keep track of their execution right from inside the notebook. This functionality is provided by the Spark Monitor, which will show an interactive monitoring display in the notebook anytime you run a cell that triggers a Spark computation.

![][spark_monitor]

With this tool you can see in detail the jobs, including stages, and the tasks that are running. You can also see the resource allocation and access the Spark UI.

To make this work, SWAN exports to the notebook a SparkConf object in the variable _swan\_spark\_conf_. You need to use this variable as the conf source, like so:

    sc = SparkContext(conf = swan_spark_conf)
    

To add more configurations, add them to this this SparkConf object, by issuing:

    swan_spark_conf.set(option_name, option_value)
    

Keep in mind that we add a jar in spark.driver.extraClassPath option. If you need to add more paths to this option, don’t forget to concatenate, like this:

    extra_class = swan_spark_conf.get('spark.driver.extraClassPath') + ':/another_file.jar'
    swan_spark_conf.set('spark.driver.extraClassPath', extra_class)

[spark_monitor]: ../images/spark_monitor.png "Spark Monitor"