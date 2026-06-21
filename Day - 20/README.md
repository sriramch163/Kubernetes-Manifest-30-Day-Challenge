# Day 20 - StorageClass

## Objective

Learn how StorageClasses enable dynamic storage provisioning in Kubernetes.

## Files

- storageclass.yaml
- pvc.yaml

## View Existing StorageClasses

```bash
kubectl get storageclass
```

or

```bash
kubectl get sc
```

Expected:

```bash
NAME                 PROVISIONER
local-path (default) rancher.io/local-path
```

You may already have a default StorageClass depending on your cluster.

## Create StorageClass

```bash
kubectl apply -f storageclass.yaml
```

Verify:

```bash
kubectl get sc
```

## Create PVC

```bash
kubectl apply -f pvc.yaml
```

Verify:

```bash
kubectl get pvc
```

## Describe PVC

```bash
kubectl describe pvc dynamic-pvc
```

Observe:

- Requested Storage
- StorageClass
- Events

## Describe StorageClass

```bash
kubectl describe sc fast-storage
```

## Delete Resources

```bash
kubectl delete -f pvc.yaml
kubectl delete -f storageclass.yaml
```

## Concepts Learned

- StorageClass
- Dynamic Provisioning
- Provisioners
- PVC
- Storage Automation