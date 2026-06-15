# Day 14 - Secret

## Objective

Learn how to store sensitive information using Kubernetes Secrets.

## Files

- secret.yaml
- pod.yaml

## Apply Resources

```bash
kubectl apply -f secret.yaml
kubectl apply -f pod.yaml
```

## Verify Secret

```bash
kubectl get secrets
kubectl describe secret app-secret
```

## Verify Environment Variables

```bash
kubectl exec secret-pod -- env
```

## Concepts Learned

- Secret
- Sensitive Data
- Base64 Encoding
- Environment Variables