# Manual Prometheus

## Pre-Requisites

*   The following software is required for Densify container data collection and optimization.

    1. Kubernetes or OpenShift must be deployed.
       1. Running cAdvisor as part of the kubelet provides the workload and configuration data required by Densify.
    2. kube-state-metrics—This service monitors the Kubernetes API server and generates metrics from the various objects inside the individual Kubernetes components. This service provides orchestration and cluster level metrics such as deployments, pod metrics, resource reservation, etc. The collected metrics allow Densify to get a complete picture of how your containers are setup i.e. Replica Sets, Deployments, Pod and Container Labels.
    3.
       * Requires v1.5.0 or later. See [additional considerations](https://www.densify.com/docs/WebHelp_Densify_Cloud/Content/Data_Collection_for_Public_Cloud_Systems/Container_Data_Collection_Additional_Considerations.htm#ksm2x) when using v2.x.
       * [https://github.com/kubernetes/kube-state-metrics](https://github.com/kubernetes/kube-state-metrics)
    4. Prometheus or supported observability platform—Collects metrics from configured targets at given intervals. It provides the monitoring/data aggregation layer. It must be deployed and configured to collect kube-state-metrics and cAdvisor/kubelet metrics. See [additional considerations](https://www.densify.com/docs/WebHelp_Densify_Cloud/Content/Data_Collection_for_Public_Cloud_Systems/Container_Data_Collection_Additional_Considerations.htm#ObsPlat) when using an observability platform.
    5.
       * [https://prometheus.io](https://prometheus.io/)
    6. When deploying Prometheus and kube-state-metrics using a standard operator, some of the metrics that Densify needs for analysis may be excluded (i.e. on a deny list). Refer to [Prometheus-Data](https://github.com/densify-dev/container-data-collection/tree/main/docs) for details of the list of metrics that Densify requires for analysis.
    7. Node Exporter—This is an agent deployed on every node to collect data about the nodes, on which the containers are running. This provides host-related metrics such as CPU, memory, network, etc.
    8.
       * [https://github.com/prometheus/node\_exporter](https://github.com/prometheus/node_exporter)

    The following item is not mandatory but provides additional environment information for Densify's container optimization analysis, .

    6. Openshift-state-metrics—Expands upon kube-state-metrics by adding metrics for OpenShift-specific resources and provides additional details such as Cluster Resource Quotas (CRQ).
    7.
       * [https://github.com/openshift/openshift-state-metrics](https://github.com/openshift/openshift-state-metrics)
    8. The data forwarder is only supported on Linux OS and x64 architecture.

    After deploying the data forwarder, contact Support@Densify.com to enable your Densify instance with container optimization.

## Troubleshooting

*
