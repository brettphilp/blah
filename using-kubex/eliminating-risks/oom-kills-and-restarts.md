# OOM Kills and Restarts

OOM (Out of Memory) kills and restarts are mechanisms that manage memory usage within containers and pods. These processes are crucial for maintaining the stability and performance of applications running in a cluster.  OOM kills occur when a container tries to use more memory than its allocated limit.

Restarts occur when a container is terminated and then restarted by the kubelet. This can happen due to OOM kills or other failures.

### Why OOM Kills and Restarts are Problematic

1. **Resource Management**: OOM kills highlight the importance of proper resource management. Containers without adequate memory limits can consume all available memory on a node, affecting other pods and potentially leading to node instability.
2. **Application Stability**: Applications that frequently hit memory limits and are OOM killed may experience downtime, affecting user experience and service reliability.
3. **Debugging Complexity**: Identifying the root cause of OOM kills can be challenging. It requires analyzing logs, monitoring resource usage, and understanding application behavior.
4. **Performance Degradation**: Frequent restarts can degrade the performance of applications, leading to increased response times and reduced throughput.



Select a group of systems then examine the histogram to determine if the Memory Requests or Limits are too small (red) or not set (gray)

<figure><img src="../../.gitbook/assets/image (41).png" alt=""><figcaption></figcaption></figure>

* Click on the blue headers to drill into those impacted pods. Here we've gone into the "Memory Request Shortfall" group of risky pods to examine the risks
*

    <figure><img src="../../.gitbook/assets/image (42).png" alt=""><figcaption></figcaption></figure>
* Sorting on "Restarts - Last Day" we can quickly detects pods with restarts and evaluate the "% Nodes Memory Saturation" to see if it may be correlated to a full host. Scrolling across the lower panel of Utilization Charts we can see time of day information for the "No. of Restarts"
*

    <figure><img src="../../.gitbook/assets/image (43).png" alt=""><figcaption></figcaption></figure>
