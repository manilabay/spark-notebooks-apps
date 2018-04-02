# spark-notebooks-apps

This repo is to refresh the author's Spark knowledge, to play a little bit again with it and hit an interview process with more chances, it could be useful for people learning Spark programming as well. Cross the fingers and wish him good luck ;)

It will be an exercise to create and run simple Apps using Scala(with sbt), Python(with pip), Java(with maven), SQL, Parquet.

## Spark programming ELI5 (Explain me Like I´m 5)

You must think about it as an extra layer to do your programmer life easier. Basically Spark programming is a chain of dots with instructions(aggregates, transformations, filters, etc) and every dot represent an input and output in a long data pipeline. Also you can extend your Spark programming using the typical objects and functions in every programming language with focus in data capabilities, for example in python it is common to develop Spark Apps using Python numpy and pandas library and mix with the Spark programming.

To run programs through Spark pipeline you develop in your favourite or more adecuated language for every Use Case App you are developing and you just need to connect with Spark, instancing SparkSession, SparkContext, SparkConf, and so on.

## Spark infrastructure

This guide have the focus in Spark programming so the infra required is out of scope but basically, you would need to setup your Spark cluster in your infra or in Cloud following the Spark guides and choose a cluster manager fit with your strategy and your Architecture base: Mesos, Kubernetes. Also you will need install maven, sbt and pip in your CI system and setup the spark-submit in your scripts to launch the Apps in the cluster. A good strategy will be run the builds, tests and executions within Docker containers (only if you have a good Docker experience or Docker experts in your team). Also if you are in a Event-Driven-Architecture stage you could use Kafka to produce and consume from/to another data systems.

## Dependencies

* [Spark](https://spark.apache.org)
* Scala + [sbt](https://www.scala-sbt.org/)
* Python 3.x + pip
* Java + maven
* [Parquet](https://parquet.apache.org)

## Useful References

* [Data Pipeline Architecture Reference with Spark](https://github.com/manilabay/dot-graphviz-aws/tree/master/diagrams/data-pipeline-architecture-reference) (own project)
* [Spark examples in Scala, Python, Java and R](https://github.com/apache/spark/tree/master/examples/src/main)
* [Databricks Notebooks](https://databricks.com/resources/type/example-notebooks)
* [PySpark Cheatsheet](https://www.datacamp.com/community/blog/pyspark-cheat-sheet-python)
* [SQL Programming guide](https://spark.apache.org/docs/latest/sql-programming-guide.html)
