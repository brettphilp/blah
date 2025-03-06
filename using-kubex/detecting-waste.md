# Eliminate Waste

To effectively reduce waste in Kubernetes, consider optimizing resource allocation by right-sizing your workloads. Analyze the current usage patterns of your pods and nodes to identify opportunities for downsizing or terminating underutilized resources.&#x20;

Generally you pay for node resources so it follows that if you run on less nodes then you will pay less cost.   Some clusters are small (2-3 nodes) and designed for specific purposes and not the best targets for waste reduction.  Instead we focus on the larger (and typically more general purpose) clusters to detect waste.&#x20;

Leverage autoscaling to dynamically adjust resources based on real-time demand, ensuring efficient use of infrastructure. Use cost visualization tools to gain insights into spending patterns. For public cloud hosted clusters, regularly review and adjust your provider settings to align with any negotiated pricing discounts available to you.

**Kubernetes waste and causes include;**

* Stranded Resource - CPU or Memory Request too high or not set
* Too Many Nodes Active - Cluster Scaling too high&#x20;

## **Steps to Eliminate Waste** ![](<../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1).png>)

### Targeting a Node Group

Instead of looking at the entire infrastructure at once, we'll choose node groups of interest based on their node-level surpluses and constraints.

* Step 1 - In Kubex select Nodes from the left-side navigator ![](<../.gitbook/assets/image (7).png>)
* Step 2 - descending sort the "Avg no. of Nodes" column to show the largest node groups first ![](<../.gitbook/assets/image (8).png>)
* Step 3 - from the right-side Columns selector enable "Primary Constraints" and filter it on Requests  ![](<../.gitbook/assets/image (9).png>)
* Step 4 - the ideal node groups to target for waste will be those with a high avg. number of nodes and low utilization for the non-primary constraint.  For example if CPU requests is the primary constraints then target node groups where CPU Request is the constraint and Memory Utilization is low.  For example set the "Avg Memory Utilization (%)" to be less then 50. ![](<../.gitbook/assets/image (10).png>)
* Step 5 - Now you can see a list of clusters that are constrained by CPU Requests and where memory utilization is low. &#x20;

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

* Step 6 - Next we choose each group to review the related container resizing recommendations to reduce CPU Requests.  Switch to the Containers view via the left-side navigator ![](<../.gitbook/assets/image (2).png>)
* Step 7 - Selecting the first node group we are considering you can see the related histogram indicating significant CPU Request Surplus.
*

    <figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>
* Step 8 - Click the blue CPU Request Surplus to review the related pod recommendations
* Step 9 - Filter on the Node Group identified during Step 5 to review the CPU Request resizing recommendations.
*

    <figure><img src="../.gitbook/assets/image (36).png" alt=""><figcaption></figcaption></figure>

### **Eliminate** pod unset requests or oversized requests

Select a group of systems then examine the histogram to determine if the CPU or Memory Requests are too high (yellow).

<figure><img src="../.gitbook/assets/image (3) (1) (1).png" alt=""><figcaption></figcaption></figure>

Click on the blue headers to drill into those impacted pods. Here we've gone into the "Memory Request Surplus" group of pods with to examine the waste.

<figure><img src="../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

### **Eliminate** full or imbalanced nodes

[https://www.densify.com/docs-kubex/Content/Kubex/Node%20Group%20Capacity%20View.htm](https://www.densify.com/docs-kubex/Content/Kubex/Node%20Group%20Capacity%20View.htm)

### **Eliminate** node group rescaling options&#x20;

[https://www.densify.com/docs-kubex/Content/Kubex/Node%20Group%20Capacity%20View.htm](https://www.densify.com/docs-kubex/Content/Kubex/Node%20Group%20Capacity%20View.htm)

### **Eliminate** nodes (scale down the cluster) - too many nodes are active due to full or imbalanced nodes

[https://www.densify.com/docs/WebHelp\_Densify\_Cloud/Content/Densify\_Com/Working\_with\_ASGs.htm?Highlight=asg](https://www.densify.com/docs/WebHelp_Densify_Cloud/Content/Densify_Com/Working_with_ASGs.htm?Highlight=asg)

With waste detected the next step is to take action to reduce the waste.  For more information on approaches to taking action skip to "[Taking Action](taking-action.md)".
