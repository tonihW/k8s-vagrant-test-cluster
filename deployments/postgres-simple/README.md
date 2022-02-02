# postgres-simple

Very simple specification for deploying a single PostgreSQL 14 instance with a single PersistentVolumeClaim to a k8s cluster.

## Deployment / update

```bash
kubectl apply -f postgres-secret.yml
kubectl apply -f postgres-volume.yml
kubectl apply -f postgres-volume-claim.yml
kubectl apply -f postgres-deployment.yml
```

## Postgres CLI access

```bash
kubectl exec -it <postgres-pod-name> -- psql -U postgres
```

## Concepts

### Labels

https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/

### Secret

https://kubernetes.io/docs/concepts/configuration/secret/

### PersistentVolume

https://kubernetes.io/docs/concepts/storage/persistent-volumes/

### Deployment

https://kubernetes.io/docs/concepts/workloads/controllers/deployment/
