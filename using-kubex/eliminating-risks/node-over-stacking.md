# Node Over Stacking

Node over stacking refers to the situation where too many workloads (pods) are scheduled on a single node, exceeding the node's capacity in terms of CPU, memory, or other resources.&#x20;

**Why Node Over Stacking is a Problem**

1. **Resource Contention**: When multiple pods compete for the same resources, it can lead to performance degradation. Some pods may experience slow response times or even timeouts.
2. **Pod Evictions**: If a node runs out of resources, Kubernetes may evict pods to free up space for more critical workloads. This can lead to service disruptions, especially for stateful applications.
3. **Increased Latency**: Overloaded nodes can result in increased latency for requests, as the node struggles to manage multiple workloads simultaneously.
4. **Unstable Applications**: Applications may become unstable or crash if they do not receive the resources they need to operate effectively.
5. **Monitoring and Management Challenges**: With too many workloads on a single node, it can become difficult to monitor performance and manage resources effectively.

#### How to identify Node Over Stacking in Kubex

Select Nodes from the left-side navigator.

![](https://bptest.gitbook.io/~gitbook/image?url=https%3A%2F%2F4188913827-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FRNeoHYPAhUAxZfrIDY0P%252Fuploads%252FnDCEhkRegfE7mGQuAHnO%252Fimage.png%3Falt%3Dmedia%26token%3Dd86cfbb0-7057-4b51-aba1-bbfe6d373b08\&width=768\&dpr=4\&quality=100\&sign=4cbff12e\&sv=2)

Click the link for "Node Group Analysis" at the top of the tabular view. We then descend sort the "Average Memory Utilization" column and see the node groups with very high memory usage. We'll take a closer look at the first node pool "pool-1" in the GKE cluster.

<figure><img src="../../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

Next from the left-side view and filter navigator we pick the "GKE" cluster, expand the cluster to see the node pools and choose the "pool-1" group. We then picked "Nodes" from above the tabular view. Finally we descend sorted on "Memory Utilization" to identify a troubled node.

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

To mitigate node over stacking, Kubernetes provides resource Requests and Limits, which allow developers to specify how much CPU and memory a pod requires, helping the scheduler make better decisions about where to place pods. Additionally, monitoring and autoscaling solutions can help manage workloads more effectively.
