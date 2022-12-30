# __Notes__

## __Docker__
### What is Docker?
Docker is a platform or ecosystem around creating and running containers (Docker Client, Docker Server, Docker Machine, Docker Images, Docker Hub, Docker Compose).

### Why Docker?
- Running our app right now makes big assumptions about our environment.
- Running our app requires precise knowledge of how to start it (npm start).
- Docker solves both these issues. Containers wrap up everything that is need for a program + how to start and run it.

### Terminology
- Image: Single file with all the deps and config required to run a program. It contains a snapshot of the file system and a specific start command.
- Container: Instance of an image. Runs a program and it has a very specific portion of hard drive, network, RAM, CPU, etc.


## __Kubernetes__
### Why Kubernetes?
- Kubernetes is a tool for running a bunch of different containers together.
- We give it some configuration to describe how we want our containers to run and interact with eachother.

### Terminology
- __Cluster__: A collections of nodes + a master to manage them.
- __Node__: A virtual machine that will run our container.
- __Pod__: _More or less_ a running container. Technically, a pod can run multiple containers. 
- __Deployment__: Monitors a set of pods, make sure they are running an restarts them if ther crashed.
- __Service__: Provides an easy-to-remember URL to access a running container.
__Deployments__, __pods__ and __services__ are called objects in Kubernetes.

### Types of Services
- __Cluster IP__: Sets up an easy-to-remember URL to access a pod. Only exposes pods _in the cluster_.
- __Node Port__: Makes a pod accessible from _outside the cluster_. Usually only used for dev purposes.
- __Load Balancer__: Makes a pod accessible from _outside the cluster_. This is the right way to expose a pod to the outside world.
- __External Name__: Redirects an in-cluster request to CNAME url.