# Day 02 - Multi-Container Pod

## Objective

Learn how multiple containers can run inside a single Kubernetes Pod.

## Files

- `pod.yaml` - Creates a Pod with two containers

## Create Pod

```bash
kubectl apply -f pod.yaml
```

## Verify Pod

```bash
kubectl get pods
```

Expected:

```bash
NAME                  READY   STATUS
multi-container-pod   2/2     Running
```

## View Containers in Pod

```bash
kubectl describe pod multi-container-pod
```

Observe:

- nginx container
- busybox container

## View Logs

Nginx container:

```bash
kubectl logs multi-container-pod -c nginx
```

BusyBox container:

```bash
kubectl logs multi-container-pod -c busybox
```

## Access Container Shell

BusyBox:

```bash
kubectl exec -it multi-container-pod -c busybox -- sh
```

## Verify Containers Can Communicate

Inside BusyBox:

```bash
wget -qO- http://localhost
```

Expected:

Nginx HTML page.

This works because both containers share the same network namespace inside the Pod.

## Delete Pod

```bash
kubectl delete -f pod.yaml
```

## Concepts Learned

- Multi-Container Pod
- Container Communication
- Shared Network Namespace
- kubectl exec
- kubectl logs -c