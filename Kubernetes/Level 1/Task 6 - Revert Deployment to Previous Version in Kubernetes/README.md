## Revert Deployment to Previous Version in Kubernetes

### Description

Earlier today, the Nautilus DevOps team deployed a new release for an application. However, a customer has reported a bug related to this recent release. Consequently, the team aims to revert to the previous version.


There exists a deployment named nginx-deployment; initiate a rollback to the previous revision.

Note: The kubectl utility on the jump-host has been configured to work with the Kubernetes cluster.

---

Step 1: Check rollout history

```bash
kubectl rollout history deployment/nginx-deployment
```

Step 2: Roll back to the previous revision

```bash
kubectl rollout undo deployment/nginx-deployment
```

Step 3: Verify the rollback completed

```bash
kubectl rollout status deployment/nginx-deployment
```
You should see:
```bash
deployment "nginx-deployment" successfully rolled out
```

Step 4: Verify the pods

```bash
kubectl get pods
```
And confirm the deployment:
```bash
kubectl get deployment nginx-deployment
```
You should have all desired replicas READY and AVAILABLE.

--- 
Task Completed

