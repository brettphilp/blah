# Detecting Waste

To effectively reduce waste in Kubernetes, consider optimizing resource allocation by right-sizing your workloads. Analyze the current usage patterns of your pods and nodes to identify opportunities for downsizing or terminating underutilized resources. Leverage autoscaling to dynamically adjust resources based on real-time demand, ensuring efficient use of infrastructure. Use cost visualization tools to gain insights into spending patterns. For public cloud hosted clusters, regularly review and adjust your provider settings to align with any negotiated pricing discounts available to you.

**Kubernetes waste and causes include;**

* Stranded Resource - CPU or Memory Request too high or unset
* Too Many Nodes Active - Cluster Scaling too high&#x20;

## **Steps to Detect Waste** ![](<../.gitbook/assets/image (1) (1) (1) (1) (1).png>)

### Detect pod unset requests or reduce requests

Select a group of systems then examine the histogram to determine if the CPU Requests or Limits are too high (yellow), or not set (gray).

\***EDITING**\*

Click on the blue headers to drill into those impacted pods. Here we've gone into the "CPU Request Shortfall" group of risky pods to examine the risks.



### Detect Namespace quotas to set or reduce?

### Detect full or imbalanced nodes

* [https://www.densify.com/docs-kubex/Content/Kubex/Node%20Group%20Analysis.htm](https://www.densify.com/docs-kubex/Content/Kubex/Node%20Group%20Analysis.htm)

### Detect node group rescaling options&#x20;

### Less nodes (scale down the cluster) - too many nodes are active due to full or imbalanced nodes
