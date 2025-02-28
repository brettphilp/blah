# Detecting Risks

Risk are caused by the deployment of containers with unset or poorly set request and limit values for CPU and memory resources.

**Kubernetes risks and causes include;**

* **CPU Throttling**
  * CPU Request or Limit too small&#x20;
  * CPU Limit not set&#x20;
* **Noisy Neighbor**
  * CPU Limit not set&#x20;
  * Memory Limit not set
  * Limit too big
* **Node Performance**&#x20;
  * CPU or Memory Request not set&#x20;
* **Pod OOM Kill**&#x20;
  * Memory Request too small or not set
  * Memory Limit not set
  * Memory Limit too small (container process termination via OOM kills)\*

\*_coming soon_

## **Steps to Detect Risks** ![](<../.gitbook/assets/image (2) (1) (1) (1).png>)

### **Detecting** CPU Throttling

Select a group of systems then examine the histogram to determine if the CPU Requests or Limits are too small (red), or not set (gray).

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

Click on the blue headers to drill into those impacted pods.  Here we've gone into the "CPU Request Shortfall" group of risky pods to examine the risks.

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

### Detecting Noisy Neighbors

Select a group of systems then examine the histogram to determine if the CPU or Memory Limits are not set (gray), or too big (yellow).

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

Click on the blue headers to drill into those impacted pods.  Here we've gone into the "Oversized Memory Limit" group of risky pods to examine the risks.

<figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

### Detecting Node Over Stacking

Select Nodes from the left-side navigator.

<figure><img src="../.gitbook/assets/image (2) (1) (1).png" alt=""><figcaption></figcaption></figure>

Click the link for "Node Group Analysis" at the top of the tabular view.  We then descend sort the "Average Memory Utilization" column and see the node groups with very high memory usage.  We'll take a closer look at the first node pool "pool-1" in the GKE cluster.

<figure><img src="../.gitbook/assets/image (5) (1).png" alt=""><figcaption></figcaption></figure>

Next from the left-side view and filter navigator we pick the "GKE" cluster, expand the cluster to see the node pools and choose the "pool-1" group.  We then picked "Nodes" from above the tabular view.  Finally we descend sorted on "Memory Utilization" to identify a troubled node.

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

### **Detect the OOM Kills and Restarts**&#x20;

Select a group of systems then examine the histogram to determine if the Memory Requests or Limits are too small (red) or not set (gray)

<figure><img src="../.gitbook/assets/image (6) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Click on the blue headers to drill into those impacted pods.  Here we've gone into the "Memory Request Shortfall" group of risky pods to examine the risks
*

    <figure><img src="../.gitbook/assets/image (7) (1) (1).png" alt=""><figcaption></figcaption></figure>
* Sorting on "Restarts - Last Day" we can quickly detects pods with restarts and evaluate the "% Nodes Memory Saturation" to see if it may be correlated to a full host.  Scrolling across the lower panel of Utilization Charts we can see time of day information for the "No. of Restarts"
*

    <figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

With risks detected the next step is to take action to remedy the risks.  For more information on approaches to taking action skip to "[Taking Action](taking-action.md)".
