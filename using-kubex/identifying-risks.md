# Detecting Risks

Risk are caused by the deployment of containers with unset or poorly set request and limit values for CPU and memory resources.

**Kubernetes risks and impacts include;**

* CPU Request or Limit too small (CPU Throttling)
* Limit too big (Noisy Neighbor)
* Memory Request too small or not set (pod OOM kills)
* Memory Limit too small (container process termination via OOM kills)\*
* CPU Request not set (node performance by over stacking)
* CPU Limit not set (Noisy Neighbor and CPU Throttling)
* Memory Limit not set (Noisy Neighbor and pod OOM kills)

\*_coming soon_

> <mark style="background-color:blue;">TIP: Fix risks first then reduce waste</mark>

## **Steps to Detect Risks** ![](<../.gitbook/assets/image (2).png>)

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

Select a group of systems then examine the histogram to determine if the CPU Requests are not set (gray).

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

Click on the blue headers to drill into those impacted pods.  Here we've gone into the "CPU Request Shortfall" group of risky pods to examine the risks.

<figure><img src="../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

### **Detect the OOM Kills and Restarts**&#x20;

Select a group of systems then examine the histogram to determine if the Memory Requests or Limits are too small (red) or not set (gray)

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

* Click on the blue headers to drill into those impacted pods.  Here we've gone into the "Memory Request Shortfall" group of risky pods to examine the risks
*

    <figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>
* Sorting on "Restarts - Last Day" we can quickly detects pods with restarts and evaluate the "% Nodes Memory Saturation" to see if it may be correlated to a full host.  Scrolling across the lower panel of Utilization Charts we can see time of day information for the "No. of Restarts"
*

    <figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>
