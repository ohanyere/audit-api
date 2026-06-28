# Runbook

## Service

- Name: `audit-api`
- Team: `Developer Experience`
- Owner: `mooref068@gmail.com`
- Cost center: `developer-experience`

## First Checks

```bash
kubectl get rollout audit-api -n audit-api-dev
kubectl get pods -l app.kubernetes.io/name=audit-api -n audit-api-dev
kubectl logs -l app.kubernetes.io/name=audit-api -n audit-api-dev
```

## Health

```bash
curl https://audit-api.dev.platform.ohanyere.internal/healthz
curl https://audit-api.dev.platform.ohanyere.internal/readyz
curl https://audit-api.dev.platform.ohanyere.internal/livez
```

## Rollback

```bash
kubectl argo rollouts undo audit-api -n audit-api-dev
```

Escalate to `Developer Experience` through `mooref068@gmail.com` if rollback does not restore service.
