# Kubernetes

## What is container?

A container is a collection of software processes unified by one namespace with access to an operating system kernel that it shares with other containers with little or no access to other containers.

## Container Orchestrator Features
-   Provison Hosts
-   Intantiate container on a host
-   Restart failing containers
-   Expose containers as a services outside the cluster
-   Scaling the cluster up and down

## Players in Market
-   Docker Swarm 
    -   Used by startups and mid-size organizations
-   Mesos
    -   Oldest in the market and mostly driven by developers.
    -   Complex architecture than Docker Swarm.
-   Rancher
-   Kubernetes

![alt text](https://github.com/konicapatait/kubernetes/blob/master/images/container-orchestration.png "Container Orchestration")

## Kubernetes

It is an open source container management tool. It can help in automate the deployment, scaling up the application, and operation of application containers across clusters. It helps in moving from the host-centric infrastructure to container-centric infrastructure.

## Kubernetes Features

-   Multi-Host Container Scheduling
    -   Handled by Kube Scheduler
    -   Assigns Pods to nods at runtime
    -   Checks resources, quality of services, policies, user specifications before scheduling
-   Scalability and Availability
    -   K8s master can be deployed in highly available configuration.
    -   Multi region deployments available.
    -   Supports 5000 node clusters, 150,000 total pods.
    -   2 features that allow scalibility at K8s level: Registration and Service Discovery.
        -   New worker nodes can seemlessly register themselves with the master node.
        -   Allows automatic detection of services and endpoints via DNS or environment variables. 
-   Flexibility and Modularization
    -   Plug and play architecture; extend the architecture when needed.
    -   Add-ons: Network drivers etc.
-   Application Upgrades and Downgrades
    -   K8s supports the backword compatibility.
    -   During K8s maintanence, unregister the host so that no deployment can happen and ones it is done, turn on the host and schedule the deployments on it.
-   Logging and monitoring
    -   Built-in application monitoring
    -   Node health check handled by node controller
    -   K8s status is 
-    Secret Management
    -   Sensitive data is first class citizen.
    -   Mounted as data volumes or env variables
    -   Specific to namespace.


## What can Kubernetes do?
-   Create Kubernetes cluster
-   Deploy an app
-   Explore your app
-   Explore your app publicaly
-   Scale up your app
-   Update your app

## Kubernetes and Docker

Kubernetes is a container platform. Docker is used to develop and build the application. Kubernetes is used to schedule and run the containers on your infrastructure.

## Kubernetes Jargons
-   Kubernetes Clusters

    ![alt text](https://github.com/konicapatait/kubernetes/blob/master/images/kubernetes-clusters.png "kubernetes Cluster")

-   Master

    It takes care of overall management of kubernetes cluster.

    -   The API Server
        -   Kube API server allows to communicate with Kubernetes API.
    -   Controller Manager
    -   Scheduler
        -    created
    
     -   etcd
        -   Simple distributed key value storage.
        -   Kubernetes uses this as a database and store all cluster data in there like job scheduling info, pod details, stage information etc.
    -   Kubectl
        -   To interact with master node; it is a command line interface for Kubernetes.
        -   It has config file called as kubeconfig. It has server information and authenitification information to access the API server.

-   Worker Nodes

    It is where the application operates. It communicate back with master node and communication is handled by **kubelet process**. 

    -   Container running platform / Docker

    -   Kubelet Service/ Kubelet Process

        It is a agent that communicate with API Server, if the PODS have been designed to the nodes.
        It executes the pod container. It mounts and runs PODS volume and secrets. Also, it is aware about the PODS state on node and respond it back to master node.
    -   Kubernetes Proxy Service

        Network proxy and load balancer for a service, on a single Worker node.
        Handles network routing for TCP and UDP packets and perform connection forwarding.

-   Node Processes

-   POD

    Containers of an applications are tightly couple together in a POD. So by definition

        POD is a smallest unit that can be scheduled as a deployment in kubernetes. This group of containers share storage, linux name space, IP addressess etc.

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

    -   `kubectl proxy`

        This command create a proxy that will forward the communication into the cluster-wide private network

-   Kubernetes Pods

    It is a group of containers that are deployed together on the same host. If you frequently deploy single containers, you can generally replace the word "pod" with "container" and accurately understand the concept.


## Kubernetes Architecture
    ![alt text](https://github.com/konicapatait/kubernetes/blob/master/images/kubernetes-architecture.png "kubernetes Architecture")

    -   Master Node
        - 