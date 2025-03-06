# Eliminating Risks

### **Steps to Eliminate Risks** ![](<../.gitbook/assets/image (2) (1) (1) (1) (1) (1).png>)

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
