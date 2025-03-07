# Oversized Node Groups

Oversized Node Groups refers to a situation where a node group (a collection of nodes that share the same configuration and are managed together) is configured with too many nodes relative to the workload it supports. This can happen for several reasons, such as misconfigured resource requests and limits, scaling issues, or simply having too few workloads for the available resources.

**Why Oversized Node Groups are a Problem**

1. **Nodes are the cost basis for Kubernetes workloads:** Oversized node groups results in wasted costs, especially in cloud environments where you pay for what you provision.  Organizations may end up paying for unused capacity, which can significantly impact budgets.
2. **Inefficient Scheduling:** Kubernetes uses scheduling algorithms to allocate pods to nodes based on resource availability. Oversized node groups can lead to inefficient scheduling, where smaller pods are unable to be placed effectively on larger nodes, potentially leading to fragmentation of resources.
3. **Longer Recovery Times**: When nodes in an oversized group become unavailable, the recovery time might be longer due to the excess resources. This can lead to delays in service restoration and impact application performance.
4. **Operational Complexity**: Managing oversized node groups can add complexity to operations, as monitoring and scaling become more challenging. It may lead to confusion over resource allocation and overall cluster health.

**How to Identify Oversized Node Groups in Kubex**

Instead of looking at the entire infrastructure at once, we'll choose node groups of interest based on their node-level surpluses and constraints.

* Step 1 - In Kubex select "Nodes" from the left-side navigator ![](<../../.gitbook/assets/image (7).png>)
* Step 2 - descending sort the "Avg no. of Nodes" column to show the largest node groups first ![](<../../.gitbook/assets/image (8).png>)
* Step 3 - from the right-side Columns selector enable "Primary Constraints" and filter it on Requests  ![](<../../.gitbook/assets/image (9).png>)
* Step 4 - the ideal node groups to target for waste will be those with a high avg. number of nodes and low utilization for the non-primary constraint.  For example if CPU requests is the primary constraints then target node groups where CPU Request is the constraint and Memory Utilization is low.  For example set the "Avg Memory Utilization (%)" to be less then 50. ![](<../../.gitbook/assets/image (10).png>)
* Step 5 - Now you can see a list of clusters that are constrained by CPU Requests and where memory utilization is low. &#x20;

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Step 6 - Next we choose each group to review the related container resizing recommendations to reduce CPU Requests.  Switch to the "Containers" view via the left-side navigator ![](<../../.gitbook/assets/image (2) (1) (1) (1).png>)
* Step 7 - Selecting the first node group we are considering you can see the related histogram indicating significant CPU Request Surplus.
*

    <figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>
* Step 8 - Click the blue "CPU Request Surplus" link to review the related pod recommendations
* Step 9 - Filter on the Node Group identified during Step 5 to review the CPU Request resizing recommendations.
*

    <figure><img src="../../.gitbook/assets/image (36).png" alt=""><figcaption></figcaption></figure>

### Handling Oversized Node Groups

* **Step 1 - Right sizing pods:** eliminate CPU and memory request waste as described under [Unset and Oversized Pod Requests](unset-pod-requests-and-oversized-requests.md) and using either [GitOps integration with your source control via the Kubex API](../../api-and-automation/api-reference.md) or  [the Kubex Mutating Admission Controller ](../../api-and-automation/automation/kubex-mutating-admission-controller.md)to automatically adjust the resource request and limits of deployed pods
* **Step 2 - Autoscale the Cluster Nodes:** leverage a [Cluster Autoscaler](https://kubernetes.io/docs/concepts/cluster-administration/node-autoscaling/#autoscaler-implementations) to adjust the size of the node  group based on the new demands after pod request Right-Sizing of the workloads running in the cluster

