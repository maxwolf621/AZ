# 3-29 

Your company has 12 peered virtual networks in your Azure subscription.

You plan to deploy a network security group for each virtual network.

There is a compliance requirement that port 80 should be automatically blocked between virtual networks whenever a new network security group is created. 

The solution must minimize administrative effort.


**ANS :**
It is stated in the scenario that **blocking port 80 should be done automatically whenever a new network security group is created.** 

By creating a rule manually, it becomes quite cumbersome to configure as you need to create a security rule for every network security group you create. 

![Alt text](image-104.png)
**It’s best practice to always automate your security processes to avoid administrative overhead.**  
**You should use a custom policy definition in order to automate the requirement.**  

Azure Policy has a list of built-in policy definitions, but if you need something more specific, you can create your own by creating a custom policy definition that will allow your organization to meet its compliance requirements.

A custom policy definition allows customers to define their own rules for using Azure. 

These rules often enforce:
– Security practices
– Cost management
– Organization-specific rules (like naming or locations)

:x:

![Alt text](image-105.png)
You configure the network security group (NSG) flow log to automatically block port 80.

Network security group (NSG) flow logs are a feature of Azure Network Watcher that allows you to log the source and destination IP address, port, protocol, and whether traffic was allowed or denied by an NSG. Flow data is sent to Azure Storage accounts from where you can access it as well as export it to any visualization tool, SIEM, or IDS of your choice.

NSG flow logs are only used to monitor traffic that is allowed or denied by a network security group.


## Associate a public IP address to a SKU of Standard Public Load Balancer

https://docs.microsoft.com/en-us/azure/virtual-network/ip-services/public-ip-addresses

https://docs.microsoft.com/en-us/azure/virtual-network/ip-services/configure-public-ip-load-balancer

A public IP associated with a load balancer serves as an Internet-facing frontend IP configuration.   
- The frontend is used to access resources in the backend pool. (Internet -> Resource)
- The frontend IP can be used for members of the backend pool to egress to the Internet. (Resource -> Internet)

Remember that 
1. The SKU of a load balancer and the SKU of a public IP address SKU must match
2. You can only create a standard public IP address with an assignment of static

**Q 4-3:**
![Alt text](image-113.png)

You need to associate a public IP address to a public Azure load balancer with an SKU of standard.


**ANS :**
:o: TD3.  

:x: TD1 and TD1 and TD2 are incorrect 
- because both public IP addresses have an SKU of basic. 
- You must provision a public IP address with a SKU of standard so you can associate it with a standard public load balancer.

:x: TD3 and TD4 is incorrect 
- **because you can only create a standard public IP address with an assignment of static**.

## Network Interface usage

:m: Learning : 
**A virtual machine, virtual network and network interface must be in the same region or location.**

**Q 4-9**
Tutorials Dojo has a subscription named `TDSub1` that contains the following resources:
![Alt text](image-119.png)

`TDVM1` needs to connect to a newly created virtual network named `TDNET1` that is located in Japan West.

What should you do to connect `TDVM1` to `TDNET1`?

:x: Solution: You create a network interface in TD1 in the South East Asia region.

:o: Solution : Redeploy TDVM1 to the Japan West region and create and attach a network interface in the Japan West Region.

---

A network interface enables an Azure Virtual Machine to communicate with internet, Azure, and on-premises resources. 

When creating a virtual machine using the Azure portal, the portal creates one network interface with default settings for you.

:star2: what you may do with interface setup 
- **You may instead choose to create network interfaces with custom settings and add one or more network interfaces to a virtual machine when you create it.** 
- **You may also want to change default network interface settings for an existing network interface.**

![Alt text](image-120.png)

:warning: :triangular_flag_on_post:	Remember these conditions and restrictions when it comes to network interfaces:  
1. A VM can have multiple network interfaces attached BUT a network interface can only be attached to a single VM.  
2. The network interface must be located in the same region and subscription as the VM that it will be attached to.
3. **When you delete a virtual machine, the network interface attached to it will not be deleted.**
4. In order to detach a network interface from a VM, you must shut down the virtual machine first.
5. **By default, the first network interface attached to a VM is the primary network interface.**  
All other network interfaces in the VM are secondary network interfaces.

:star2: **Take note that resources inside a resource group can be of different regions.**
- A resource group is only a logical grouping of resources so it does not matter if a resource group is located in a different region.

:warning: (VM與NIC) Each NIC attached to a VM must exist in the same location and subscription as the VM. 
:warning: (Subscript與NIC) Each NIC must be connected to a VNet that exists in the same Azure location and subscription as the NIC. 
:warning: You can’t change the virtual network.

## (Azure Network Watcher) Capture IP Traffic and Diagnose connectivity Issue


**Q 4-15**
You have an Azure subscription that contains a subscription named `TDSub1`.

There is a requirement to assess your network infrastructure using Azure Network Watcher. 

You plan to do the following activities:
1. Capture information about the IP traffic going to and from a network security group.
2. Diagnose connectivity issues to or from an Azure virtual machine

Which feature should you use for each activity?

**ANS**

Capture information about the IP traffic going to and from a network security group: `NSG flow logs`

Diagnose connectivity issues to an Azure virtual machine: `IP flow verify`



---

https://docs.microsoft.com/en-us/azure/network-watcher/network-watcher-monitoring-overview

https://docs.microsoft.com/en-us/azure/network-watcher/network-watcher-ip-flow-verify-overview

https://docs.microsoft.com/en-us/azure/network-watcher/network-watcher-nsg-flow-logging-overview

 
`Azure Network Watcher Resource | Network diagnostic tools`  
`Azure Network Watcher Resource | Logs`  
![Alt text](image-125.png)  

Network security group (NSG) flow logs is a feature of Azure Network Watcher that allows you to log information about IP traffic flowing through an NSG. 

Flow data is sent to Azure Storage accounts from where you can access it as well as export it to any visualization tool, SIEM, or IDS of your choice.

Flow logs are the source of truth for all network activity in your cloud environment. 

Whether you’re an upcoming startup trying to optimize resources or a large enterprise trying to detect intrusion, Flow logs are your best bet. You can use it for optimizing network flows, monitoring throughput, verifying compliance, detecting intrusions, and more.

IP flow verify checks if a packet is allowed or denied to or from a virtual machine. If the packet is denied by a security group, the name of the rule that denied the packet is returned.

IP flow verify looks at the rules for all Network Security Groups (NSGs) applied to the network interface, such as a subnet or virtual machine NIC. Traffic flow is then verified based on the configured settings to or from that network interface. IP flow verify is useful in confirming if a rule in a Network Security Group is blocking ingress or egress traffic to or from a virtual machine.

Therefore, you have to use the NSG flow logs to capture information about the IP traffic going to and from a network security group.

Conversely, to diagnose connectivity issues to or from an Azure virtual machine, you need to use IP flow verify.

Next hop is incorrect because this simply helps you determine if traffic is being directed to the intended destination, or whether the traffic is being sent nowhere.

Traffic analytics is incorrect because this just allows you to process your NSG Flow Log data that enables you to visualize, query, analyze, and understand your network traffic.

## SKU of load balancer for Health Probe

**Q 4-21**
![Alt text](image-131.png)

You provisioned two groups of virtual machines containing 5 virtual machines each where the traffic must be load balanced to ensure the traffic are evenly distributed.

Which of the following health probes are not available for TD2?

![Alt text](image-130.png)

Remember that although cheaper, load balancers with the basic SKU have limited features compared to a standard load balancer. **Basic load balancers are only useful for testing in development environments** but when it comes to production workloads, you need to upgrade your basic load balancer to standard load balancer to fully utilize the features of Azure Load Balancer.

Take note, the protocols supported by the health probes of a basic load balancer only support HTTP and TCP protocols.

Hence, the correct answer is: HTTPS.

---

https://docs.microsoft.com/en-us/azure/load-balancer/load-balancer-overview

https://docs.microsoft.com/en-us/azure/load-balancer/skus

Certainly! Let's talk about **Azure Load Balancer SKUs**. Azure Load Balancer provides different **Service Level Agreements (SLAs)** and features based on the SKU you choose. Here's a comparison between the **Standard** and **Basic** SKUs:

1. **Standard Load Balancer**:
    - **Scenario**: Designed for load-balancing network layer traffic when high performance and ultra-low latency are needed.
    - **Backend Type**: IP-based or NIC-based.
    - **Protocol**: Supports TCP and UDP.
    - **Backend Pool Endpoints**: Includes any virtual machines or virtual machine scale sets in a single virtual network.
    - **Health Probes**: Supports TCP, HTTP, and HTTPS.
    - **Health Probe Down Behavior**: TCP connections stay alive on an instance probe down and on all probes down.
    - **Availability Zones**: Zone-redundant and zonal frontends for inbound and outbound traffic.
    - **Diagnostics**: Azure Monitor multi-dimensional metrics.
    - **HA Ports**: Available for Internal Load Balancer.
    - **Security**: Closed to inbound flows by default unless allowed by a network security group.
    - **Outbound Rules**: Declarative outbound NAT configuration.
    - **Multiple Front Ends**: Supports both inbound and outbound.
    - **Management Operations**: Most operations complete in less than 30 seconds.
    - **SLA**: 99.99%.
    - **Global VNet Peering Support**: Available.
    - **NAT Gateway Support**: Supported.
    - **Private Link Support**: Supported.
    - **Global Tier**: Supports cross-region load balancing for Public Load Balancers.

2. **Basic Load Balancer**:
    - **Scenario**: Suitable for small-scale applications that don't need high availability or redundancy.
    - **Backend Type**: NIC-based.
    - **Protocol**: Supports TCP and UDP.
    - **Backend Pool Endpoints**: Limited to virtual machines in a single availability set or virtual machine scale set.
    - **Health Probes**: Supports TCP and HTTP.
    - **Health Probe Down Behavior**: TCP connections stay alive on an instance probe down. All TCP connections end when all probes are down.
    - **Availability Zones**: Not compatible with availability zones.
    - **Diagnostics**: Not supported.
    - **HA Ports**: Not available.
    - **Security**: Open by default.
    - **Outbound Rules**: Not available.
    - **Multiple Front Ends**: Inbound only.
    - **Management Operations**: Typically take 60-90+ seconds.
    - **SLA**: Not available.
    - **Global VNet Peering Support**: Not supported.
    - **NAT Gateway Support**: Not supported.
    - **Private Link Support**: Not supported.
    - **Global Tier**: Not supported.

Remember that Basic Load Balancer will be retired on September 30, 2025, so if you're currently using it, consider upgrading to Standard Load Balancer before that date .


## Packet Capture

Q-22
![Alt text](image-132.png)

You plan to record all sessions to track traffic to and from your virtual machines for a period of 3600 seconds.

:x: Solution: Create a connection monitor in Azure Network Watcher.
> The solution provided is to set up a Connection Monitor in Azure Network Watcher. Connection Monitor’s primary use case is to track connectivity between your on-premises setups and the Azure VMs/virtual machine scale sets that host your cloud application. You cannot use this feature to capture packets to and from your virtual machines in a virtual network because it is not supported

:x: Solution: Use IP flow verify in Azure Network Watcher.
> The provided solution is to use IP flow verify in Azure Network Watcher. 
> The main use case of IP flow verify is to determine whether a packet to or from a virtual machine is allowed or denied based on 5-tuple information and not to capture packets from your virtual machines for a period of 3600 seconds or 1 hour.

:o: Solution: Configure a packet capture in Azure Network Watcher.

![Alt text](image-133.png)
With Packet Capture, you can create packet capture sessions to track traffic to and from a virtual machine. It also helps diagnose network anomalies both reactively and proactively. But in order to use this feature, the virtual machine must have the Azure Network Watcher extension.

The packet capture output (.cap) file can be saved in a storage account and/or on the target virtual machine. You can also filter the protocol, IP addresses, and ports when adding a packet capture. Keep in mind that the maximum duration of capturing sessions is 5 hours.


## Create DNS Zone & Record

Q 4-29
Your organization has a domain named `tutorialsdojo.com`.

You want to host your records in Microsoft Azure.

Which three actions should you perform?


You can use Azure DNS to host your DNS domain and manage your DNS records. By hosting your domains in Azure, you can manage your DNS records by using the same credentials, APIs, tools, and billing as your other Azure services.

Since you own tutorialsdojo.com from a domain name registrar you can then create a zone with the name tutorialsdojo.com in Azure DNS. Since you’re the owner of the domain, your registrar allows you to configure the Nameserver (NS) records to your domain allowing internet users around the world are then directed to your domain in your Azure DNS zone whenever they try to resolve tutorialsdojo.com.

The steps in registering your Azure public DNS records are:

Create your Azure public DNS zone
Retrieve name servers – Azure DNS gives name servers from a pool each time a zone is created.
Delegate the domain – Once the DNS zone gets created and you have the name servers, you’ll need to update the parent domain with the Azure DNS name servers.
Hence, the correct answers are:

– Create an Azure public DNS zone

– Update the Azure NS records to your domain registrar

– Copy the Azure DNS NS records

The options that say: Copy the Azure DNS A records and Update the Azure A records to your domain registrar is incorrect because you need to copy the nameserver records instead of the A record. An A record is a type of DNS record that points a domain to an IP address.

The option that says: Create an Azure private DNS zone is incorrect because this simply manages and resolves domain names in the virtual network without the need to configure a custom DNS solution. The requirement states that the users must be able to access tutorialsdojo.com via the internet. You need to deploy an Azure public DNS zone instead.

https://docs.microsoft.com/en-us/azure/dns/dns-overview

https://docs.microsoft.com/en-us/azure/dns/dns-getstarted-portal


## Azure Network Watcher

![Alt text](image-143.png)

TD1 is unable to connect to TD4 via port 443. You need to troubleshoot why the communication between the two virtual machines is failing.  

Connection troubleshoot helps reduce the amount of time to diagnose and troubleshoot network connectivity issues. The results returned can provide insights about the root cause of the connectivity problem and whether it’s due to a platform or user configuration issue.

Connection troubleshoot reduces the Mean Time To Resolution (MTTR) by providing a comprehensive method of performing all connection major checks to detect issues pertaining to network security groups, user-defined routes, and blocked ports.

IP flow verify checks if a packet is allowed or denied to or from a virtual machine. If the packet is denied by a security group, the name of the rule that denied the packet is returned.

IP flow verify looks at the rules for all Network Security Groups (NSGs) applied to the network interface, such as a subnet or virtual machine NIC. Traffic flow is then verified based on the configured settings to or from that network interface. IP flow verify is useful in confirming if a rule in a Network Security Group is blocking ingress or egress traffic to or from a virtual machine.

Therefore, the correct answers are:

– Connection troubleshoot

– IP flow verify

Effective security rules is incorrect because this simply allows you to see all inbound and outbound security rules that apply to a virtual machine’s network interface. This is also used for security compliance and auditing.

Azure Diagnostics is incorrect because it is an agent in Azure Monitor that collects monitoring data from the guest operating system of Azure compute resources, including virtual machines.

Log Analytics is incorrect because this is just a tool to edit and run log queries from data collected by Azure Monitor logs and interactively analyze their results.

VPN troubleshoot is incorrect because this only provides the capability to troubleshoot virtual network gateways and their connections. This is primarily used for diagnosing the traffic between your on-premises resources and Azure virtual networks.

## dynamic/static public IP address x routine maintenance

You have an Azure subscription containing an Azure virtual machine named `Siargao` with an assigned dynamic public IP address.

During routine maintenance, `Siargao` was deallocated and then started again.

The development team reports that their application hosted on `Siargao` has lost its connection with an external service. 

The external service whitelists the IP addresses allowed to access it. 

You suspect the public IP address has changed during the maintenance.

What should you do?


![Alt text](image-148.png)


Public IP addresses allow Internet resources to communicate inbound to Azure resources. Public IP addresses enable Azure resources to communicate with the Internet and public-facing Azure services. The address is dedicated to the resource until it’s unassigned by you. A resource without a public IP assigned can communicate outbound.

IP addresses in Azure can be either dynamic or static. By default, Azure assigns a dynamic IP address to the VM. When the VM is started, Azure assigns it an IP address, and when the VM is stopped (deallocated), that IP address is returned to the pool and can be assigned to a different VM. This means that when you stop and start a VM, it can get a different public IP address, which can cause problems if you have systems or services that rely on the specific IP address of that VM, such as an external service that whitelists specific IP addresses.

A static IP address, unlike a dynamic IP address, does not change when the VM is deallocated. Once a static IP address is assigned to a VM, that IP is reserved for the VM and won’t be assigned to any other VM, even when the original VM is stopped. This means the VM would keep the same IP address throughout its lifecycle, regardless of its state.

In this case, to solve the issue, we need to modify Siargao to use a static public IP address instead of a dynamic public IP address.

Hence, the correct answer is: Modify Siargao to use a static public IP address.

The statement that says: Enable an Azure VPN gateway for Siargao is incorrect. Azure VPN Gateway is used to establish secure, cross-premises connectivity between your virtual network within Azure and your on-premises network, but it doesn’t provide static public IP functionality for individual VMs.

The statement that says: Attach multiple dynamic public IP addresses to Siargao is incorrect because assigning multiple dynamic public IP addresses would not solve the issue, as these dynamic IP addresses can still change when the VM is deallocated.

The statement that says: Provision an Azure NAT gateway to provide outbound internet connectivity is incorrect because Azure NAT Gateway is a service that provides outbound-only internet connectivity for the VMs in your virtual network. However, it doesn’t help in maintaining the same public IP address of a VM during its deallocation and reallocation.  

https://learn.microsoft.com/en-us/azure/virtual-network/ip-services/public-ip-addresses

https://learn.microsoft.com/en-us/azure/virtual-network/ip-services/default-outbound-access

## Site Recovery

Your company is currently running a mission-critical application in a primary Azure region.

You plan to implement a disaster recovery by configuring failover to a secondary region using Azure Site Recovery.

What should you do?

![Alt text](image-149.png)
Enabling replication for a virtual machine (VM) for disaster recovery purposes involves installing the Site Recovery Mobility service extension on the VM and registering it with Azure Site Recovery. During replication, any disk writes from the VM are first sent to a cache storage account in the source region. Subsequently, the data is transferred to the target region, where recovery points are generated from it. During a disaster recovery failover of the VM, a recovery point is used to restore the VM in the target region.

Here’s how to set up disaster recovery for a VM with Azure Site Recovery:

First, you need to create a Recovery Services Vault (RSV) in the secondary region, which will serve as the target location for the VM during a failover.
Next, you need to install and configure the Azure Site Recovery agent on the VMs that you want to protect. The agent captures data changes on the VM disks and sends them to Azure Site Recovery for replication to the secondary region.
Once the replication is set up, you need to design a recovery plan that outlines the steps to orchestrate the failover and failback operations. This includes defining the order in which VMs should be failed over, any dependencies between VMs, and the desired recovery point objective (RPO) and recovery time objective (RTO) for each VM.
During replication, VM disk writes are sent to a cache storage account in the source region, and from there to the target region, where recovery points are generated from the data. In the event of a disaster or planned failover, a recovery point is used to restore the VM in the target region, allowing the business to continue operations without significant downtime or data loss.
Hence, the correct answer is: Create an RSV in the secondary region, install and configure the Azure Site Recovery agent on the VMs, and design a recovery plan to orchestrate failover and failback operations.

The option that says: Create an RSV in the primary region, install and configure the Azure Site Recovery agent on the VMs, and design a replication policy to replicate the data to the secondary region is incorrect because although this will replicate the data to the secondary region, it does not include the necessary steps to perform failover. You still need to create a Recovery Services vault in the secondary region, not the primary region, to perform failover.

The option that says: Create a virtual network and subnet in the secondary region, install and configure the Azure Site Recovery agent on the VMs, and design a recovery plan to orchestrate failover and failback operations is incorrect because, just like the other options, you will still need to create a Recovery Services vault in the secondary region, install and configure the Azure Site Recovery agent on the virtual machines, and create a recovery plan to orchestrate failover and failback operations.

The option that says: Create an Azure Traffic Manager profile to load-balance traffic between the primary and secondary regions, install and configure the Azure Site Recovery agent on the VMs, and design a replication policy to replicate the data to the secondary region is incorrect because this will just load-balance traffic between the primary and secondary regions but won’t be able to perform failover. You will still need to create a Recovery Services vault in the secondary region to perform failover.


---

Azure Site Recovery service contributes to your business continuity and disaster recovery (BCDR) strategy by keeping your business applications online during planned and unplanned outages. Site Recovery manages and orchestrates disaster recovery of on-premises machines and Azure virtual machines (VM), including replication, failover, and recovery.

https://learn.microsoft.com/en-us/azure/site-recovery/site-recovery-overview

https://learn.microsoft.com/en-us/azure/site-recovery/azure-to-azure-quickstart

