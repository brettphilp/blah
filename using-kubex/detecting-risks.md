# Eliminating Risks

### **Steps to Eliminate Risks** ![](<../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1).png>)

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

For each of the Risk item recommendations are available for actioning. &#x20;

Most risks can be handled by setting container resource request and / or limit settings based on actual historical usage data.  The recommendations to set or adjust these settings are found on the container details screen. &#x20;

Here we show the Namespace level for a group of containers with memory request recommendations (both set as well as upsize in this case to reduce risk).

<figure><img src="../.gitbook/assets/image (48).png" alt=""><figcaption></figcaption></figure>

From here customers often find it helpful to extract or publish these recommendations to internal users.  FinOps practitioners refer to this stage as socializing or campaigning of the optimization recommendations. &#x20;

Extraction can be accomplished via the extract widget in the UI and publishing to third party BI tool can be accomplished via the [Densify API.](../api-and-automation/)

Once application owners are in agreement to action, the recommendations can then be adopted through desired [DevOps or GitOps workflows](../api-and-automation/automation/) as per usual change operations.
