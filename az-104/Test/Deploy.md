
## upgrade aks cluster 

Your organization has an Azure subscription that contains an AKS cluster running an older version of Kubernetes.

You have been assigned to upgrade the cluster to the latest stable version of Kubernetes.

![Alt text](image-147.png)

Periodic upgrades to the latest Kubernetes version are part of the AKS cluster lifecycle. It is critical that you apply the most recent security updates or upgrade to get the most recent features. In Azure, you can upgrade a cluster using Azure CLI, PowerShell or Portal.

AKS performs the following operations during the cluster upgrade process:

-Add a new buffer node to the cluster that runs the specified Kubernetes version (or as many nodes as configured in max surge).

-To minimize disruption to running applications, cordon and drain one of the old nodes. When you use max surge, it cordons and drains as many nodes as the number of buffer nodes you specify.

-When the old node is completely depleted, it is reimaged to receive the new version and serves as a buffer node for the next node to be upgraded.

-This process is repeated until all cluster nodes have been upgraded.

-At the end of the process, the last buffer node is deleted while the existing agent node is kept.

Hence, the correct answer is: Plan and execute the upgrade by reviewing release notes, determining a maintenance window, and upgrading the AKS cluster via Azure Portal.

The option that says: Run az aks get-upgrades in Azure CLI to upgrade the AKS cluster to the latest Kubernetes version is incorrect because this command won’t upgrade the cluster but it will just get the upgrade versions available for a managed Kubernetes cluster.

The option that says: Stop all workloads, scale down the cluster to zero nodes, delete the cluster, create a new AKS cluster, and redeploy the application workloads is incorrect because deleting the cluster and redeploying all the application workloads would result in unnecessary downtime and resource loss, as well as potential issues in recreating the cluster and redeploying the applications.

The option that says: Create a new AKS cluster with the desired Kubernetes version, migrate the application workloads from the old cluster to the new cluster, and then delete the old cluster is incorrect because this approach would involve unnecessary complexity and downtime for migrating the workloads between clusters, which can be avoided by upgrading the existing cluster directly.

## 

Your organization has an AKS cluster that hosts several microservices as Kubernetes deployments. 

During peak hours, one of the deployments experiences high traffic, resulting in longer response times and occasional failures.

You plan to implement horizontal pod autoscaling to scale the deployment based on traffic.

![Alt text](image-150.png)

The horizontal pod autoscaler (HPA) is used by Kubernetes to monitor resource demand and automatically scale the number of pods. The HPA checks the Metrics API for any required changes in replica count every 15 seconds by default, and the Metrics API retrieves data from the Kubelet every 60 seconds. As a result, the HPA is updated every 60 seconds. When changes are made, the number of replicas is increased or decreased.

The following steps should be taken to configure horizontal pod autoscaling (HPA) for the deployment:

Install the Kubernetes Metrics Server to provide HPA with metrics.
In the Kubernetes manifest file, define a horizontal pod autoscaler object. This object specifies the scaled deployment, the minimum and maximum number of replicas, and the scaling metric.
Set the deployment’s minimum and maximum number of replicas. Based on the specified metric, these values determine the number of pods that the HPA feature can create or delete.
Hence, the correct answer is: Install Kubernetes Metrics Server, then define an HPA object in the manifest file and set the min and max number of replicas in a deployment.

The option that says: Install Kubernetes Dashboard, then define an HPA object in the manifest file and set the desired min and max number of replicas in a deployment is incorrect because the Kubernetes Dashboard does not provide HPA functionality. It is mainly used for deploying applications, creating and updating objects, and monitoring the health of the cluster.

The option that says: Install AKS cluster autoscaler, then define an HPA object in the manifest file and set the desired min and max number of replicas in a deployment is incorrect because the AKS cluster autoscaler scales the number of nodes in an AKS cluster rather than the number of replicas in a deployment.

The option that says: Install Azure Monitor for Containers agent, then define a VPA object in the manifest file and set the desired min and max number of replicas in a deployment is incorrect. Instead of scaling the number of replicas, vertical pod autoscaling (VPA) is used to adjust the resource allocation of individual pods based on their resource usage.

 

References:

https://learn.microsoft.com/en-us/azure/aks/tutorial-kubernetes-scale?tabs=azure-cli#autoscale-pods

https://learn.microsoft.com/en-us/azure/aks/intro-kubernetes

