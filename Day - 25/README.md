# Day 25 - CronJob

## Objective

Learn how to schedule recurring tasks using Kubernetes CronJobs.

## Files

- cronjob.yaml

## Create CronJob

```bash
kubectl apply -f cronjob.yaml
```

## Verify CronJob

```bash
kubectl get cronjobs
```

or

```bash
kubectl get cj
```

Expected:

```bash
NAME            SCHEDULE        SUSPEND
hello-cronjob   */1 * * * *     False
```

## Watch Jobs

After one minute:

```bash
kubectl get jobs
```

Expected:

```bash
NAME                          COMPLETIONS
hello-cronjob-xxxxxxxxxx      1/1
```

## View Pods

```bash
kubectl get pods
```

Each scheduled Job creates its own Pod.

## View Logs

Get the Pod name:

```bash
kubectl get pods
```

View logs:

```bash
kubectl logs <pod-name>
```

Expected:

```text
Fri Jun 26 ...
Hello from CronJob
```

## Describe CronJob

```bash
kubectl describe cronjob hello-cronjob
```

## Delete CronJob

```bash
kubectl delete -f cronjob.yaml
```

## Concepts Learned

- CronJob
- Scheduling
- Cron Expressions
- Job Automation