# Day 21 - DaemonSet

## Objective

Learn how DaemonSets automatically run one Pod on every node in a Kubernetes cluster.

## Files

- daemonset.yaml

## Create DaemonSet

```bash
kubectl apply -f daemonset.yaml
```

## Verify DaemonSet

```bash
kubectl get daemonsets
```

Expected:

```bash
NAME              DESIRED   CURRENT   READY
nginx-daemonset   1         1         1
```

In a multi-node cluster:

```bash
NAME              DESIRED   CURRENT   READY
nginx-daemonset   3         3         3
```

## View Pods

```bash
kubectl get pods -o wide
```

Observe:

- One Pod per node

## View Nodes

```bash
kubectl get nodes
```

Compare:

- Number of Nodes
- Number of DaemonSet Pods

They should match.

## Describe DaemonSet

```bash
kubectl describe daemonset nginx-daemonset
```

## Delete DaemonSet

```bash
kubectl delete -f daemonset.yaml
```

## Concepts Learned

- DaemonSet
- Node-Level Pods
- Cluster Agents
- Logging Agents
- Monitoring Agents