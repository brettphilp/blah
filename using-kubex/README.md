# Using Kubex

#### Main Screen Overview

The primary screen of the Kubex user interface consists of a [navigator tree with views and filters](https://www.densify.com/docs-kubex/Content/Videos/Using%20the%20Tree%20Viewer.htm)  where you can contextually display a series of histograms that categorize containers based on their CPU and memory configuration.  Users can create tailored views and filters to analyze specific aspects of their environments, helping to focus on critical performance metrics.

The ability to visualize resource allocation through histograms allows organizations to better understand how efficiently their containers are using CPU and memory resources. By knowing where inefficiencies lie, companies can make informed decisions about resource adjustments.

The visual nature of the histograms can also facilitate better communication among different teams within an organization. By presenting data in an easily digestible format, stakeholders can quickly understand resource allocation issues and collaborate on solutions.

The histogram not only highlights inefficiencies but also allows companies to identify potential waste. By pinpointing containers that are consuming unnecessary resources, organizations can streamline their operations and reduce waste.

The color-coded system (red, yellow, green) is a crucial feature that simplifies the complex data associated with resource health. It allows users to quickly ascertain which containers are at risk (red), which are over-allocated (yellow), and which are functioning optimally (green), making it easier to address issues before they escalate.

<figure><img src="../.gitbook/assets/image (3) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

The ability to group histograms by application, business unit, or region provides a multi-dimensional view of resource allocation. This dynamic analysis is essential for organizations with diverse operations, as it enables targeted interventions and optimizations.

With the insights gained from these visualizations, teams can take a proactive approach to resource management. Rather than waiting for issues to arise, organizations can continuously monitor and adjust resource allocations based on real-time data.

* **CPU Requests**: Each bar in the histogram represents the number of containers within a specific configuration range. For instance, an excessive number of containers without specified CPU requests can introduce risk, as exemplified by the 243 containers missing this setting in our demonstration. Containers inadequately or excessively utilizing CPU resources are annotated to highlight adjustment opportunities, with oversized allocations typically indicating a chance to reduce waste.
* **Memory Requests**: Memory management presents nuance, with some containers under-allocated and others consuming more than necessary. The histograms help visualize these disparities, highlighting containers with missing memory requests that pose a risk of node overstacking and operational instability. The interface flags such issues, advising corrective measures to prevent excessive memory usage that Kubernetes cannot properly manage.

#### Additional Features

* **CPU and Memory Limits**: Although setting CPU limits is optional, configuring memory limits is crucial. Containers with unconstrained memory settings (denoted as gray in the histogram) risk monopolizing node resources, potentially jeopardizing other container operations. Memory limits set too low can result in the Linux kernel terminating processes prematurely, leading to service disruptions.
* **Overall Summary**: The summary tab offers a ranked view of environments, enabling users to quickly identify areas with significant container risks or resource waste. This feature aids in prioritizing optimization efforts across multiple environments, particularly useful in large-scale Kubernetes deployments with thousands of containers.

