# OOM Kills and Restarts

Select a group of systems then examine the histogram to determine if the Memory Requests or Limits are too small (red) or not set (gray)

<figure><img src="../../.gitbook/assets/image (41).png" alt=""><figcaption></figcaption></figure>

* Click on the blue headers to drill into those impacted pods. Here we've gone into the "Memory Request Shortfall" group of risky pods to examine the risks
*

    <figure><img src="../../.gitbook/assets/image (42).png" alt=""><figcaption></figcaption></figure>
* Sorting on "Restarts - Last Day" we can quickly detects pods with restarts and evaluate the "% Nodes Memory Saturation" to see if it may be correlated to a full host. Scrolling across the lower panel of Utilization Charts we can see time of day information for the "No. of Restarts"
*

    <figure><img src="../../.gitbook/assets/image (43).png" alt=""><figcaption></figcaption></figure>
