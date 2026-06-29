# Day 29 - Init Containers

## Objective

Learn how Init Containers perform setup tasks before the main application starts.

## Files

- pod.yaml

## Create Pod

```bash
kubectl apply -f pod.yaml
```

## Watch Pod Status

```bash
kubectl get pods -w
```

Observe:

```text
Init:0/1
```

After about 10 seconds:

```text
Running
```

## Describe Pod

```bash
kubectl describe pod init-container-pod
```

Observe:

- Init Containers
- Main Container
- Events

## View Init Container Logs

```bash
kubectl logs init-container-pod -c init-message
```

Expected:

```text
Initializing application...
```

## View Main Container Logs

```bash
kubectl logs init-container-pod -c nginx
```

## Delete Pod

```bash
kubectl delete -f pod.yaml
```

## Concepts Learned

- Init Container
- Sequential Startup
- Container Initialization
- Pod Lifecycle