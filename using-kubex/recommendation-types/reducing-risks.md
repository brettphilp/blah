# Reducing Risks

Risk are caused by the deployment of containers with unset or poorly set request and limit values for CPU and memory resources.

**Kubernetes risks and impacts include;**

* CPU Request or Limit too small (CPU Throttling)
* Limit too big (Noisy Neighbor)
* Memory Request too small (pod termination via OOM kill)
* Memory Limit too small (process termination within container via OOM kill)
* CPU Request not set (node performance by over stacking)
* CPU Limit not set (Noisy Neighbor and CPU Throttling)
*
*

> <mark style="background-color:blue;">TIP: Fix risks first then save money by downsizing</mark>







#### Reducing Risk

1. **Comprehensive Analysis**:
   * Kubex conducts deep analysis of Kubernetes environments, including both containers and nodes.
   * Recommendations are made based on the entire infrastructure context to avoid harmful changes.
2. **Cost and Risk Awareness**:
   * Many organizations experience a blind spot regarding costs and risks associated with Kubernetes.
   * The software addresses potential waste and resource sensitivity, ensuring stability before efficiency.
3. **Monitoring and Alerts**:
   * The system identifies and highlights containers and nodes at risk, such as those exceeding memory limits or causing restarts due to memory issues.
4. **Data-Driven Recommendations**:
   * Recommendations are provided based on historical data and usage patterns, ensuring that changes will not negatively impact the system.

#### Performance Improvement

1. **Optimization of Resources**:
   * Kubex identifies oversized containers and recommends adjustments to reduce resource waste, which can lead to significant cost savings.
2. **Customizable Views**:

* Users can create tailored views and filters to analyze specific aspects of their environments, helping to focus on critical performance metrics.

