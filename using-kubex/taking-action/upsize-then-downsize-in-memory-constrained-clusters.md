# Upsize then Downsize in Memory Constrained Clusters

If any nodes are overloaded, reducing container sizes might lead to more containers being scheduled on each node, potentially worsening the issue. Typically, there is a mix of underutilized and overutilized nodes, making the situation complex. If a small container is placed on a stressed node (where usage exceeds total requests), it can exacerbate the problem.

If none of the nodes are close to capacity, reducing container sizes is acceptable, and we recommend starting with these adjustments to achieve "realizable gains." However, if too many containers are downsized without addressing smaller containers in the same node group, it can lead to overloading. In such cases, some containers may need to be upsized to alleviate stress.

Generally, CPU resources can be safely reduced first, while memory may be constrained on some nodes. Increasing memory requests (or setting those that are unset) will help before reducing any excess memory requests. Thus, the recommended order is to reduce CPU, increase memory, and then adjust other resources as needed. However, the specific approach may vary depending on the cluster's condition, and the user interface can provide guidance on whether memory downsizing is feasible from the outset.
