# Day 12 - Multiple Pods Behind a Service

## Objective

Learn how a Service routes traffic to multiple Pods.

## Files

- deployment.yaml
- service.yaml

## Apply Resources

```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

## Verify Deployment

```bash
kubectl get deployments
kubectl get pods
```

## Verify Service

```bash
kubectl get svc
kubectl describe svc nginx-service
```

## Verify Endpoints

```bash
kubectl get endpoints
```

## Concepts Learned

- Service
- Endpoints
- Load Balancing
- Labels
- Selectors