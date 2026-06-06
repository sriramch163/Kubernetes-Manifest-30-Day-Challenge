# Day 06 - Rolling Updates

## Objective

Learn how Kubernetes performs rolling updates when a Deployment is modified.

## Files

- `deployment.yaml` - Deployment running Nginx

## Create Deployment

```bash
kubectl apply -f deployment.yaml
```

## Verify Deployment

```bash
kubectl get deployment
```

## Verify ReplicaSet

```bash
kubectl get rs
```

## Verify Pods

```bash
kubectl get pods
```

---

## Update the Image

Edit deployment.yaml

Change:

```yaml
image: nginx:1.27
```

To:

```yaml
image: nginx:1.28
```

Apply the changes:

```bash
kubectl apply -f deployment.yaml
```

---

## Watch the Rollout

```bash
kubectl rollout status deployment/nginx-deployment
```

Expected:

```bash
deployment "nginx-deployment" successfully rolled out
```

---

## Watch Pods

Open another terminal:

```bash
kubectl get pods -w
```

Observe:

- New Pods are created
- Old Pods are terminated gradually
- Application remains available

---

## Observe ReplicaSets

```bash
kubectl get rs
```

Expected:

```bash
NAME                         DESIRED
nginx-deployment-old-rs      0
nginx-deployment-new-rs      3
```

Notice that a new ReplicaSet was created.

---

## Deployment History

```bash
kubectl rollout history deployment/nginx-deployment
```

---

## Delete Deployment

```bash
kubectl delete -f deployment.yaml
```

## Concepts Learned

- Rolling Update
- Zero Downtime Deployment
- Rollout Status
- Deployment History
- ReplicaSet Replacement