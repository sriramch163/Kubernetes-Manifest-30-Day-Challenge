# Day 04 - ReplicaSet

## Objective

Learn how ReplicaSets maintain a desired number of Pod replicas.

## Files

- `replicaset.yaml` - Creates a ReplicaSet with 3 Nginx Pods

## Create ReplicaSet

```bash
kubectl apply -f replicaset.yaml
```

## Verify ReplicaSet

```bash
kubectl get rs
```

Expected:

```bash
NAME       DESIRED   CURRENT   READY
nginx-rs   3         3         3
```

## Verify Pods

```bash
kubectl get pods
```

Expected:

```bash
NAME             READY   STATUS
nginx-rs-xxxxx   1/1     Running
nginx-rs-yyyyy   1/1     Running
nginx-rs-zzzzz   1/1     Running
```

## Describe ReplicaSet

```bash
kubectl describe rs nginx-rs
```

Observe:

- Desired Replicas
- Current Replicas
- Pod Template
- Events

## Test Self-Healing

Delete one Pod:

```bash
kubectl delete pod <pod-name>
```

Example:

```bash
kubectl delete pod nginx-rs-xxxxx
```

Verify:

```bash
kubectl get pods
```

A new Pod should be created automatically.

## Scale ReplicaSet

Increase replicas:

```bash
kubectl scale rs nginx-rs --replicas=5
```

Verify:

```bash
kubectl get pods
```

You should now see 5 Pods.

## Delete ReplicaSet

```bash
kubectl delete -f replicaset.yaml
```

## Concepts Learned

- ReplicaSet
- Desired State
- Self-Healing
- Pod Replicas
- Label Selectors
- Scaling