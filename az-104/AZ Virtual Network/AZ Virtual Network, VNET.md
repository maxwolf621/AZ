{%hackmd @Edixon/dracula %}
# AZ Virtual Network, VNET

[TOC]

![image](https://hackmd.io/_uploads/rkoxq_sIa.png)

## Vnet Peering

Encapsulate the Vnets (in the same region)  

![image](https://hackmd.io/_uploads/HyWQ5OoUT.png)


## Network Interface 

Software or hardware interface btw two pieces of equipment or protocol layers in a computer network.  

### Network Interface Controller 

![image](https://hackmd.io/_uploads/SJyR5diI6.png)


## Route Table

![image](https://hackmd.io/_uploads/SynljuoIT.png)

### Override the Default System Table

![image](https://hackmd.io/_uploads/SkY4jusU6.png)

Route table creation
`Route Tables | Add`  
![image](https://hackmd.io/_uploads/rkwRvEhUp.png)

Override the subnet in specific virtual machine 
`Route talbe | Settings | Subnets` 
- Override the subnet named `default` in virtual machine named `Cardassia-vnet`

Refresh the subnet in virtual machine
`Virutal network#Cardassia-vnet | Setting | Subnets`
![image](https://hackmd.io/_uploads/BJdgo43Up.png)

Add Route 
`Route Tables#resource_name | Routes`
![image](https://hackmd.io/_uploads/ryF3WrnL6.png)


### Address Space

![image](https://hackmd.io/_uploads/HkLiodjI6.png)


## Subnets

![image](https://hackmd.io/_uploads/BySVJKiLp.png)

## Private Link

Keep Everything (e.g resources, VMs, On-Premise.) within Azure Network.  

![image](https://hackmd.io/_uploads/SyHelFiIT.png)

## ExpressRoute

Azure ExpressRoute is a service (like a colocation facility) that enables you to extend your on-premises networks into the Microsoft cloud over a private connection facilitated by a connectivity provider.  

![image](https://hackmd.io/_uploads/Syg_ZYi8T.png)  

## Firewall 

![image](https://hackmd.io/_uploads/rkL20Wh8T.png)

Once a virtual machine is created, it also create virtual network.  

Before creating a fire wall you should already setup the following configuration in a virtual machine resource :arrow_down:  
#### Create Address Space  
`Virtual network#resource_name | Settings | Address Space`  

#### Create subnet  
`Virtual network#resource_name | Settings | Subnets | subnet`

![image](https://hackmd.io/_uploads/HknmRGnIp.png)

Once a firewall service's resource is deployed.  

We can check resource group to make sure if deployment has succeeded or not.   
![image](https://hackmd.io/_uploads/rkj5LE28T.png)  


### Rule Setup 

#### Types

1. DNAT (Destination Network Address Translation) Rules:
These rules redirect **inbound traffic from the public IP address of Azure Firewall to specific private IP addresses within your VNet.**  
Useful for exposing internal services with private IP addresses to the internet without publicly revealing their actual addresses.  
    - e.g. Forwarding web traffic to a web server, RDP connections to a specific VM, or SSH access to a management machine.
2. Network Rules:
These rules **filter inbound and outbound traffic based on source and destination IP addresses, ports, protocols** (TCP, UDP, etc.), and other network properties.
Offer granular control over what traffic can enter and leave your VNet.
    > e.g. Blocking specific IP addresses, allowing outbound traffic only to specific domains, or limiting certain ports for inbound connections.
3. Application Rules:
These rules **inspect traffic at the application layer** (deep packet inspection) based on protocols, application signatures, and web categories.
Provide advanced security by blocking malicious content and unwanted applications.
    > e.g blocking malware, preventing data exfiltration, or restricting access to social media and streaming services.

![image](https://hackmd.io/_uploads/SJZlPU2UT.png)  


### Network

`Setting |Networking | Network Interface`

## Network Watcher

Virtualize the VNets

![image](https://hackmd.io/_uploads/HJTt1Gn8T.png)

`Virtual Machine#name | Support + Troubleshooting | Connection troubleshoot`  
![image](https://hackmd.io/_uploads/B1KXIt28a.png)  

`Network Watcher | Network diagonistic tools`
`Network Watcher | Monotoring | Topology`

### NSG diagnostic 

[NSG diagnostics overview
](https://learn.microsoft.com/en-us/azure/network-watcher/network-watcher-network-configuration-diagnostics-overview)

### Packet Capture

`Network Watcher | Network diagonistic tools | Packet capture`
  
Capture Configuration  
![image](https://hackmd.io/_uploads/Bkxm7hF2I6.png)  

Download the cap file (the format can be opened by `wireshark`)  
![image](https://hackmd.io/_uploads/HJmOnY28T.png)  

### NSG flow logs 


Creation NSG flow logs resource  
![image](https://hackmd.io/_uploads/BkumpK3L6.png)

![image](https://hackmd.io/_uploads/HJPvaK3IT.png)

## Network Performance Monitor

it is a cloud-based hybrid network monitoring solution in network infrastructure.  

Creation 
`Log Analytics Workspace | NPM resource`

![image](https://hackmd.io/_uploads/Hk4Ihzn86.png)

## Cheatsheet 

![image](https://hackmd.io/_uploads/ryfQAFhUT.png)
![image](https://hackmd.io/_uploads/H1zBCt286.png)
![image](https://hackmd.io/_uploads/H16OCF2Ip.png)

