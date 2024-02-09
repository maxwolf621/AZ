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