# K8S
## Name:
* Node:
* Cluster:
* Pods: 
    * Pods are the smallest deployable units of computing that you can create and manage in Kubernetes.
    * A Pod (as in a pod of whales or pea pod) is a group of one or more containers, with shared storage and network resources
## Node Component:
* container runtimes : Enable pod to run on each node in cluster.
* kubelet: Enable containers running in pods.
* kube-proxy: Enable network on each node.

## Minikube
### Deployment
* Usage:
    * Check health of Pods.
    * Restart Pods.
* Create a deployment:
```
kubectl create deployment hello-node --image=k8s.gcr.io/echoserver:1.4
```
* Use some ==kubectl== command to check status of deployment, pods, (cluster event?)
### Service
* Expose to the public internet
```
kubectl expose deployment hello-node --type=LoadBalancer --port=8080
```
* start a service
```
minikube service hello-node
```
![](https://i.imgur.com/3H5iXMp.png)

* In the "Katacoda environment(in-browser)" go to port number: 31758 then show
> CLIENT VALUES:
> client_address=172.18.0.1
> command=GET
> real path=/
> query=nil
> request_version=1.1
> request_uri=http://2886795288-31758-jago01.environments.katacoda.com:8080/
> 
> SERVER VALUES:
> server_version=nginx: 1.10.0 - lua: 10001
> 
> HEADERS RECEIVED:
> accept=text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
> accept-encoding=gzip
> accept-language=en-US,en;q=0.9,zh-TW;q=0.8,zh;q=0.7
> host=2886795288-31758-jago01.environments.katacoda.com
> referer=https://2886795288-jago01.environments.katacoda.com/
> sec-ch-ua=" Not A;Brand";v="99", "Chromium";v="98", "Google Chrome";v="98"
> sec-ch-ua-mobile=?0
> sec-ch-ua-platform="Windows"
> sec-fetch-dest=document
> sec-fetch-mode=navigate
> sec-fetch-site=same-site
> sec-fetch-user=?1
> upgrade-insecure-requests=1
> user-agent=Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/98.0.4758.102 Safari/537.36
> via=1.1 google
> x-cloud-trace-context=299bca84d0ff14f430003c3e30fc1281/8273605122034481456
> x-forwarded-for=118.166.111.101, 35.201.124.219, 130.211.2.179, 35.186.156.29, 172.17.0.7
> x-forwarded-proto=https
> x-katacoda-host=jago01
> x-real-ip=35.186.156.29
> BODY:
> -no body in request-


## container runtimes 