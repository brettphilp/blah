# Node Over Stacking

Select Nodes from the left-side navigator.

![](https://bptest.gitbook.io/~gitbook/image?url=https%3A%2F%2F4188913827-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FRNeoHYPAhUAxZfrIDY0P%252Fuploads%252FnDCEhkRegfE7mGQuAHnO%252Fimage.png%3Falt%3Dmedia%26token%3Dd86cfbb0-7057-4b51-aba1-bbfe6d373b08\&width=768\&dpr=4\&quality=100\&sign=4cbff12e\&sv=2)

Click the link for "Node Group Analysis" at the top of the tabular view. We then descend sort the "Average Memory Utilization" column and see the node groups with very high memory usage. We'll take a closer look at the first node pool "pool-1" in the GKE cluster.

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

Next from the left-side view and filter navigator we pick the "GKE" cluster, expand the cluster to see the node pools and choose the "pool-1" group. We then picked "Nodes" from above the tabular view. Finally we descend sorted on "Memory Utilization" to identify a troubled node.

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>
