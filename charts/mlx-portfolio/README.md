# DDB Proxy

This is a chart that will deploy my [Portfolio Website](https://github.com/TheNightAngel17/portfolio) service to a kubernetes cluster.

# Overview

## Image

While in the documentaiton, it says to use the tag `latest`, I opted for a more controlled approach in the default values, ensuring that if you do use this, it will stick with the tag until you are ready to go. 

## Data and persistance

This service is a static website - no data nees to be persisted!

## Security Considerations

This exposes a non-TLS port for use. You will need to find a way to proxy connections to this service with TLS, be it nginx or traefik or some other system. Each implementer will want it their own way, I leave that to you.

# Deploying

As there's not much to configure, feel free to deploy this chart without any values.

```bash
helm repo add mlx-charts https://thenightangel17.github.io/helm-charts/
```

```bash
helm upgrade --install ddb-proxy mlx-charts/mlx-portfolio
```

If you wish to add values, feel free to pass them in.

```bash
helm upgrade --install ddb-proxy mlx-charts/mlx-portfolio -f my-values.yaml
```