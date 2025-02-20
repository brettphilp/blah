# Troubleshooting

[Troubleshooting](https://github.com/densify-dev/container-data-collection/blob/main/egress-requirements.md)

### Frequently Encountered Issues

* **User Credential vs. Service Credential**
  * It is recommended to use a Service Credential with the Densify Forwarder as User Credentials will have password timeouts/resets that would cause the Forwarder to fail.  Request a Service ID from support@densify.com.
* **Prometheus Not Setup Properly for Densify**
  * Review the pre-requisites for your desired approach to data collection
  * A detailed list of metrics (and their sources) is provided at [https://github.com/densify-dev/container-data-collection/tree/main/docs#prometheus-metrics](https://github.com/densify-dev/container-data-collection/tree/main/docs#prometheus-metrics)
  * Consider using the Helm - All In One Installation method as it will provide a Prometheus stack that includes are necessary components required for Densify.&#x20;
* **Proxy**
  * Some deployments may require the use of a proxy service to forward data back to Densify
  * Update the Proxy section of the configmap.yaml file and rerun the job &#x20;
* **Cluster Re-Paving**
  * Some deployments use devops processes such as cluster repaving to complete destroy the cluster and rebuild it from scratch via codified declarations - Densify's Data Forwarder will need to be part of that process or will be removed when repaving happens

