# Ambari on Docker Machine and Swarm Cluster

This project contains fixes for https://github.com/sequenceiq/docker-ambari to run on Docker Machine and Swarm cluster

## Set up Docker Machine and Swarm Cluster
To set up Docker Machine and Swarm Cluster please follow the instruction in section 3 of https://github.com/sfedyakov/hadoop-271-cluster up to and including overlay network creation.

## Usage
Simple start is the following
```
curl -Lo .amb https://raw.githubusercontent.com/sfedyakov/docker-ambari/master/ambari-functions && source .amb && amb-deploy-cluster
```
This command will create the following services:
- amb-consul for cluster maintenance
- amb-server for ambari maintenance
- amb1 for cluster worker
- amb2 for cluster worker

You can specify the size and options for the cluster -- see usage of ambari-functions

Once the script finishes it prints out the following information

```
  HOSTGROUP  HOST
  ---------  -------------------
  master     amb1.service.consul
  slave_1    amb2.service.consul
```

Now you can connect to Ambari via forwarded port 8080

**NOTE: you can not use cluster immediately after script finishes, because actual Hadoop, HDFS and YARN are being installed by Ambari agents in background. This operation may take hours.** You can monitor progress in Ambari WEB UI.
