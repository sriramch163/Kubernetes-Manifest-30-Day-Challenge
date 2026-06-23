# Day 22 - StatefulSet

## Objective

Learn how StatefulSets provide stable identities for stateful applications.

## Files

- service.yaml
- statefulset.yaml

## Create Headless Service

```bash
kubectl apply -f service.yaml
```

Verify:

```bash
kubectl get svc
```

Expected:

```bash
NAME             TYPE        CLUSTER-IP
nginx-headless   ClusterIP   None
```

## Create StatefulSet

```bash
kubectl apply -f statefulset.yaml
```

Verify:

```bash
kubectl get statefulsets
```

Expected:

```bash
NAME                 READY
nginx-statefulset    3/3
```

## View Pods

```bash
kubectl get pods
```

Expected:

```bash
nginx-statefulset-0
nginx-statefulset-1
nginx-statefulset-2
```

Observe:

The pod names remain stable.

## Scale StatefulSet

```bash
kubectl scale statefulset nginx-statefulset --replicas=5
```

Verify:

```bash
kubectl get pods
```

Expected:

```bash
nginx-statefulset-0
nginx-statefulset-1
nginx-statefulset-2
nginx-statefulset-3
nginx-statefulset-4
```

## Scale Down

```bash
kubectl scale statefulset nginx-statefulset --replicas=2
```

Observe:

Pods are removed in reverse order.

## Delete Resources

```bash
kubectl delete -f statefulset.yaml
kubectl delete -f service.yaml
```

## Concepts Learned

- StatefulSet
- Stable Pod Names
- Ordered Scaling
- Stateful Applications
- Headless Service