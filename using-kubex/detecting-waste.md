# Eliminate Waste

### **Steps to Eliminate Waste** ![](<../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png>)

To effectively reduce waste in Kubernetes, consider optimizing resource allocation by right-sizing your workloads. Analyze the current usage patterns of your pods and nodes to identify opportunities for downsizing or terminating underutilized resources.&#x20;

Generally you pay for node resources so it follows that if you run on less nodes then you will pay less cost.   Some clusters are small (2-3 nodes) and designed for specific purposes and not the best targets for waste reduction.  Instead we focus on the larger (and typically more general purpose) clusters to detect waste.&#x20;

Leverage autoscaling to dynamically adjust resources based on real-time demand, ensuring efficient use of infrastructure. Use cost visualization tools to gain insights into spending patterns. For public cloud hosted clusters, regularly review and adjust your provider settings to align with any negotiated pricing discounts available to you.

**Kubernetes waste and causes include;**

* Stranded Resource - CPU or Memory Request too high or not set
* Too Many Nodes Active - Cluster Scaling too high&#x20;

For each of the waste item recommendations are available for actioning. &#x20;

Most waste can be handled by setting container resource request and / or limit settings based on actual historical usage data.  The recommendations to set or adjust these settings are found on the container details screen. &#x20;

Here we show the Namespace level for a group of containers with memory request recommendations (downsize in this case to reduce waste).

<figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

From here customers often find it helpful to extract or publish these recommendations to internal users.  FinOps practitioners refer to this stage as socializing or campaigning of the optimization recommendations. &#x20;

Extraction can be accomplished via the extract widget in the UI and publishing to third party BI tool can be accomplished via the [Densify API.](../api-and-automation/)

Once application owners are in agreement to action, the recommendations can then be adopted through desired [DevOps or GitOps workflows](../api-and-automation/automation/) as per usual change operations.
