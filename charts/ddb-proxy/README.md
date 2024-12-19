# DDB Proxy

This is a chart that will deploy [MrPrimate's ddb-proxy](https://github.com/MrPrimate/ddb-proxy) service to a kubernetes cluster.

>**NOTE**: This is a free version of his service, so some functionality is stripped out, understandably so. Please read his documention page on his repo for more information. I'm just providing a way to deploy this service in kubernetes.

# Overview

From the servic's main repo page, you can find a link to [running this service in docker](https://github.com/MrPrimate/ddb-proxy/blob/main/docker/README.md). That game me the thought of why not just shove it into a simple chart, and that's what this is.

## Image

While in the documentaiton, it says to use the tag `latest`, I opted for a more controlled approach in the default values, ensuring that if you do use this, it will stick with the tag until you are ready to go. 

## Data and persistance

This service is not really ment to be a persistable service. It's a proxy between FoundryVTT and D&D Beyond. If the service goes down and comes back up with no data, that's perfectly fine.

## Security Considerations

This exposes a non-TLS port for use. You will need to find a way to proxy connections to this service with TLS, be it nginx or traefik or some other system. Each implementer will want it their own way, I leave that to you.

>**NOTE**: you ***WILL*** need to proxy this for TLS/HTTPS. I cannoot find a direct link to documentation at this moment, but if it isn't a "localhost" connection, it will need to be TLS/HTTPS.

# Deploying

As there's not much to configure, feel free to deploy this chart without any values.

```bash
helm repo add mlx-charts https://thenightangel17.github.io/helm-charts/
```

```bash
helm upgrade --install ddb-proxy mlx-charts/ddb-proxy
```

If you wish to add values, feel free to pass them in.

```bash
helm upgrade --install ddb-proxy mlx-charts/ddb-proxy -f my-values.yaml
```