# Taking Action

For each of the Risk or Waste items detected recommendations are available for actioning. &#x20;

Most risks can be handled by setting container resource request and / or limit settings based on actual historical usage data.  The recommendations to set or adjust these settings are found on the container details screen. &#x20;

Here we show the Namespace level for a group of containers with memory request recommendations (downsize in this case to reduce waste).

<figure><img src="../../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

From here customers often find it helpful to extract or publish these recommendations to internal users.  FinOps practitioners refer to this stage as socializing or campaigning of the optimization recommendations. &#x20;

Extraction can be accomplished via the extract widget in the UI and publishing to third party BI tool can be accomplished via the [Densify API.](../../api-and-integration/)

Once application owners are in agreement to action, the recommendations can then be adopted through desired [DevOps or GitOps workflows](../../automation/) as per usual change operations.
