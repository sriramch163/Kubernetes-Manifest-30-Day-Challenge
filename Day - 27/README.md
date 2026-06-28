# Day 27 - Liveness and Readiness Probes

## Objective

Learn how Kubernetes checks whether a container is healthy and ready to receive traffic.

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

- Liveness Probe
- Readiness Probe
- Events

## View Pod Status

```bash
kubectl get pods -w
```

## Delete Deployment

```bash
kubectl delete -f deployment.yaml
```

## Concepts Learned

- Liveness Probe
- Readiness Probe
- Health Checks
- Container Status