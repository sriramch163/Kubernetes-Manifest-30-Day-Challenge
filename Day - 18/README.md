# Day 18 - PersistentVolumeClaim (PVC)

## Objective

Learn how Pods request storage using PersistentVolumeClaims.

## Files

- pv.yaml
- pvc.yaml

## Create PersistentVolume

```bash
kubectl apply -f pv.yaml
```

Verify:

```bash
kubectl get pv
```

Expected:

```bash
NAME    CAPACITY
my-pv   1Gi
```

## Create PersistentVolumeClaim

```bash
kubectl apply -f pvc.yaml
```

Verify:

```bash
kubectl get pvc
```

Expected:

```bash
NAME     STATUS   VOLUME
my-pvc   Bound    my-pv
```

## Verify PV and PVC

```bash
kubectl get pv
kubectl get pvc
```

## Describe PVC

```bash
kubectl describe pvc my-pvc
```

Observe:

- Requested Storage
- Bound Volume
- Access Modes

## Delete Resources

```bash
kubectl delete -f pvc.yaml
kubectl delete -f pv.yaml
```

## Concepts Learned

- PersistentVolumeClaim
- Storage Requests
- PV Binding
- Storage Abstraction