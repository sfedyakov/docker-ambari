# Ambari on Docker Machine and Swarm Cluster

This project contains fixes for https://github.com/sequenceiq/docker-ambari to run on Docker Machine and Swarm cluster

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

