# Running Spark Locally

As before, you can use an instance of Spark that is local to your SWAN session. In order to do so, Python notebooks have a [SparkConf](https://spark.apache.org/docs/latest/api/python/pyspark.sql.html#pyspark.sql.SparkConf) variable pre-defined (_swan\_spark\_conf_). Therefore, if you would like to create a [SparkContext](https://spark.apache.org/docs/latest/api/python/pyspark.html#pyspark.SparkContext), you can do:

    from pyspark import SparkContext
    sc=SparkContext.getOrCreate(conf=swan_spark_conf)