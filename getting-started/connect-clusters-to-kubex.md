# Connect Clusters to Kubex

Decide if you will host the data forwarder in your local image repository or reference the public image

If you're required to host container images via an intranet repository then the Docker image is available on Docker hub.&#x20;

Pull it using

```
docker pull densify/container-optimization-data-forwarder:4
```

The data forwarder is  supported on Linux OS and x64 architectures

[Detailed Requirements](https://github.com/densify-dev/container-data-collection/blob/main/requirements.md)

[Egress Requirements](https://github.com/densify-dev/container-data-collection/blob/main/egress-requirements.md)

Helm - "All in One Install"

* Helm is required (compatible with k8s 1.32)
* [https://github.com/densify-dev/helm-charts/tree/master/charts/kubex-automation-stack](https://github.com/densify-dev/helm-charts/tree/master/charts/kubex-automation-stack)
