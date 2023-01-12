# Commands

## Docker (most common)
- Build an image based on the dockerfile in the current directory. Tag it as 'braianmg/posts': `docker build -f braianmg/posts`
- Create an start a container based on the provided image id or tag: `docker run [image id or image tag]`
- Create an start container, but also override the default comman: `docker run -it [image id or image tag] [cmd]`
- Print out information about all of the running containers: `docker ps`
- Execute the given comman in a running container: `docker exec -it [container id] [cmd]`
- Print out logs from the given container: `docker logs [container id]`

## Kubernetes (most common)
- Print out information about all of the running pods: `kubectl get pods`
- Execute the given command in a running pod: `kubectl exec -id [pod_name] [cmd]`
- Print out logs from the given pod: `kubectl logs [pod_name]`
- Deletes the given pod: `kubectl delete pod [pod_name]`
- Tells kubernetes to process the config: `kubectl apply -f [config file name]`
- Print out some information about the running pod: `kubectl describe pod [pod_name]`
- Execute a console in a running pod: `kubectl exe -it [pod_name] sh`
  - To exit the console: `exit`

### Deployment Commands
- List all the running deployments: `kubectl get deployments`
- Print out details about a specific deployment: `kubectl describe deployment [depl name]`
- Create a deployment out of a config file: `kubectl apply -f [config file name]`
- Delete a deployment: `kubectl delete deployment [depl name]`



### Updating the image used by a Deployment (recomended method)
- The deployment must be using the 'latest' tag in the pod spec section, for example:
  - `image: cursomicroservicios/posts:latest`
  - `image: cursomicroservicios/posts`
- Make an update to your code
- Build the image: `docker build -t [name] [dir]`
- Push the image to docker hub: `docker push [name]`
- Run the command: `kubectl rollout restart deployment [depl_name]`