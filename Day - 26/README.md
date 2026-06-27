# Day 26 - Resource Requests and Limits

## Objective

Learn how to define CPU and memory requests and limits for containers.

## Files

- pod.yaml

## Create Pod

```bash
kubectl apply -f pod.yaml
```

## Verify Pod

```bash
kubectl get pods
```

Expected:

```bash
NAME              READY   STATUS
nginx-resources   1/1     Running
```

## Describe Pod

```bash
kubectl describe pod nginx-resources
```

Observe:

- CPU Requests
- CPU Limits
- Memory Requests
- Memory Limits

## View Pod YAML

```bash
kubectl get pod nginx-resources -o yaml
```

## Delete Pod

```bash
kubectl delete -f pod.yaml
```

## Concepts Learned

- Resource Requests
- Resource Limits
- CPU
- Memory
- Resource Management