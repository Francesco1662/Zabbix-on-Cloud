## Introduction

- In this repository contains files necessary to provisioning Zabbix in Kubernetes

# Pre requirements

- Kubernetes (Used version: v1.18.0)


# Step by Step


1- Execute the apply to create namespace.

```
kubectl apply -f namespace.yaml
```

2- Execute the apply to create configmaps
```
kubectl apply -f configmaps.yaml
```

3 - Execute the apply to create secrtetes
```
kubectl apply -f secretes.yaml
```

4 - Execute the apply to create database
```
kubectl apply -f database-pgsql.yaml 
```

6- Execute the apply to create zabbix-server

```
 kubectl apply -f zabbix-server.yaml
```
7 - Execute the apply to create frontend

```
 kubectl apply -f zabbix-frontend.yaml 
```

Execute the command to get informations about your enviromennt:

```
kubectl get deployment,svc,pods,pvc,ingress  -n monitoring




## Access

To  you access  Zabbix through the Minikube, execute this command:

```
$ minikube tunnel
Status:	
	machine: minikube
	pid: 4042
	route: 10.96.0.0/12 -> 172.17.0.2
	minikube: Running
	services: []
    errors: 

```

After that execute this command to get IP address of the Zabbix Frontend:

```
$ kubectl get svc  -n monitoring
...
zabbix-web-nginx-pgsql   ClusterIP   10.103.89.223   <none>        8081/TCP,8443/TCP   18h

```
