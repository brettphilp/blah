# Taking Action

For each of the Risk or Waste items detected recommendations are available for actioning. &#x20;

Most risks can be handled by setting container resource request and / or limit settings based on actual historical usage data.  The recommendations to set or adjust these settings are found on the container details screen. &#x20;

Here we show the Namespace level for a group of containers with memory request recommendations (downsize in this case to reduce waste).

<figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

From here customers often find it helpful to extract or publish these recommendations to internal users.  FinOps practitioners refer to this stage as socializing or campaigning of the optimization recommendations. &#x20;

Extraction can be accomplished via the extract widget in the UI and publishing to third party BI tool can be accomplished via the [Densify API.](../api-and-integration/)

Once application owners are in agreement to action, the recommendations can then be adopted through desired [DevOps or GitOps workflows](../automation/) as per usual change operations.

**Special Note for Constrained Clusters :**

In instances where any nodes are experiencing saturation—such as in the case of memory constraints—downsizing containers may lead to an increased number of deployments on each node, potentially exacerbating the situation. Typically, there exists a combination of underutilized and overutilized nodes, which complicates the matter. Specifically, if an undersized container is allocated to a node that is already under stress (where utilization exceeds the aggregate resource requests), this can further aggravate the problem.

Conversely, if none of the nodes are nearing their maximum capacity, downsizing is generally not problematic, and it is advisable to prioritize these downsizes first to achieve what can be termed "realizable gains." However, executing a sufficient number of these downsizes may lead to utilization becoming the limiting factor, especially if undersized containers remain within the same node group, ultimately resulting in over stacking. In such cases, some level of upsizing will be necessary to alleviate the stress.

Typically, it is feasible to immediately downsize CPU allocations; however, memory utilization may be strained on certain nodes. Therefore, it is prudent to increase memory requests (or set previously unset requests) prior to downsizing any oversized memory allocations. The recommended sequence of actions is to first downsize CPU allocations, followed by increasing memory requests, and finally downsizing any other applicable resources. Nonetheless, the specific approach may vary depending on the characteristics of the cluster, as the user interface may indicate whether memory downsizing can be initiated from the outset.
