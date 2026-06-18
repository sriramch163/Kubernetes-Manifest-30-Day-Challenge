# Day 17 - hostPath Volume

## Objective

Learn how to mount node storage inside a Pod.

## Files

- pod.yaml

## Apply Resource

```bash
kubectl apply -f pod.yaml
```

## Verify Pod

```bash
kubectl get pods
```

## Access Pod

```bash
kubectl exec -it hostpath-pod -- sh
```

## Create Test File

```bash
echo hello > /host-data/test.txt
```

## Verify Node Storage

```bash
ls /tmp/k8s-data
```

## Concepts Learned

- hostPath
- Node Storage
- Persistent Files
- Volume Mounts