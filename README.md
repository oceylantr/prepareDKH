# prepareDKH

A simple script to install Docker, Kubernetes and Helm on a fresh Ubuntu 16.04 installation. 

At the end, you will have Docker Community Edition, Kubernetes with RBAC installed by KubeAdm and Helm package manager, already installed with Tiller on your Kubernetes cluster. I've chosen Calico as ingress controller, feel free to choose any other like Flannel and etc...

Warning !!: Script closes Swap space usage on current Linux, Kubelet needs that. Use at your own risk !

## Getting Started

### Prerequisites

1-  Linux distro (tried on Ubuntu 16.04 LTS)

### Installing

Download code with below command on your working directory:

```
sudo git clone https://github.com/oceylantr/prepareDKH.git
```

Give all permission for passing security phase now:

```
sudo chmod -R 777 prepareDKH
```

Get in the code 

```
cd prepareDKH
sudo ./prepareDKH.sh
```

## Verifiying installation

We can see container status with 

```
sudo docker ps
```

Check Kubernetes cluster status
```
sudo kubectl get pods --all-namespaces
sudo kubectl get ns
sudo kubectl get services
```

Check Helm & Tiller status. You should wait some time for Tiller pod to be deployed on "kube-system" ns of your Kubernetes cluster; then you will be able to see Tiller version, too
```
helm version
```

## Component Versions Now
Kubernetes 1.12.2

Docker Community Edition 18.06.0 ce 3-0~ubuntu

Helm 2.11.0

Calico 3.3 RBAC


## Built With

* [Kubeadm](https://github.com/kubernetes/kubeadm) - Nice tool to create Kube cluster from scratch
* [Helm](https://helm.sh/) - Perfect package manager for Kubernetes
* [Docker](https://www.docker.com/) - You know what it is I think

## Authors

* **Oğuzhan Ceylan** - *Initial work* - [oceylantr](https://github.com/oceylantr)

## License

This project is licensed under the GPL v3.0 - see the [LICENSE](LICENSE) file for details

