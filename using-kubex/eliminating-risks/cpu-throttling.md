# CPU Throttling

Saturated resources can lead to CPU throttling or OOM kills for hosted containers. Imbalances in CPU or memory utilization across nodes may indicate future saturation and lead to performance and stability issues in containers.

Select a group of systems then examine the histogram to determine if the CPU Requests or Limits are too small (red), or not set (gray).

<figure><img src="../../.gitbook/assets/image (37).png" alt=""><figcaption></figcaption></figure>

Click on the blue headers to drill into those impacted pods. Here we've gone into the "CPU Request Shortfall" group of risky pods to examine the risks and associated recommendations.

<figure><img src="../../.gitbook/assets/image (38).png" alt=""><figcaption></figcaption></figure>
