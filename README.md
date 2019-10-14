# Kubernetes

It is an open source container management tool. It can help in automate the deployment, scaling up the application, and operation of application containers across clusters. It helps in moving from the host-centric infrastructure to container-centric infrastructure.

## What can Kubernetes do?
-   Create Kubernetes cluster
-   Deploy an app
-   Explore your app
-   Explore your app publicaly
-   Scale up your app
-   Update your app


## Kubernetes Jargons
-   Kubernetes Clusters
-   Master
    -   etcd
    -   API Server
    -   Controller Manager
    -   Scheduler
-   Node
    -   Docker
    -   Kubelet Service
    -   Kubernetes Proxy Service
-   Node Processes

![alt text](https://github.com/konicapatait/kubernetes/blob/master/images/kubernetes-arch.png "kubernetes Components")

-   Minikube

    It is a tool that makes it easy to run the kubernetes locally. Minikube runs **single node** kubernetes cluster inside VM on your laptop.

    -   `minikube start`

    -   `minikube dashboard`

    -   

-   Kubectl

    It is a command line interface for kubernetes. It controls the kubernetes cluster and manage the nodes in cluster.

    -   `kubectl version`

        -   <b>Client Version:</b> version.Info{Major:"1", Minor:"15", GitVersion:"v1.15.2", GitCommit:"f6278300bebbb750328ac16ee6dd3aa7d3549568", GitTreeState:"clean", BuildDate:"2019-08-05T09:23:26Z", GoVersion:"go1.12.5", Compiler:"gc", Platform:"linux/amd64"}

        -   <b>Server Version:</b> version.Info{Major:"1", Minor:"15", GitVersion:"v1.15.0", GitCommit:"e8462b5b5dc2584fdcd18e6bcfe9f1e4d970a529", GitTreeState:"clean", BuildDate:"2019-06-19T16:32:14Z", GoVersion:"go1.12.5", Compiler:"gc", Platform:"linux/amd64"}

    -   `kubectl cluster-info`
    
        -   Kubernetes master is running at https://172.17.0.14:8443
        -   KubeDNS is running at https://172.17.0.14:8443/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy

    -   `kubectl get nodes`

                 NAME       STATUS   ROLES    AGE     VERSION

                minikube    Ready    master   9m14s   v1.15.0 
    
    -   `kubectl api-versions`

    -   `kubectl run`
    
            kubectl run kubernetes-bootcamp --image=gcr.io/google-samples/kubernetes-bootcamp:v1 --port=8080
            
    -   `kubectl get deployments`

-   Kubernetes Pods

    It is a group of containers that are deployed together on the same host. If you frequently deploy single containers, you can generally replace the word "pod" with "container" and accurately understand the concept.

-   