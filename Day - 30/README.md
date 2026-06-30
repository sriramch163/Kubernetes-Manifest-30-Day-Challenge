# Day 30 - Production-Style Kubernetes Application

## Objective

Deploy a production-style application using multiple Kubernetes resources together.

## Files

- namespace.yaml
- configmap.yaml
- secret.yaml
- pvc.yaml
- deployment.yaml
- service.yaml

## Create Namespace

```bash
kubectl apply -f namespace.yaml
```

## Deploy Resources

```bash
kubectl apply -f configmap.yaml
kubectl apply -f secret.yaml
kubectl apply -f pvc.yaml
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

## Verify Resources

```bash
kubectl get all -n production
```

Verify ConfigMap:

```bash
kubectl get configmap -n production
```

Verify Secret:

```bash
kubectl get secret -n production
```

Verify PVC:

```bash
kubectl get pvc -n production
```

Describe Deployment:

```bash
kubectl describe deployment nginx-app -n production
```

View Service:

```bash
kubectl get svc -n production
```

Delete Resources:

```bash
kubectl delete namespace production
```

## Concepts Learned

- Namespace
- ConfigMap
- Secret
- PersistentVolumeClaim
- Deployment
- Service
- Resource Requests & Limits
- Liveness Probe
- Readiness Probe