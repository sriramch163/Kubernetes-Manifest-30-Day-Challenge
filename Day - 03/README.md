# Day 03 - Namespace

## Objective

Learn how to create and use Kubernetes Namespaces to logically separate resources.

## Files

- `namespace.yaml` - Creates a Namespace named dev
- `pod.yaml` - Creates a Pod inside the dev Namespace

## Create Namespace

```bash
kubectl apply -f namespace.yaml
```

Verify:

```bash
kubectl get namespaces
```

## Create Pod

```bash
kubectl apply -f pod.yaml
```

## Verify Pod

Without namespace:

```bash
kubectl get pods
```

Expected:

```bash
No resources found in default namespace.
```

With namespace:

```bash
kubectl get pods -n dev
```

Expected:

```bash
NAME        READY   STATUS
nginx-pod   1/1     Running
```

## Describe Pod

```bash
kubectl describe pod nginx-pod -n dev
```

## View Resources in Namespace

```bash
kubectl get all -n dev
```

## Delete Pod

```bash
kubectl delete -f pod.yaml
```

## Delete Namespace

```bash
kubectl delete -f namespace.yaml
```

## Concepts Learned

- Namespace
- Resource Isolation
- Namespace Scoped Resources
- kubectl -n option