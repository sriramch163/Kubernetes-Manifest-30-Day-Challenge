# Day 13 - ConfigMap

## Objective

Learn how to store non-sensitive configuration outside application containers.

## Files

- configmap.yaml
- pod.yaml

## Apply Resources

```bash
kubectl apply -f configmap.yaml
kubectl apply -f pod.yaml
```

## Verify ConfigMap

```bash
kubectl get configmap
kubectl describe configmap app-config
```

## Verify Environment Variables

```bash
kubectl exec configmap-pod -- env
```

## Concepts Learned

- ConfigMap
- Environment Variables
- External Configuration