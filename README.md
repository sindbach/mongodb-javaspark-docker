# Docker for MongoDB and Apache Spark. 

An example of docker-compose to set up a single [Apache Spark](http://spark.apache.org/) node connecting to [MongoDB](https://www.mongodb.com/) via [MongoDB Spark Connector](https://github.com/mongodb/mongo-spark) using JAVA. 

** For demo purposes only **


#### Environment : 

* Ubuntu v14.04
* Apache Spark v1.6.2
* MongoDB Spark Connector v1.1.0
* MongoDB v3.2.x
* Java 1.7
* Maven 

### Starting up 

You can start by running command : 

```
docker-compose run java bash
```

Which would run the spark node and the mongodb node, and provides you with bash shell for the java spark instance. 

From the spark instance, you could reach the MongoDB instance using `mongodb` hostname. 

From the home dir `/home/ubuntu`, you should be able to compile the Java introduction file: 

```
mvn package 
```

Which should generate a jar file in the `target` directory. 
You can then execute using: 

```
spark-submit --class tour.JavaIntroduction ./target/tour-1.0-SNAPSHOT.jar 
```

### More Information. 

See related article:

* [MongoDB Spark Connector](https://docs.mongodb.com/spark-connector/)

* [MongoDB Course M233: Getting Started with Spark and MongoDB](https://university.mongodb.com/courses/M233/about)

* [MongoDB Hadoop use cases ](https://docs.mongodb.org/ecosystem/use-cases/hadoop/)

* [MongoDB Blog: aggregating intervals of stock prices](https://www.mongodb.com/blog/post/using-mongodb-hadoop-spark-part-1-introduction-setup)

