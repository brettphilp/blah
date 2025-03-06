# Navigating the UI

By navigating through the dashboard, users can drill down into specific environments, clusters, and namespaces. This flexibility allows for targeted analysis, providing users with the ability to isolate problem areas and ensure efficient resource distribution. You can explore individual namespace statistics and get detailed insights into the health and optimization potential of each segment.

<mark style="color:yellow;">Joanne's video and content around UI elements would fit well here</mark>

[<mark style="color:yellow;">https://www.densify.com/docs-kubex/Content/Welcome.htm</mark>](https://www.densify.com/docs-kubex/Content/Welcome.htm)

#### Additional Features

* **CPU and Memory Limits**: Although setting CPU limits is optional, configuring memory limits is crucial. Containers with unconstrained memory settings (denoted as gray in the histogram) risk monopolizing node resources, potentially jeopardizing other container operations. Memory limits set too low can result in the Linux kernel terminating processes prematurely, leading to service disruptions.
* **Overall Summary**: The summary tab offers a ranked view of environments, enabling users to quickly identify areas with significant container risks or resource waste. This feature aids in prioritizing optimization efforts across multiple environments, particularly useful in large-scale Kubernetes deployments with thousands of containers.
