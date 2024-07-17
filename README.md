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

**Install kubectl binary with curl on Windows** 

```sh
curl.exe -LO https://dl.k8s.io/release/v1.30.0/bin/windows/amd64/kubectl.exe
```

**Check version**

```sh
kubectl version –client
```

**Set up AWS Profile:** 

```sh
SET AWS_PROFILE=FacctumSSMAccess-223530587197 >  --for AWS Development a/c 
```

**AWS sso login**

```sh
aws sso login 
```

```sh
aws sso login --profile dev-profile
```

**updates the local kubeconfig file with the configuration needed to access an Amazon EKS cluster named “facctum-dev-eks-cluster"** 

```sh
aws eks update-kubeconfig --name facctum-dev-eks-cluster 
```

```sh
aws eks update-kubeconfig --name facctum-dev-eks-cluster --profile dev-profile
```
 
**Lists all pods in the current namespace**

```sh '
kubectl get nodes 
```

**Lists all namespaces in the cluster** 

```sh
kubectl get ns  
```

**list of all pods in the “facctlist-dev” namespace** 

```sh
kubectl get pods -n <pod name>
```

```sh
e.g. kubectl get pods -n facctlist-dev 
```

**streams the logs for the pod facctlist-frontend-deployment-7486c5f47-srx92 in the facctlist-dev namespace** 

```sh
kubectl logs -n <namespace> <pod-name> 
```

```sh
e.g. kubectl logs -n facctlist-dev -f facctlist-frontend-deployment-7486c5f47-srx92 
```

**For checking the description of pod**

```sh
kubectl describe pod <pod name> -n <namespace-name>
```

```sh
kubectl describe pod admin-portal-frontend-64d46d5b65-kfm2p -n adminportal
```

**To check recent events:**

```sh
kubectl get events -n namespace
```

### More kubectl commands 

https://kubernetes.io/docs/reference/kubectl/quick-reference/ 


**Lists all configmaps in the current namespace.**

```sh
kubectl get configmaps  
```

**Lists all secrets in the current namespace.**

```sh
kubectl get secrets 
```
 
**Show Merged kubeconfig settings** 

```sh
kubectl config view > 
```
 
**Show Merged kubeconfig settings** 

```sh
kubectl explain pods 
```
 
**List all services in the namespace** 

```sh
kubectl get services
```

**List all pods in all namespaces** 

```sh
kubectl get pods --all-namespaces  
```

command lists detailed information about each node in the Kubernetes cluster, including internal and external IPs, OS image, kernel version, and container runtime.

```sh
kubectl get nodes -o wide
```

out:

```
NAME               STATUS   ROLES    AGE     VERSION   INTERNAL-IP     EXTERNAL-IP     OS-IMAGE             KERNEL-VERSION      CONTAINER-RUNTIME
ip-192-168-1-1     Ready    <none>   3d      v1.21.1   192.168.1.1     203.0.113.1     Ubuntu 20.04.2 LTS   5.4.0-1037-aws      docker://19.3.12
ip-192-168-1-2     Ready    <none>   3d      v1.21.1   192.168.1.2     <none>          Ubuntu 20.04.2 LTS   5.4.0-1037-aws      docker://19.3.12
```


**Get a pod's YAML** 

```sh
kubectl get pod <pod name>-o yaml
``` 

```sh
e.g. kubectl get pod facctlist-frontend-deployment-69745f5b47-5vw46 -o yaml

e.g. kubectl get deploy facctlist-backend-deployment -n facctlist -o yaml
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

```sh
kubectl apply -f tools/facctguard/facctguard-ui/ --namespace=facctguard
```

#### Create a config map

**Create ConfigMap locally**

```sh
vi facctview-backend-config.yaml
cat facctview-backend-config.yaml
kubectl apply -f facctview-backend-config.yaml
```

**Create ConfigMap from File**

kubectl ```create configmap``` with the ```--from-file```

```sh
kubectl create configmap <facctguard-config> --from-file=<facctguard-config.yaml>
```

**View ConfigMap Details**

```sh
kubectl describe configmap <facctguard-config>
```

**Apply ConfigMap**

```sh
kubectl apply -f <facctguard-ui> --namespace=<facctguard>
```

**Edit ConfigMap**

```sh
kubectl edit configmap facctguard-config
```

**Delete ConfigMap**

```sh
kubectl delete configmap facctguard-config
```

**To scale down pod:**

https://spacelift.io/blog/restart-kubernetes-pods-with-kubectl

https://komodor.com/learn/kubectl-scale-deployment-the-basics-and-a-quick-tutorial/

```kubectl scale deployment``` command to adjust the number of pods in a Deployment.

```sh
kubectl get deploy -n <facctlist-dev>   [ facctlist-dev is namaespace ]
```

**Stop the deployed container instances:**

```sh
kubectl scale deploy <facctlist-backend-deployment> -n <facctlist-dev> --replicas=0
```

```sh
kubectl get pods -n facctlist-dev
```

```sh
kubectl scale deploy facctlist-backend-deployment -n facctlist-dev --replicas=1
```

```sh
kubectl get pods -n facctlist-dev
```

When you scale your deployments to zero (0), this operation effectively stops the component or application. You scale the deployment back to your original number to restart the component or application.

**Delete Deployment: To delete a deployment:**

```bash 
kubectl get deployment -n <namespace-name>
```

output: 

```
NAME                             READY   UP-TO-DATE   AVAILABLE   AGE
facctguard-frontend-deployment   1/1     1            1           6d5h
```

```bash
kubectl delete deployment <deployment-name> -n <namespace-name>
```

e.g. 

```bash
kubectl delete deployment facctguard-frontend-deployment -n facctguard
```

```bash
kubectl delete deployment <DEPLOYMENT_NAME>
```

**To Create a Service Account for K8S**

vi facctlist-backend-service-account.yml

```yaml
apiVersion: v1
kind: ServiceAccount
metadata:
  annotations:
    eks.amazonaws.com/role-arn: arn:aws:iam::223530587197:role/facctlist_pod_iam_role
  name: factlist-s3-access
  namespace: facctlist
```

**name: factlist-s3-access**

```sh
kubectl apply -f facctlist-backend-service-account.yml
```

# AWS EKS Cluster Setup and Management

## Setting Up Your Environment

### Verify kubectl Installation

```bash
kubectl version --client
```

**Verify eksctl Installation**

```bash
eksctl version
```

## Creating an EKS Cluster Using eksctl

### Create an EKS Cluster with Specified Parameters

```bash
eksctl create cluster \
    --name <cluster-name> \
    --region <region> \
    --nodegroup-name <nodegroup-name> \
    --node-type <instance-type> \
    --nodes <number-of-nodes> \
    --nodes-min <min-nodes> \
    --nodes-max <max-nodes> \
    --ssh-access \
    --ssh-public-key <path-to-ssh-public-key>
```

e.g. 
```bash 
eksctl create cluster \
    --name my-eks-cluster \
    --region ap-south-1 \
    --nodegroup-name ng-1 \
    --node-type t2.micro \
    --nodes 2
```

**OR in windows**

```batch
eksctl create cluster --name my-eks-cluster --region ap-south-1 --nodegroup-name ng-1 --node-type t2.micro --nodes 2
```

**Verify Cluster Creation**

```bash
kubectl config current-context
```

**Verify Cluster Creation: Check the status of your EKS cluster.**

```bash
eksctl get cluster --name my-eks-cluster --region ap-south-1
```

**Configure kubectl to Use Your EKS Cluster:**

e.g. 
```bash
aws eks update-kubeconfig --name facctum-dev-eks-cluster --profile dev-profile
```

```bash
aws eks --region ap-south-1 update-kubeconfig --name my-eks-cluster --profile learning
```

**Verify Connection to Your EKS Cluster**

```bash
kubectl get nodes
```

**Verify Connection to Your EKS Cluster**

```bash
kubectl get componentstatus
```


end!!
