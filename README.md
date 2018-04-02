# spark-notebooks-apps

This repo is to refresh the author's Spark knowledge, to play a little bit again with it and hit an interview process with more chances, it could be useful for people learning Spark programming as well. Cross the fingers and wish him good luck ;)

It will be an exercise to create and run simple Apps using Scala(with sbt), Python(with pip), Java(with maven), SQL, Parquet.

## Spark programming ELI5 (Explain me Like I´m 5)

You must think about it as an extra layer to do your programmer life easier. Basically Spark programming is a chain of dots with instructions(aggregates, transformations, filters, etc) and every dot represent an input and output in a long data pipeline. Also you can extend your Spark programming using the typical objects and functions in every programming language with focus in data capabilities, for example in python it is common to develop Spark Apps using Python numpy and pandas library and mix with the Spark programming.

To run programs through Spark pipeline you develop in your favourite or more adecuated language for every Use Case App you are developing and you just need to connect with Spark, instancing SparkSession, SparkContext, SparkConf, and so on.

## Spark Streaming

Basically Spark Streaming differ from Spark Core as it is an additional stage placed previously in the Data Pipeline which has the function to ingest a continuous dataflow and convert in a discretized dataflow (called DStream) formed by several data packages (called RDDs). What happened under the hoods really is, Spark Streaming distribute to the nodes(in-memory) and process a RDDs sequence. Each RDDs cycle is configured and processed by a time interval. It is a batch processing but setup automatically until a termination Signal is received.

The basic programming steps to setup a Spark Streaming pipeline are:

* Create a SparkContext that points to your cluster
* Create a StreamingContext(specify the size or time interval of the batch in seconds) from the SparkContext
* Create the DStream for your input sources
* Apply transformations
* Push transformations results to target systems

**Important notes to have in mind**
* Remember in your sizing exercise than 1 DStream = 1 Receiver, for a read parallelism multiple receivers, so multiple DStream need to be created. 1 receiver run within 1 executor and it occupies 1 Core. Ensure that there are enough cores for processing after receiver slots are booked (for example using spark.cores.max) Receivers are allocated to executors with round robin method.


## Spark infrastructure

This guide have the focus in Spark programming so the infra required is out of scope but basically, you would need to setup your Spark cluster in your on-premise infrastructure or your Cloud provider following the Spark guides and choose a cluster manager fit with your strategy and your Architecture base: YARN, Mesos, Kubernetes. Also you will need install maven, sbt and pip in your CI system and setup the spark-submit in your scripts to chain and launch the Apps in the cluster. A good strategy will be run the builds, tests and executions within Docker containers (only if you have a good Docker experience or Docker experts in your team). Also if you are in a Event-Driven-Architecture stage you could use Kafka to produce and consume from/to another data systems.

## Spark simple config & launch

```console
./bin/spark-submit --class "YourApp" --master local[4]   
```

## Dependencies

* [Spark](https://spark.apache.org)
* Scala + [sbt](https://www.scala-sbt.org/)
* Python 3.x + pip
* Java + maven
* [Parquet](https://parquet.apache.org)

## Useful References

* [Data Pipeline Architecture Reference with Spark](https://github.com/manilabay/dot-graphviz-aws/tree/master/diagrams/data-pipeline-architecture-reference) (own project)
* [Spark Configuration](https://spark.apache.org/docs/latest/configuration.html)
* [Spark examples in Scala, Python, Java and R](https://github.com/apache/spark/tree/master/examples/src/main)
* [Databricks Notebooks](https://databricks.com/resources/type/example-notebooks)
* [PySpark Cheatsheet](https://www.datacamp.com/community/blog/pyspark-cheat-sheet-python)
* [SQL Programming guide](https://spark.apache.org/docs/latest/sql-programming-guide.html)
* [Spark Streaming](https://people.apache.org/~pwendell/spark-releases/latest/streaming-programming-guide.html)
