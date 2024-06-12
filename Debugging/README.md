### Task 1: Getting the **CreateContainerConfigError** error

https://spacelift.io/blog/createcontainerconfigerror

https://stackoverflow.com/questions/50424754/pod-status-as-createcontainerconfigerror-in-minikube-cluster

### Task 2: Getting the **ImagePullBackOff** error


### Task 3: How to Restart the pod

https://spacelift.io/blog/restart-kubernetes-pods-with-kubectl

https://stackoverflow.com/questions/64299456/kubernetes-error-from-server-notfound-deployments-apps-kube-verify-not-fou

#### Multiple Methods are there:-
**1. Using **restart** command- kubectl rollout restart**

```kubectl rollout restart deployment <deployment_name> -n <namespace>```

**2. kubectl scale:**

```kubectl scale deployment <deployment name> -n <namespace> --replicas=0```

```kubectl scale deployment <deployment name> -n <namespace> --replicas=3```

```kubectl get pods -n <namespace>```

**3. kubectl delete pod and kubectl delete replicaset**

```kubectl delete pod <pod_name> -n <namespace>```

```kubectl delete replicaset <name> -n <namespace>```

**4. kubectl get pod | kubectl replace**

```kubectl get pod <pod_name> -n <namespace> -o yaml | kubectl replace --force -f -```

**Rollout Status**
```bash
kubectl rollout status deployment <DEPLOYMENT_NAME>
```

e.g.
```bash
kubectl rollout status deployment facctguard-frontend-deployment -n facctguard
```
output:
**deployment "facctguard-frontend-deployment" successfully rolled out**
