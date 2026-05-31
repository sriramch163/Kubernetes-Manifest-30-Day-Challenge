# Day 01 - Pod

## Objective

Create a simple Nginx Pod and understand the basic structure of a Kubernetes manifest.

## Files

- `pod.yaml` - Creates an Nginx Pod

## Create Pod

```bash
kubectl apply -f pod.yaml
```

## Verify Pod

```bash
kubectl get pods
```

## Inspect Pod

```bash
kubectl describe pod nginx-pod
```

## View Labels

```bash
kubectl get pods --show-labels
```

## Access Application

```bash
kubectl port-forward pod/nginx-pod 8080:80
```

Open:

```text
http://localhost:8080
```

## Delete Pod

```bash
kubectl delete -f pod.yaml
```

## Concepts Learned

- Pod
- Labels
- Container Image
- Container Port
- kubectl apply
- kubectl get
- kubectl describe
- kubectl delete