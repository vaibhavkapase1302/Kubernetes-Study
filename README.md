## Kubernetes Kickstarter

## Architecture Guides

1. [Kubernetes Architecture Guide](./kubernetes_architecture.md)

## Examples with Interview Questions

1. [NGINX with Deployment & Service](./examples/nginx)
2. [MySQL with ConfigMaps, Secrets & Persistent Volumes](./examples/mysql)

## Installation Guides

1. [Kubeadm Installation Guide](./kubeadm_installation.md)
2. [Minikube Installation Guide](./minikube_installation.md)

## Practice Projects

1. [Microservices on k8s](https://github.com/LondheShubham153/microservices-k8s)
2. [Django App Deployment](https://github.com/LondheShubham153/django-todo-cicd)
3. [Redit Clone with Ingress](https://github.com/LondheShubham153/reddit-clone-k8s-ingress)
4. [For More Challenges, Check Out These Ideas](./examples/More_K8s_Practice_Ideas.md)

## Installation of kubectl on Windows and commands 

Install and Set Up kubectl on Windows Docs:- 
[https://kubernetes.io/docs/tasks/tools/install-kubectl-windows/](https://kubernetes.io/docs/tasks/tools/install-kubectl-windows/)

Install kubectl binary with curl on Windows  

```sh
curl.exe -LO https://dl.k8s.io/release/v1.30.0/bin/windows/amd64/kubectl.exe
```

Check version: 
```sh
kubectl version –client
```

Set up AWS Profile: 

```sh
SET AWS_PROFILE=FacctumSSMAccess-223530587197 >  --for AWS Development a/c 
```

AWS sso login 

```sh
aws sso login 
```

updates the local kubeconfig file with the configuration needed to access an Amazon EKS cluster named “facctum-dev-eks-cluster" 

```sh
aws eks update-kubeconfig --name facctum-dev-eks-cluster 
```
 
Lists all pods in the current namespace 

```sh '
kubectl get nodes 
```

Lists all namespaces in the cluster 

```sh
kubectl get ns  
```

list of all pods in the “facctlist-dev” namespace 

```sh
kubectl get pods -n <pod name>
```

```sh
e.g. kubectl get pods -n facctlist-dev 
```

streams the logs for the pod facctlist-frontend-deployment-7486c5f47-srx92 in the facctlist-dev namespace 

```sh
kubectl logs -n <namespace> <pod-name> 
```

```sh
e.g. kubectl logs -n facctlist-dev -f facctlist-frontend-deployment-7486c5f47-srx92 
```

### More kubectl commands 

https://kubernetes.io/docs/reference/kubectl/quick-reference/ 


Lists all configmaps in the current namespace. 

```sh
kubectl get configmaps  
```

Lists all secrets in the current namespace. 

```sh
kubectl get secrets 
```
 
Show Merged kubeconfig settings 

```sh
kubectl config view > 
```
 
Show Merged kubeconfig settings 

```sh
kubectl explain pods 
```
 
List all services in the namespace 

```sh
kubectl get services
```

List all pods in all namespaces 

```sh
kubectl get pods --all-namespaces  
```

Get a pod's YAML 

```sh
kubectl get pod <pod name>-o yaml
``` 

```sh
e.g. kubectl get pod facctlist-frontend-deployment-69745f5b47-5vw46 -o yaml 
```
 
#### Some of the most commonly used kubectl commands include:

```kubectl get:``` Retrieve information about resources (pods, deployments, services, etc.).
```kubectl create:``` Create a new resource from a file or stdin.
```kubectl apply:``` Apply a configuration to a resource.
```kubectl describe:``` Show detailed information about a resource.
```kubectl logs:``` Print the logs for a container in a pod.
```kubectl exec:``` Execute a command in a container.
```kubectl delete:``` Delete resources by filenames, stdin, resources, and names, or by resources and label selector.
```kubectl rollout:``` Manage the rollout of a resource (e.g., deployments).
```kubectl scale:``` Change the number of replicas of a resource.
```kubectl port-forward:``` Forward one or more local ports to a pod.
```kubectl get events:``` Display events related to resources.
```kubectl top:``` Display Resource (CPU/Memory/Storage) usage.

```kubectl create``` is a command used to create a resource by specifying the resource type and configuration through either a file or directly in the command.

For example, you can use ```kubectl create -f deployment.yaml``` to create a deployment using the configuration defined in the **deployment.yaml** file. Alternatively, you can use ```kubectl create deployment my-deployment --image=my-image``` to create a deployment named my-deployment using the **my-image** Docker image.


