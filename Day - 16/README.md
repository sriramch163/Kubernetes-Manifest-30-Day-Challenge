# Day 16 - emptyDir Volume

## Objective

Learn how Pods use temporary storage with emptyDir volumes.

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
kubectl exec -it emptydir-pod -- sh
```

## Create Test File

```bash
echo hello > /data/test.txt

cat /data/test.txt
```

## Concepts Learned

- Volumes
- emptyDir
- Temporary Storage
- Volume Mounts