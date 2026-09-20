## Kubernetes Namespace and Pod

### Description

The Nautilus DevOps team has noticed performance issues in some Kubernetes-hosted applications due to resource constraints. To address this, they plan to set limits on resource utilization. Here are the details:


Create a pod named httpd-pod with a container named httpd-container. Use the httpd image with the latest tag (specify as httpd:latest). Configure the following container-level resource requests and limits for the container:

Requests: Memory: 15Mi, CPU: 100m

Limits: Memory: 20Mi, CPU: 100m

Note: The kubectl utility on the jump-host has been configured to work with the Kubernetes cluster.

---
Step 1: Create the pod using this YAML

```bash
apiVersion: v1
kind: Pod
metadata:
  name: httpd-pod
spec:
  containers:
    - name: httpd-container
      image: httpd:latest
      resources:
        requests:
          memory: "15Mi"
          cpu: "100m"
        limits:
          memory: "20Mi"
          cpu: "100m"
```
Step 2: Apply the pod
```bash
kubectl apply -f pod.yaml
```
Step 3: Verify if the pod is running
```bash
kubectl get pod httpd-pod
```
---
Task Completed
