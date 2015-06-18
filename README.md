# docker-mesos-spark

An attempt to run an Apache Mesos cluster within Docker containers.

## Usage

Launch the Mesos master in the background:

```
$ docker-compose up -d master
```

Next, launch a Mesos slave in the background:

```
$ docker-compose up -d slave
```

Lastly, launch a Spark driver connected to the Mesos master:

```
$ docker-compose build driver
$ docker-compose run driver /bin/bash
root@31a6abd640ce:/# /opt/spark/bin/spark-shell --master mesos://${MASTER_PORT_5050_TCP_ADDR}:5050
```
