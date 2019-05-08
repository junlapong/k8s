# Install Kubernetes on Mac

![](https://2.bp.blogspot.com/-BOa91Nbp9FU/WyuhO_0k1sI/AAAAAAAARIA/wn8-wBidYAIdI1Y6kT3PAczsKRu2gjllACLcBGAs/s1600/kubectlToMangerClusterInsideMinikubeVM.PNG)

## Installation Guide
The only pre-requisite for this guide is that you have [Homebrew](https://brew.sh/) installed. Homebrew is a package manager for the Mac. You’ll also need Homebrew Cask, which you can install after Homebrew by running 

```
brew tap caskroom/cask
```

### 1. Install Docker for Mac.
Docker is used to create, manage, and run our containers. It lets us construct containers that will run in Kubernetes Pods.

- [Install Docker Desktop for Mac](https://docs.docker.com/docker-for-mac/install/)

### 2. Install VirtualBox
For Mac using Homebrew. VirtualBox lets you run virtual machines on your Mac (like running Windows inside macOS, except for a Kubernetes cluster.)

```
brew cask install virtualbox
brew cask install virtualbox-extension-pack
```

### 3. Install kubectl for Mac
This is the command-line interface that lets you interact with Kuberentes.

```
brew install kubectl
```

### 4. Install Minikube

```
brew cask install minikube
```

### 5. Everything should work!
Start your Minikube cluster with (*minikube start might take a few minutes)

```
minikube start
minikube dashboard
```

Then run

```
kubectl api-versions
```

If you see a list of versions, everything’s working!

For verbose

```
minikube -v10 start
minikube -v10 stop
```

## Notes
- VirtualBox is a generic tool for running virtual machines. You can use it to run Ubuntu, Windows, etc. inside your macOS operating system host.
- Minikube is a Kubernetes-specific package that runs a Kubernetes cluster on your machine. That cluster has a single node and has some unique features that make it more suitable for local development. Minikube tells VirtualBox to run. Minikube can use other virtualization tools—not just VirtualBox—however these require extra configuration.
- kubectl is the command line application that lets you interact with your Minikube Kubernetes cluster. It sends request to the Kubernetes API server running on the cluser to manage your Kubernetes environment. kubectl is like any other application that runs on your Mac—it just makes HTTP requests to the Kubernetes API on the cluster.

## References
- [How to Install Kubernetes on Mac](https://matthewpalmer.net/kubernetes-app-developer/articles/guide-install-kubernetes-mac.html)
- [Kubernetes: Orchestration Framework for Containers](https://www.middlewareandme.tech/2018/02/kubernetes-orchestration-framework-for_24.html)
- [มาลอง Kubernetes ด้วย Minikube กันเถอะ](https://medium.com/@phayao/%E0%B8%A1%E0%B8%B2%E0%B8%A5%E0%B8%AD%E0%B8%87-kubernetes-%E0%B8%94%E0%B9%89%E0%B8%A7%E0%B8%A2-minikube-%E0%B8%81%E0%B8%B1%E0%B8%99%E0%B9%80%E0%B8%96%E0%B8%AD%E0%B8%B0-b8a7bd1a6b59)
- [สร้าง CI/CD ด้วย Jenkins บน Kubernetes แบบง่ายๆ](https://medium.com/@phayao/%E0%B8%AA%E0%B8%A3%E0%B9%89%E0%B8%B2%E0%B8%87-ci-cd-%E0%B8%94%E0%B9%89%E0%B8%A7%E0%B8%A2-jenkins-%E0%B8%9A%E0%B8%99-kubernetes-%E0%B9%81%E0%B8%9A%E0%B8%9A%E0%B8%87%E0%B9%88%E0%B8%B2%E0%B8%A2%E0%B9%86-fd4a1a496c46)