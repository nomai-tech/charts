# Nomai Tech Helm Charts

This repository hosts the `web-app` Helm chart.

## Add the chart repository

Replace `CHART_REPO_URL` with the URL where this repository is published (for example a GitHub Pages URL).

```bash
helm repo add nomai-tech CHART_REPO_URL
helm repo update
```

## Install the chart

```bash
helm install my-web nomai-tech/web-app \
  --set image.name=your-registry/your-image:tag \
  --set ingress.host=example.com
```

## Upgrade the chart

```bash
helm upgrade my-web nomai-tech/web-app \
  --set image.name=your-registry/your-image:tag \
  --set ingress.host=example.com
```

## Values

Common values you may want to override:

- `image.name`: Container image to deploy.
- `image.pullPolicy`: Image pull policy. Default: `IfNotPresent`.
- `replicaCount`: Number of replicas. Default: `1`.
- `service.type`: Service type. Default: `ClusterIP`.
- `service.port`: Service port. Default: `80`.
- `containerPort`: Container port. Default: `80`.
- `ingress.enabled`: Enable ingress. Default: `true`.
- `ingress.host`: Primary host name for ingress.
- `ingress.className`: Ingress class name (optional).
- `ingress.annotations`: Extra ingress annotations.
- `ingress.hosts`: Advanced host/path configuration.
- `ingress.tls`: TLS configuration.

See `web-app/values.yaml` for the full set of defaults.
