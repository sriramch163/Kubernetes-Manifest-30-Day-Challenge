# Day 08 - ClusterIP Service

## Objective

Learn how a Service provides a stable endpoint for Pods.

## Files

- deployment.yaml
- service.yaml

## Create Deployment

```bash
kubectl apply -f deployment.yaml
```

Verify:

```bash
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
NAME            TYPE        CLUSTER-IP
nginx-service   ClusterIP   10.x.x.x
```

## View Service Details

```bash
kubectl describe svc nginx-service
```

Observe:

- Selector
- Cluster IP
- Endpoints

## View Endpoints

```bash
kubectl get endpoints
```

Expected:

```bash
NAME            ENDPOINTS
nginx-service   <pod-ip>:80,...
```

## Test Service

Start a temporary Pod:

```bash
kubectl run test-pod --image=busybox -it --rm -- sh
```

Inside the Pod:

```sh
wget -qO- http://nginx-service
```

Expected:

```html
Welcome to nginx!
```

## Verify DNS

Inside BusyBox:

```sh
nslookup nginx-service
```

## Delete Resources

```bash
kubectl delete -f service.yaml
kubectl delete -f deployment.yaml
```

## Concepts Learned

- Service
- ClusterIP
- Service Discovery
- DNS
- Selectors
- Endpoints