# Using Kubex

The Kubex interface provides a comprehensive, at-a-glance view of your entire container landscape, helping you understand resource allocations from both a performance (Reducing Risk) and a cost-saving (Reducing Costs) perspective.

#### Main Screen Overview

The primary screen of the Kubex user interface consists of a [navigator tree with views and filters](https://www.densify.com/docs-kubex/Content/Videos/Using%20the%20Tree%20Viewer.htm)  where you can contextually display a series of histograms that categorize containers based on their CPU and memory configuration:

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

* **CPU Requests**: Each bar in the histogram represents the number of containers within a specific configuration range. For instance, an excessive number of containers without specified CPU requests can introduce risk, as exemplified by the 243 containers missing this setting in our demonstration. Containers inadequately or excessively utilizing CPU resources are annotated to highlight adjustment opportunities, with oversized allocations typically indicating a chance to reduce costs.
* **Memory Requests**: Memory management presents nuance, with some containers under-allocated and others consuming more than necessary. The histograms help visualize these disparities, highlighting containers with missing memory requests that pose a risk of node overstacking and operational instability. The interface flags such issues, advising corrective measures to prevent excessive memory usage that Kubernetes cannot properly manage.

#### Detailed Insights

By navigating through the dashboard, users can drill down into specific environments, clusters, and namespaces. This flexibility allows for targeted analysis, providing users with the ability to isolate problem areas and ensure efficient resource distribution. You can explore individual namespace statistics and get detailed insights into the health and optimization potential of each segment.

#### Additional Features

* **CPU and Memory Limits**: Although setting CPU limits is optional, configuring memory limits is crucial. Containers with unconstrained memory settings (denoted as gray in the histogram) risk monopolizing node resources, potentially jeopardizing other container operations. Memory limits set too low can result in the Linux kernel terminating processes prematurely, leading to service disruptions.
* **Overall Summary**: The summary tab offers a ranked view of environments, enabling users to quickly identify areas with significant container risks or resource waste. This feature aids in prioritizing optimization efforts across multiple environments, particularly useful in large-scale Kubernetes deployments with thousands of containers.

The Kubex product is designed to serve as a diagnostic tool, much like an MRI, for your Kubernetes environments. It identifies inefficiencies and provides actionable insights, ensuring that even the most sophisticated setups can achieve balanced resource allocation. With this tool, stakeholders can proactively address operational risks, effectively managing their container landscapes for optimal performance and cost efficiency.

For a video walkthrough of this information visit [https://www.youtube.com/watch?v=AP27\_ajtRx4](https://www.youtube.com/watch?v=AP27_ajtRx4)

