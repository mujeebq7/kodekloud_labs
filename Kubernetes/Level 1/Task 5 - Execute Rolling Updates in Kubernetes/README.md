## Execute Rolling Updates in Kubernetes

### Description

An application currently running on the Kubernetes cluster employs the nginx web server. The Nautilus application development team has introduced some recent changes that need deployment. They've crafted an image nginx:1.18 with the latest updates.


Execute a rolling update for this application, integrating the nginx:1.18 image. The deployment is named nginx-deployment.

Ensure all pods are operational post-update.

Note: The kubectl utility on the jump-host has been configured to work with the Kubernetes cluster.

---

Step 1: Verify the existing pods/deployments in the cluster

```bash
kubectl get all
```

You should see something similar

```bash
NAME                                   READY   STATUS    RESTARTS   AGE
pod/nginx-deployment-fc677cbc9-cqrl8   1/1     Running   0          3m52s
pod/nginx-deployment-fc677cbc9-jdmmc   1/1     Running   0          3m52s
pod/nginx-deployment-fc677cbc9-p9ssh   1/1     Running   0          3m52s

NAME                    TYPE        CLUSTER-IP     EXTERNAL-IP   PORT(S)        AGE
service/kubernetes      ClusterIP   10.43.0.1      <none>        443/TCP        3h43m
service/nginx-service   NodePort    10.43.17.165   <none>        80:30008/TCP   3m52s

NAME                               READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/nginx-deployment   3/3     3            3           3m52s
```

Step 2: Verify the current version of nginx image

```bash
kubectl describe pod pod/nginx-deployment-fc677cbc9-cqrl8
```

Step 3: Update the nginx image

```bash
kubectl set image deployment/nginx-deployment nginx-container=nginx:1.18
```

Step 4: Monitor the rollout

```bash
kubectl rollout status deployment/nginx-deployment
```
You should see something similar to:

```bash
deployment "nginx-deployment" successfully rolled out
```

Step 5: Verify all pods are running
```bash
kubectl get pods
```
check the updated nginx image
```bash
kubectl describe pod nginx-deployment-79b79679fc-bflhg
```
This performs a rolling update, rather than deleting all existing pods at once.

---

Task Completed

