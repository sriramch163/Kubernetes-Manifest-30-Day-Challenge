# Day 05 - Deployment

## Objective

Learn how to create and manage a Deployment.

## Files

- `deployment.yaml` - Creates a Deployment with 3 Nginx Pods

## Create Deployment

```bash
kubectl apply -f deployment.yaml
```

## Verify Deployment

```bash
kubectl get deployments
```

Expected:

```bash
NAME               READY   UP-TO-DATE   AVAILABLE
nginx-deployment   3/3     3            3
```

## Verify ReplicaSet

```bash
kubectl get rs
```

Expected:

```bash
NAME                          DESIRED   CURRENT   READY
nginx-deployment-xxxxxxxxxx   3         3         3
```

## Verify Pods

```bash
kubectl get pods
```

Expected:

```bash
NAME                               READY   STATUS
nginx-deployment-xxxxxx-yyyyy      1/1     Running
nginx-deployment-xxxxxx-zzzzz      1/1     Running
nginx-deployment-xxxxxx-aaaaa      1/1     Running
```

## Describe Deployment

```bash
kubectl describe deployment nginx-deployment
```

Observe:

- Replicas
- Labels
- Pod Template
- Events

## Scale Deployment

```bash
kubectl scale deployment nginx-deployment --replicas=5
```

Verify:

```bash
kubectl get pods
```

Expected:

5 running Pods.

## Test Self-Healing

Delete a Pod:

```bash
kubectl delete pod <pod-name>
```

Verify:

```bash
kubectl get pods
```

A new Pod will be created automatically.

## View Deployment Details

```bash
kubectl get deployment nginx-deployment -o yaml
```

## Delete Deployment

```bash
kubectl delete -f deployment.yaml
```

## Concepts Learned

- Deployment
- ReplicaSet
- Pod Template
- Scaling
- Self-Healing
- Desired State