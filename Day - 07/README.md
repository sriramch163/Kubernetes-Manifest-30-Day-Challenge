# Day 07 - Rollbacks

## Objective

Learn how to rollback a Deployment to a previous version.

## Files

- `deployment.yaml` - Creates an Nginx Deployment

## Create Deployment

```bash
kubectl apply -f deployment.yaml
```

Verify:

```bash
kubectl get deployments
kubectl get pods
```

---

## Update Deployment

Change:

```yaml
image: nginx:1.27
```

To:

```yaml
image: nginx:1.28
```

Apply:

```bash
kubectl apply -f deployment.yaml
```

Verify rollout:

```bash
kubectl rollout status deployment/nginx-deployment
```

---

## View Rollout History

```bash
kubectl rollout history deployment/nginx-deployment
```

Expected:

```bash
REVISION  CHANGE-CAUSE
1
2
```

---

## Rollback Deployment

```bash
kubectl rollout undo deployment/nginx-deployment
```

Verify:

```bash
kubectl rollout status deployment/nginx-deployment
```

Expected:

```bash
deployment "nginx-deployment" successfully rolled out
```

---

## Verify Current Image

```bash
kubectl describe deployment nginx-deployment
```

or

```bash
kubectl get deployment nginx-deployment -o yaml
```

You should see:

```yaml
image: nginx:1.27
```

---

## Check ReplicaSets

```bash
kubectl get rs
```

Observe:

- Old ReplicaSet becomes active again
- New ReplicaSet scales down

---

## Delete Deployment

```bash
kubectl delete -f deployment.yaml
```

## Concepts Learned

- Deployment Revision
- Rollout History
- Rollback
- Revision Management
- ReplicaSet Recovery