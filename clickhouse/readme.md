# ClickHouse
[ClickHouse](https://clickhouse.yandex/) is an open source column-oriented database management system capable of real time generation of analytical data reports using SQL queries.

## Introduction
This chart bootstraps a [ClickHouse](https://clickhouse.yandex/) replication cluster deployment on a [Kubernetes](http://kubernetes.io) cluster using the [Helm](https://helm.sh) package manager.

## Prerequisites
- Kubernetes 1.10+
- PV provisioner support in the underlying infrastructure

## Installing the Chart
```bash
helm repo add lohmag https://lohmag.github.io/helm-charts/
helm repo update
helm install clickhouse lohmag/clickhouse
```

## Uninstalling the Chart
To uninstall/delete the `clickhouse` deployment:

```bash
$ helm delete --purge clickhouse
```
## Configuration
Create replicated ClickHouse environment. I want it to be minimalistic, without any 3-rd party apps.  
It uses official clickhouse image with server and client inside.  
It can use build-in zookeeper or external one.  
If you use just one replica, zookeeper can be turned off at all - by setting 
`zookeeper.enabled=false` and `externalZookeeper.enabled=false` in `values.yaml`.  
If you want to use helm build-in zookeeper you need to set `clusterDomain` of your k8s.  
Default clickhouse user `default` with no password.  
All configuration done through configmaps.
