# Detecting Waste

To effectively reduce waste in Kubernetes, consider optimizing resource allocation by right-sizing your workloads. Analyze the current usage patterns of your pods and nodes to identify opportunities for downsizing or terminating underutilized resources. Leverage autoscaling to dynamically adjust resources based on real-time demand, ensuring efficient use of infrastructure. Use cost visualization tools to gain insights into spending patterns. For public cloud hosted clusters, regularly review and adjust your provider settings to align with any negotiated pricing discounts available to you.

**Kubernetes waste and causes include;**

* Stranded Resource - CPU or Memory Request too high or not set
* Too Many Nodes Active - Cluster Scaling too high&#x20;

## **Steps to Detect Waste** ![](<../.gitbook/assets/image (1) (1) (1) (1) (1).png>)

### Detect pod unset requests or reduce requests

Select a group of systems then examine the histogram to determine if the CPU or Memory Requests are too high (yellow).



<mark style="background-color:yellow;">\*</mark><mark style="background-color:yellow;">**EDITING**</mark><mark style="background-color:yellow;">\*</mark>

Click on the blue headers to drill into those impacted pods. Here we've gone into the "Memory Request Surplus" group of pods with to examine the waste.

&#x20;

### Detect full or imbalanced nodes

[https://www.densify.com/docs-kubex/Content/Kubex/Node%20Group%20Capacity%20View.htm](https://www.densify.com/docs-kubex/Content/Kubex/Node%20Group%20Capacity%20View.htm)

### Detect node group rescaling options&#x20;

[https://www.densify.com/docs-kubex/Content/Kubex/Node%20Group%20Capacity%20View.htm](https://www.densify.com/docs-kubex/Content/Kubex/Node%20Group%20Capacity%20View.htm)

### Less nodes (scale down the cluster) - too many nodes are active due to full or imbalanced nodes

[https://www.densify.com/docs/WebHelp\_Densify\_Cloud/Content/Densify\_Com/Working\_with\_ASGs.htm?Highlight=asg](https://www.densify.com/docs/WebHelp_Densify_Cloud/Content/Densify_Com/Working_with_ASGs.htm?Highlight=asg)

### Detect Namespace quotas to set or reduce?

\*Coming soon
