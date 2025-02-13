# Reducing Costs

* To effectively reduce costs in Kubernetes, consider optimizing resource allocation by right-sizing your workloads. Analyze the current usage patterns of your pods and nodes to identify opportunities for downsizing or terminating underutilized resources. Leverage autoscaling to dynamically adjust resources based on real-time demand, ensuring efficient use of infrastructure. Implement resource quotas and limits to prevent over-provisioning, and use cost visualization tools to gain insights into spending patterns. Regularly review and adjust your cloud provider settings to align with any negotiated pricing discounts available to you.
* Node metrics and views - Explanation of how container optimization prior to node optimization impacts costs
* Downsizing pods
* Downsizing/terminating nodes

A word about billing data and “true” costs&#x20;

Q. Are the CSP costs listed in the Densify Console, from customer-negotiated pricing with our CSP or standard list pricing?&#x20;

A. Densify Console pricing information is based on regional CSP cost data which Densify updates regularly. If you have a negotiated discount, that you want to apply please let your Densify Account Manager know and a global discount can be applied to values in the Densify Console. Cost information in the Densify Containers dashboards is a manually-configured cost per core and per GB of memory. Contact your Densify Account Manage if you want to update your configuration with different costs.
