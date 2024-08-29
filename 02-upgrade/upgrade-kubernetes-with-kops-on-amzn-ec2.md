
###Updates and Upgrades

## Actual process

1. First it goes to the Master node, and upgrades the Master node to the specified Kubernetes version.
2. Then it goes to the Worker nodes and does the upgrade. It upgrades the worker nodes one by one.

1. Drains all the pods that are currently running on that node.
2. It waits for the pods to be evicted, and then it disables that node, so that no new pods get scheduled to that node.
3. Takes the node offline, upgrades the node, and brings the node back online.
4. Once it has verified that the node has come-up and is back in service, it will then go to the next node and upgrade the node.
