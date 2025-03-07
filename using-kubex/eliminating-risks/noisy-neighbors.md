# Noisy Neighbors

A noisy neighbor in Kubernetes refers to a situation where one pod (or set of pods) consumes an excessive amount of shared resources, such as CPU or memory thereby negatively impacting the performance of other pods running on the same node. This scenario typically occurs in a multi-tenant environment where multiple applications or services are deployed on the same cluster.

#### Why are Noisy Neighbors a Problem?

1. **Resource Contention**: When one pod consumes too many resources, it can starve other pods of the resources they need to function properly, leading to degraded performance or even outages.
2. **Latency Issues**: High resource usage by a noisy neighbor can lead to increased latency for requests handled by other pods, affecting the overall user experience.
3. **Unpredictable Performance**: Applications may behave unpredictably, as their performance can vary widely depending on the resource consumption patterns of other pods.
4. **Operational Complexity**: Troubleshooting performance issues becomes more complex when you have noisy neighbors, as it can be challenging to identify which pod is causing the problem.
5. **Resource Waste**: Inefficient resource usage can lead to waste, as the cluster may require more nodes to meet the demands of all applications, resulting in higher operational costs.

**How to Identify Noisy Neighbors in Kubex**

Select a group of systems then examine the histogram to determine if the CPU or Memory Limits are not set (gray), or too big (yellow).

<figure><img src="../../.gitbook/assets/image (39).png" alt=""><figcaption></figcaption></figure>

Click on the blue headers to drill into those impacted pods. Here we've gone into the "Oversized Memory Limit" group of risky pods to examine the risks and associated recommendations.

<figure><img src="../../.gitbook/assets/image (40).png" alt=""><figcaption></figcaption></figure>
