FROM mesosphere/mesos:0.22.1-1.0.ubuntu1404

ENV SPARK_VERSION 1.4.0
ENV HADOOP_VERSION 2.4

# Update the base ubuntu image with dependencies needed for Spark
RUN apt-get update && \
    apt-get install -y python libnss3 openjdk-7-jre-headless curl

RUN curl http://d3kbcqa49mib13.cloudfront.net/spark-${SPARK_VERSION}-bin-hadoop${HADOOP_VERSION}.tgz \
    | tar -xzC /opt && mv /opt/spark-1.4.0-bin-hadoop2.4 /opt/spark
ENV SPARK_HOME /opt/spark
ENV MESOS_NATIVE_JAVA_LIBRARY /usr/local/lib/libmesos.so
