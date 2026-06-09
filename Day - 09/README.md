# Day 09 - NodePort Service

## Objective

Learn how to expose an application outside the Kubernetes cluster using a NodePort Service.

## Files

- deployment.yaml
- service.yaml

## Create Deployment

```bash
kubectl apply -f deployment.yaml
```

Verify:

```bash
kubectl get deployments
kubectl get pods
```

## Create Service

```bash
kubectl apply -f service.yaml
```

Verify:

```bash
kubectl get svc
```

Expected:

```bash
NAME             TYPE       CLUSTER-IP      PORT(S)
nginx-nodeport   NodePort   10.x.x.x        80:30080/TCP
```

## Describe Service

```bash
kubectl describe svc nginx-nodeport
```

Observe:

- Type
- ClusterIP
- NodePort
- Endpoints

## Get Node IP

```bash
kubectl get nodes -o wide
```

Example:

```bash
INTERNAL-IP
192.168.1.100
```

## Access Application

Open:

```text
http://192.168.1.100:30080
```

Expected:

```text
Welcome to nginx!
```

## Verify Endpoints

```bash
kubectl get endpoints
```

## Delete Resources

```bash
kubectl delete -f service.yaml
kubectl delete -f deployment.yaml
```

## Concepts Learned

- NodePort
- External Access
- Service Types
- ClusterIP
- TargetPort
- NodePort