# Identifying Waste

To effectively reduce waste in Kubernetes, consider optimizing resource allocation by right-sizing your workloads. Analyze the current usage patterns of your pods and nodes to identify opportunities for downsizing or terminating underutilized resources. Leverage autoscaling to dynamically adjust resources based on real-time demand, ensuring efficient use of infrastructure. Use cost visualization tools to gain insights into spending patterns. For public cloud hosted clusters, regularly review and adjust your provider settings to align with any negotiated pricing discounts available to you.

**Kubernetes waste and impacts include;**

* CPU or Memory Request too high (stranded resources)
* Cluster Scaling too high (too many nodes active)

> <mark style="background-color:blue;">TIP: Fix risks first then reduce waste</mark>

**Steps to Reduce Waste**

* Identify waste
  * Identify pod requests to set or reduce
  * Identify Namespace quotas to set or reduce?
  * Identify full or imbalanced nodes
  * Identify node group rescaling options&#x20;
  * Less nodes (scale down the cluster) - too many nodes are active due to full or imbalanced nodes



**A word about billing data and “true” costs**&#x20;

Public cloud CSP pricing information in Densify is based on regional CSP cost data which Densify updates regularly. If you have a negotiated discount, that you want to apply please let your Densify Account Manager know and a global discount can be applied to values in the Densify Console. Cost information in the Densify Containers dashboards is a manually-configured cost per core and per GB of memory. Contact your Densify Account Manage if you want to update your configuration with different costs.
