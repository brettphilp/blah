# Unset and Oversized Pod Requests

Managing resources efficiently is crucial for optimal performance and cost-effectiveness. &#x20;

In the case of unset pod cpu or memory resource requests, these are used to inform the scheduler about the minimum amount of resources a pod needs to run effectively. If these requests are not set, Kubernetes may not allocate the necessary resources, leading to potential performance issues or request oversizing.

Oversized pod requests occur when a pod requests more resources than it actually needs. This can happen when developers overestimate the resource requirements of their applications or applications contain sub-optimal code.

### Why are Unset and Oversized Pod Requests a problem?

1. **Inefficient Scheduling**: Without resource requests, the Kubernetes scheduler cannot make informed decisions about where to place the pod. This can lead to inefficient use of cluster resources and potential overcommitment on nodes.
2. **Unpredictable Performance**: Pods without resource requests may not receive the resources they need during peak times, leading to degraded performance or even application crashes.
3. **Default Values**: If a namespace has a LimitRange configured, default values may be applied, which might not align with the actual needs of the application. For example, as shown in the [Kubernetes documentation](https://kubernetes.io/docs/tasks/administer-cluster/manage-resources/memory-default-namespace/), a default memory request of 256MiB and a memory limit of 512MiB might be applied if not specified.
4. **Resource Wastage**: Oversized requests can lead to underutilization of cluster resources. Nodes may appear full, preventing other pods from being scheduled, even though there is available capacity.
5. **Increased Costs**: In cloud environments, resource allocation often directly impacts costs. Oversized requests can lead to higher expenses without corresponding performance benefits.
6. **Scheduling Delays**: If a pod requests more resources than any node can provide, it may remain in a pending state, waiting for a suitable node to become available.

### How to Identify Pods with Unset or Oversized Requests in Kubex

Select a group of systems then examine the histogram to determine if the CPU or Memory Requests are too high (yellow).

<figure><img src="../../.gitbook/assets/image (44).png" alt=""><figcaption></figcaption></figure>

Click on the blue headers to drill into those impacted pods. Here we've gone into the "Memory Request Surplus" group of pods with to examine the waste and associated recommendations.

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>
