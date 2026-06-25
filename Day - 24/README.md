# Day 24 - Job

## Objective

Learn how to run one-time tasks using Kubernetes Jobs.

## Files

- job.yaml

## Create Job

```bash
kubectl apply -f job.yaml
```

## Verify Job

```bash
kubectl get jobs
```

Expected:

```bash
NAME        COMPLETIONS   DURATION
hello-job   1/1           5s
```

## View Pods

```bash
kubectl get pods
```

Expected:

```bash
hello-job-xxxxx
```

## View Job Logs

Get Pod name:

```bash
kubectl get pods
```

View logs:

```bash
kubectl logs <pod-name>
```

Expected:

```text
Hello Kubernetes Job
```

## Describe Job

```bash
kubectl describe job hello-job
```

## Verify Completion

```bash
kubectl get jobs
```

Expected:

```bash
COMPLETIONS 1/1
```

## Delete Job

```bash
kubectl delete -f job.yaml
```

## Concepts Learned

- Job
- One-Time Execution
- Batch Processing
- Job Completion
- Job Pods