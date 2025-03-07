# CPU Throttling

CPU throttling in Kubernetes refers to the restriction of CPU usage for a container when it attempts to use more CPU resources than it is allowed by its configured limits. This is a mechanism to ensure that no single container can monopolize the CPU resources of a node, thereby affecting the performance of other containers running on the same node.

Select a group of systems then examine the histogram to determine if the CPU Requests or Limits are too small (red), or not set (gray).

<figure><img src="../../.gitbook/assets/image (37).png" alt=""><figcaption></figcaption></figure>

Click on the blue headers to drill into those impacted pods. Here we've gone into the "CPU Request Shortfall" group of risky pods to examine the risks and associated recommendations.

<figure><img src="../../.gitbook/assets/image (38).png" alt=""><figcaption></figcaption></figure>
