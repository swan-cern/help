# Spark Monitoring

If you are running Spark jobs on a CERN cluster, you can now keep track of their execution right from inside the notebook. This functionality is provided by the **Spark Monitor**: anytime you run a cell that triggers a Spark computation, an interactive monitoring display will automatically appear below that cell.

![][spark_monitor]

With this tool you can see in detail the jobs, including stages, and the tasks that are running. You can also inspect the resource utilization and access the Spark UI.


![][spark_conn_details]

After estabilishing successful connection, you will be shown some connection details which allow you to check your workload tasks/stages details and performance metrics. 

[spark_conn_details]: ../images/spark_conn_details.png "Spark Connection Details"
[spark_monitor]: ../images/spark_monitor.png "Spark Monitor"
