# Detecting Risks

Risk are caused by the deployment of containers with unset or poorly set request and limit values for CPU and memory resources.

**Kubernetes risks and impacts include;**

* CPU Request or Limit too small (CPU Throttling)
* Limit too big (Noisy Neighbor)
* Memory Request too small or not set (pod OOM kills)
* Memory Limit too small (container process termination via OOM kills)
* CPU Request not set (node performance by over stacking)
* CPU Limit not set (Noisy Neighbor and CPU Throttling)
* Memory Limit not set (Noisy Neighbor and pod OOM kills)

> <mark style="background-color:blue;">TIP: Fix risks first then reduce waste</mark>

## **Steps to Detect Risks** ![](<../.gitbook/assets/image (2).png>)

### **Detect the OOM Kills and Restarts**&#x20;

* Use the views and filters to select the portion of the infrastructure to focus on.
* Examine the histogram to determine if the Memory Requests or Limits are too small (red) or not set (gray)
* Double click on the red or gray bars to drill down to those impacted pods
* &#x20;

### **Detect Host Memory Pressure**
