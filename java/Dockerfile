FROM ubuntu:14.04

RUN apt-get update -y && apt-get install -y \
    openjdk-7-jre-headless \
    openjdk-7-jdk \
    maven \
    tree \
    nano \
    wget && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN useradd --create-home --shell /bin/bash ubuntu

ENV HOME /home/ubuntu
ENV SPARK_VERSION 1.6.2
ENV HADOOP_VERSION 2.6
ENV MONGO_SPARK_VERSION 1.1.0
ENV SCALA_VERSION 2.10

WORKDIR ${HOME}

ENV SPARK_HOME ${HOME}/spark-${SPARK_VERSION}-bin-hadoop${HADOOP_VERSION}
ENV PATH ${PATH}:${SPARK_HOME}/bin

COPY files/readme.txt files/pom.xml /home/ubuntu/
COPY files/src /home/ubuntu/src

RUN chown -R ubuntu:ubuntu /home/ubuntu/*
USER ubuntu

# get spark
RUN wget http://apache.mirror.digitalpacific.com.au/spark/spark-${SPARK_VERSION}/spark-${SPARK_VERSION}-bin-hadoop${HADOOP_VERSION}.tgz && \
tar xvf spark-${SPARK_VERSION}-bin-hadoop${HADOOP_VERSION}.tgz

RUN rm -fv spark-${SPARK_VERSION}-bin-hadoop${HADOOP_VERSION}.tgz
