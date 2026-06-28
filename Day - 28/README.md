# Day 28 - Startup Probe

## Objective

Learn how Startup Probes prevent Kubernetes from restarting slow-starting applications.

## Files

- deployment.yaml

## Create Deployment

```bash
kubectl apply -f deployment.yaml
```

## Verify Deployment

```bash
kubectl get deployments
kubectl get pods
```

## Describe Pod

```bash
kubectl describe pod <pod-name>
```

Observe:

- Startup Probe
- Readiness Probe
- Liveness Probe

## Watch Pod Status

```bash
kubectl get pods -w
```

## Delete Deployment

```bash
kubectl delete -f deployment.yaml
```

## Concepts Learned

- Startup Probe
- Slow Application Startup
- Health Checks
- Container Initialization