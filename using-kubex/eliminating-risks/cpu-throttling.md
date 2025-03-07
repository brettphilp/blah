# CPU Throttling

CPU throttling refers to the restriction of CPU usage for a container when it attempts to use more CPU resources than it is allowed by its configured limits. This is a mechanism to ensure that no single container can monopolize the CPU resources of a node, thereby affecting the performance of other containers running on the same node.

**Why CPU Throttling is a Problem**

1. **Performance Degradation**: When a container is throttled, its performance can degrade significantly. This is because the container is not able to use the CPU resources it needs to perform its tasks efficiently. This can lead to increased response times and reduced throughput for applications running in the container.
2. **Unpredictable Behavior**: Throttling can lead to unpredictable application behavior, especially for applications with spiky CPU usage patterns. As noted in the [CPUThrottlingHigh alert for metrics-server-nanny container in GKE](https://stackoverflow.com/q/67954658), Kubernetes uses CFS quotas to enforce CPU limits, which can cause pods to get throttled even when they are not consistently busy.
3. **Resource Underutilization**: If CPU limits are set too low, containers may be throttled unnecessarily, leading to underutilization of available CPU resources. This can result in inefficient use of the node's capacity, as other containers may not be able to use the available CPU resources.
4. **Evictions and Node Pressure**: As described in the [Resource Management for Pods and Containers | Kubernetes](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/), if a node is under CPU pressure due to throttling, it may lead to pod evictions. This happens when the actual usage exceeds the requests, even if it is within the limits, causing the system to evict pods to free up resources.

**How to Identify CPU Throttling in Kubex**

Select a group of systems then examine the histogram to determine if the CPU Requests or Limits are too small (red), or not set (gray).

<figure><img src="../../.gitbook/assets/image (37).png" alt=""><figcaption></figcaption></figure>

Click on the blue headers to drill into those impacted pods. Here we've gone into the "CPU Request Shortfall" group of risky pods to examine the risks and associated recommendations.

<figure><img src="../../.gitbook/assets/image (38).png" alt=""><figcaption></figcaption></figure>
