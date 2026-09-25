## Schedule Cronjobs in Kubernetes

### Description

The Nautilus DevOps team is setting up recurring tasks on different schedules. Currently, they're developing scripts to be executed periodically. To kickstart the process, they're creating cron jobs in the Kubernetes cluster with placeholder commands. Follow the instructions below:



Create a cronjob named datacenter.


Set Its schedule to something like */11 * * * *. You can set any schedule for now.


Name the container cron-datacenter.


Utilize the httpd image with latest tag (specify as httpd:latest).


Execute the dummy command echo Welcome to xfusioncorp!.


Ensure the restart policy is OnFailure.


Note: The kubectl utility on the jump-host has been configured to work with the Kubernetes cluster.

---

Step 1: Create the CronJob manifest file

```bash
apiVersion: batch/v1
kind: CronJob
metadata:
  name: datacenter
spec:
  schedule: "*/11 * * * *"
  jobTemplate:
    spec:
      template:
        spec:
          containers:
            - name: cron-datacenter
              image: httpd:latest
              command:
                - /bin/sh
                - -c
                - echo Welcome to xfusioncorp!
          restartPolicy: OnFailure
```
Step 2: Apply the manifest

```bash
kubectl apply -f cronjob.yaml
```

Step 3 : Verify
```bash
kubectl get cronjob
```
You should see something similar
```bash
NAME         SCHEDULE       TIMEZONE   SUSPEND   ACTIVE   LAST SCHEDULE   AGE
datacenter   */11 * * * *   <none>     False     0        <none>          18s
```
---
Task Completed
