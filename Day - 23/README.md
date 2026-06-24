# Day 23 - Headless Service

## Objective

Learn how Headless Services provide direct DNS records for Pods instead of a ClusterIP.

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
kubectl get pods
```

Expected:

```bash
nginx-statefulset-0
nginx-statefulset-1
nginx-statefulset-2
```

## Verify DNS Records

Launch a test Pod:

```bash
kubectl run test-pod --image=busybox -it --rm -- sh
```

Inside the Pod:

```sh
nslookup nginx-headless
```

You should see multiple Pod IPs.

## Verify Individual Pod DNS

```sh
nslookup nginx-statefulset-0.nginx-headless
```

```sh
nslookup nginx-statefulset-1.nginx-headless
```

```sh
nslookup nginx-statefulset-2.nginx-headless
```

Each Pod has its own DNS entry.

## Delete Resources

```bash
kubectl delete -f statefulset.yaml
kubectl delete -f service.yaml
```

## Concepts Learned

- Headless Service
- DNS Discovery
- StatefulSet Networking
- Direct Pod Access