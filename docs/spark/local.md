# Running Spark Locally

In case you want to run some quick tests on a small dataset (without creating connection to CERN clusters), you can use an instance of Spark that is local to your SWAN session. In order to do so, Python notebooks have a [SparkConf](https://spark.apache.org/docs/latest/api/python/pyspark.sql.html#pyspark.sql.SparkConf) variable pre-defined (`swan_spark_conf`) that will allow you to use e.g. spark monitor integration. You can use that variable to create, for example, a [SparkContext](https://spark.apache.org/docs/latest/api/python/pyspark.html#pyspark.SparkContext):

``` python
from pyspark import SparkContext
sc = SparkContext.getOrCreate(conf = swan_spark_conf)
```