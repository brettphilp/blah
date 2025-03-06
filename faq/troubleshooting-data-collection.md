# Troubleshooting

### **Viewing the Densify Forwarder log** <a href="#toc155089468" id="toc155089468"></a>

Inspect the log for the Densify Forwarder job.  _kubectl logs_ can be used as documented at [https://kubernetes.io/docs/reference/kubectl/generated/kubectl\_logs/](https://kubernetes.io/docs/reference/kubectl/generated/kubectl_logs/)

For example using the All-In-One method of collection you would specify

`kubectl logs kubex-kubex-stack -n densify`&#x20;

A successful completion will look something like this:

<figure><img src="../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

* Messages with a status of \[WARNING] are expected and are not by themselves an indicator of a failure
* Messages showing a fatal error mean the data collection didn't complete successfully
* Near completion you should see a message "zipping \<clustername>.zip" and the number of files should be dozens.  If it's a small number (say, under 10) then there is almost certainly an issue.
* If the file upload is unsuccessful, it may mean the instance is unreachable or hasn't been configured for containers yet.

### **Proxy**

* Some deployments may require the use of a proxy service to forward data back to Densify
* Update the Proxy section of the configmap.yaml file and rerun the job &#x20;

### "Error from server (BadRequest): container "data-forwarder" in pod "densify" is waiting to start: ContainerCreating"

This means the pod is in a hung state while creating. This can happen when the configmap can't be found. Check that you both ran the command to apply the configmap, and also that you created the configmap in the same namespace where you created the pod.

### **Fatal error "HTTP status code: 401, Message: message: Unauthorized"**&#x20;

Means the credentials you specified are invalid. Check they were specified correctly in the configmap.

### **"Permission denied" saving the Zip file**&#x20;

In the configmap try changing the value "zipname" from \<cluster\_name> to data/\<cluster\_name>

### **x509 Errors**

You may see this error sometimes if they are using a web filter/firewall/gateway device that is configured for deep SSL inspection (i.e. FortiGate web filter). This feature can ‘break’ the SSL certificate chain.

<figure><img src="../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

A troubleshooting tool is available, comprised of a pod that can be deployed which would provide helpful output that can be sent to support@densify.com.  Output will show details of certificate chain, Densify support can then validate whether the issues is customer side issue or not.&#x20;

* Tool can be found here: [https://github.com/densify-dev/cert-output](https://github.com/densify-dev/cert-output)&#x20;
* Instructions for deployment found here: [https://github.com/densify-dev/cert-output/blob/main/examples/README.md](https://github.com/densify-dev/cert-output/blob/main/examples/README.md)

### **Cluster Re-Paving**

Some deployments use devops processes such as cluster repaving to periodically completely destroy the cluster and rebuild it from scratch via codified declarations - Densify's Data Forwarder will need to be part of the cluster deployment process / template or will be removed when repaving happens.
