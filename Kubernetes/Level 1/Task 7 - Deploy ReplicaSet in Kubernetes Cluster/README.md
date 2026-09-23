## Deploy ReplicaSet in Kubernetes Cluster

### Description

The Nautilus DevOps team is gearing up to deploy applications on a Kubernetes cluster for migration purposes. A team member has been tasked with creating a ReplicaSet outlined below:



Create a ReplicaSet using nginx image with latest tag (ensure to specify as nginx:latest) and name it nginx-replicaset.


Apply labels: app as nginx_app, type as front-end.


Name the container nginx-container. Ensure the replica count is 4.


Note: The kubectl utility on the jump-host has been configured to work with the Kubernetes cluster.

---

Step 1: Create the manifest file

```bash
vim nginx-replicaset.yaml
```
Paste
```bash
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: nginx-replicaset
  labels:
    app: nginx_app
    type: front-end
spec:
  replicas: 4
  selector:
    matchLabels:
      app: nginx_app
      type: front-end
  template:
    metadata:
      labels:
        app: nginx_app
        type: front-end
    spec:
      containers:
        - name: nginx-container
          image: nginx:latest
```

Step 2: Apply the manifest
```bash
kubectl apply -f nginx-replicaset.yaml
```

Step 3 : Verify
```bash
kubectl get rs
```
Check the pods
```bash
kubectl get pods
```
Important: The labels in **spec.selector.matchLabels** must exactly match the labels in **spec.template.metadata.labels**; otherwise, the ReplicaSet won't manage the Pods correctly.

----
Task Completed
