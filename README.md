# Project Initialization Guide

## To start the docker containers

Append the -d (detached mode) and --build (re-buid images) to startup the docker containers
```bash
$docker-compose up -d --build
```

## Initialize docker volume

To inspect the location of docker volume, you may run the following command

```bash
$docker volume ls
$docker volume inspect workspace_scripts_datastore
```

Take note of the "Mountpoint", copy the directory location, and migrate base validation_scripts into docker volume store

```bash
$cp -r ./validation_store/* <SPECIFY MOUNTPOINT HERE>/
```

## Initialize kafka topics

To create topics with kafka, you would need to untar the Kafka binary files and add the bin to your export path

```bash
$cd kafka_devtools
$tar -zxvf kafka_2.11-2.0.1.tgz
$mv kafka_2.11-2.0.1 /opt/kafka

$echo 'export PATH=$PATH:/opt/kafka/bin' >> ~/.bashrc

$source ~/.bashrc

$./kafka_init_commands.sh
```

## To initiate the prometheus, grafana plugin, kudos to https://github.com/stefanprodan/dockprom

```bash
$cd ../dockprom
$ADMIN_USER=admin ADMIN_PASSWORD=admin docker-compose up -d
```


## Sample ReactJS UI
```bash
https://stackblitz.com/edit/react-tvqvx4?file=index.js
``
