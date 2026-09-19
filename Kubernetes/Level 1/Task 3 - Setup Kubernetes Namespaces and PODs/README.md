## Kubernetes Namespace and Pod

### Description

The Nautilus DevOps team is planning to deploy some micro services on Kubernetes platform. The team has already set up a Kubernetes cluster and now they want to set up some namespaces, deployments etc. Based on the current requirements, the team has shared some details as below:


Create a namespace named dev and deploy a POD within it. Name the pod dev-nginx-pod and use the nginx image with the latest tag. Ensure to specify the tag as nginx:latest.

Note: The kubectl utility on the jump-host has been configured to work with the Kubernetes cluster.

---
Step 1: Verify the current namespace in the cluster
```bash
kubectl get ns
```
You should see something similar
```bash
thor@jump-host ~$ kubectl get ns
NAME              STATUS   AGE
default           Active   90m
kube-node-lease   Active   90m
kube-public       Active   90m
kube-system       Active   90m
```
Step 2: Create the namespace as per the requirement
```bash
kubectl apply -f namespace.yaml
```
The manifest file for namespace.yaml is created in the same folder.

Once the manifest file is applied, you will see the created namespace.

Step 3: Create the pod as per the requirement
```bash
kubectl apply -f pod.yaml
```
The manifest file for pod.yaml is created in the same folder.

Step 4: Verify if the pod is running
```bash
kubectl get pods -n dev
```
You should see something similar
```bash
NAME            READY   STATUS    RESTARTS   AGE
dev-nginx-pod   1/1     Running   0          9s
```
--- 
Task Completed
