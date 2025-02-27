# Troubleshooting

[<mark style="color:yellow;">Troubleshooting notes from main docs</mark>](https://github.com/densify-dev/container-data-collection/blob/main/egress-requirements.md)

* **User Credential vs. Service Credential**
  * It is recommended to use a Service Credential with the Densify Forwarder as User Credentials will have password timeouts/resets that would cause the Forwarder to fail.  Request a Service ID from support@densify.com.
*   **View the logs**

    &#x20;

    `kubectl logs densify –n <namespace>`

    &#x20;

    By default, the one-time pod will deploy to the default namespace, so you won't have to specify a namespace.  But if you see the error "Error from server (NotFound): pods "densify" not found" it may indicate the pod was deployed to a non-default namespace.

    &#x20;

    A successful completion will look something like this:

    <figure><img src="../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

    * Messages with a status of \[WARNING] are expected and are not by themselves an indicator of a failure
    * Messages showing a fatal error mean the data collection didn't complete successfully
    * Near completion you should see a message "zipping \<clustername>.zip" and the number of files should be dozens.  If it's a small number (say, under 10) then there is almost certainly an issue.
    * If the file upload is unsuccessful, it may mean the instance is unreachable or hasn't been configured for containers yet.
* **Prometheus Not Setup Properly for Densify**
  * Review the pre-requisites for your desired approach to data collection
  * A detailed list of metrics (and their sources) is provided at [https://github.com/densify-dev/container-data-collection/tree/main/docs#prometheus-metrics](https://github.com/densify-dev/container-data-collection/tree/main/docs#prometheus-metrics)
  * Consider using the Helm - All In One Installation method as it will provide a Prometheus stack that includes are necessary components required for Densify.&#x20;
* **Proxy**
  * Some deployments may require the use of a proxy service to forward data back to Densify
  * Update the Proxy section of the configmap.yaml file and rerun the job &#x20;
* #### "Error from server (BadRequest): container "data-forwarder" in pod "densify" is waiting to start: ContainerCreating"
  * This means the pod is in a hung state while creating. This can happen when the configmap can't be found. Check that you both ran the command to apply the configmap, and also that you created the configmap in the same namespace where you created the pod.
* **"Error 429 - message: Request too frequent. Please wait 3600 seconds before trying again"**&#x20;
  * This means the cronjob is likely scheduled incorrectly. By default it should run once an hour (“0 \* \* \* \*” in Crontab format), but if schedule was misconfigured, it could be trying to send data too frequently, in which case the Densify API will simply block the connection.
  * Check the schedule in the cronjob.yaml and make sure it’s set to hourly like this example:

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

Here’s an example of an incorrect schedule, where its set to run every minute:

<figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

*
* **Cluster Re-Paving**
  * Some deployments use devops processes such as cluster repaving to complete destroy the cluster and rebuild it from scratch via codified declarations - Densify's Data Forwarder will need to be part of that process or will be removed when repaving happens

