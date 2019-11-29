# ClickHouse Helm Chart  

Fully functioning replicated ClickHouse environment. I want it to be minimalistic, without any 3-rd party apps. It uses official clickhouse image with server and client inside.  
  
It can use build-in zookeeper or external one.  
If you use just one replica, zookeeper can be turned off at all - by setting 
`zookeeper.enabled=false` and `externalZookeeper.enabled=false`.  
If you want to use build-in zookeeper you need to set `clusterDomain` of your k8s.  
Default clickhouse user `default` with no password.  
All configuration done through configmaps.

## Run  
```bash
helm repo add lohmag https://lohmag.github.io/helm-charts/
helm repo update
helm install clickhouse lohmag/clickhouse
```
