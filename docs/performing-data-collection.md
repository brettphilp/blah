# Performing Data Collection

Performing Data Collection

**Performing Data Collection**

\#990030

Data collection must be performed to collect the necessary configuration and utilization data from each of your environments. Data collection can be configured for the both cloud and container environments.

A number of resources are available to support planning for data collection activities. Contact \[email protected] for additional information.

Containers

Use the data forwarder to collect and send your container metrics from Prometheus to your Densify instance for analysis. You can configure the data forwarder for:

* [Single Cluster](about:blank/Data_Collection_for_Public_Cloud_Systems/Container_Data_Collection_Overview.htm#Single)—In this configuration data is collected from a single Kubernetes cluster. The data forwarder is deployed inside the cluster.
* [Multiple Clusters](about:blank/Data_Collection_for_Public_Cloud_Systems/Container_Data_Collection_Overview.htm#Multiple)—In this configuration data is collected from multiple Kubernetes clusters that are monitored by Prometheus or a supported observability platform. The data forwarder does not need to be within the cluster but must have access Prometheus or the observability platform

See Container Data Collection Prerequisites before deploying the data forwarder.

Public Cloud

Refer to the following prerequisites to configure a user account that can then be used for data collection:

* AWS Data Collection Using a CloudFormation Template. Densify's CloudFormation template automates the process.
* AWS Data Collection Prerequisites for an IAM Role (CloudWatch only).
* Microsoft Azure Data Collection Prerequisites
* Google Cloud Platform Data Collection Prerequisites

Use the Cloud Connections wizard to create the connection directly to your cloud environments to collect workload and configuration data.

API

Allows you to create cloud connections, collect and analyze workload data from supported public cloud providers. Refer to the [API documentation](https://www.densify.com/docs-api/WebHelp_Densify_API_Cloud/Content/APIHome_Cloud.htm) for details.
