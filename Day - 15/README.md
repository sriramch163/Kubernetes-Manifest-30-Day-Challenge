# Day 15 - ConfigMap and Secret

## Objective

Learn how ConfigMaps and Secrets work together in an application.

## Files

- configmap.yaml
- secret.yaml
- pod.yaml

## Apply Resources

```bash
kubectl apply -f configmap.yaml
kubectl apply -f secret.yaml
kubectl apply -f pod.yaml
```

## Verify Resources

```bash
kubectl get configmap
kubectl get secret
kubectl get pods
```

## Verify Environment Variables

```bash
kubectl exec app-pod -- env
```

## Concepts Learned

- ConfigMap
- Secret
- Application Configuration
- Secure Configuration