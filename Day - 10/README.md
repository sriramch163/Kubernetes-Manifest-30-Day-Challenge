# Day 10 - LoadBalancer Service

## Objective

Learn how to expose applications using a LoadBalancer Service.

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

## Create LoadBalancer Service

```bash
kubectl apply -f service.yaml
```

Verify:

```bash
kubectl get svc
```

Expected (Cloud Environment):

```bash
NAME                 TYPE           EXTERNAL-IP
nginx-loadbalancer   LoadBalancer   34.xx.xx.xx
```

## Describe Service

```bash
kubectl describe svc nginx-loadbalancer
```

Observe:

- Service Type
- External IP
- Endpoints
- Port Mappings

## Access Application

Open:

```text
http://<EXTERNAL-IP>
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

- LoadBalancer Service
- External IP
- Cloud Integration
- Traffic Routing
- Endpoints