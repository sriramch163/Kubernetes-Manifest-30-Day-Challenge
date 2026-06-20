# Day 19 - Pod with PersistentVolumeClaim

## Objective

Learn how a Pod uses persistent storage through a PersistentVolumeClaim.

## Files

- pv.yaml
- pvc.yaml
- pod.yaml

## Create PersistentVolume

```bash
kubectl apply -f pv.yaml
```

## Create PersistentVolumeClaim

```bash
kubectl apply -f pvc.yaml
```

Verify:

```bash
kubectl get pv,pvc
```

Expected:

```bash
my-pvc   Bound
```

## Create Pod

```bash
kubectl apply -f pod.yaml
```

Verify:

```bash
kubectl get pods
```

## Access Pod

```bash
kubectl exec -it pvc-pod -- sh
```

Create a file:

```bash
echo "hello kubernetes" > /data/test.txt
```

Verify:

```bash
cat /data/test.txt
```

Exit:

```bash
exit
```

## Delete Pod

```bash
kubectl delete pod pvc-pod
```

## Recreate Pod

```bash
kubectl apply -f pod.yaml
```

## Verify Data Persistence

```bash
kubectl exec -it pvc-pod -- sh
```

Check:

```bash
cat /data/test.txt
```

Expected:

```text
hello kubernetes
```

The data remains because it is stored on the PersistentVolume.

## Cleanup

```bash
kubectl delete -f pod.yaml
kubectl delete -f pvc.yaml
kubectl delete -f pv.yaml
```

## Concepts Learned

- PersistentVolume
- PersistentVolumeClaim
- Volume Mounts
- Persistent Storage
- Data Persistence