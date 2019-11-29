# ClickHouse Helm Chart  

Fully functioning replicated ClickHouse environment. It uses official clickhouse image with server and client inside.  
  
It can use build-in zookeeper or external one.  
If you use just one replica zookeeper can be turned off at all - by setting `zookeeper.enabled=false` and `externalZookeeper.enabled=false`.  
If you want to use build-in zookeeper you need to set `clusterDomain` of your k8s.  
Default clickhouse user `default` with no password.  
## Run  

```bash
helm install --name clickhouse ./clickhouse
```
