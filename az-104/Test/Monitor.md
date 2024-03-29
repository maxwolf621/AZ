# Monitor and Maintain Azure Resources

## AZ Net Watcher NSG Flow logs & IP Flow Verify

https://docs.microsoft.com/en-us/azure/network-watcher/network-watcher-monitoring-overview

https://docs.microsoft.com/en-us/azure/network-watcher/network-watcher-ip-flow-verify-overview


NSG Flow Logs:
- allow you to log network traffic passing through your `Network Security Groups` (NSGs).
These logs capture information about inbound and outbound traffic, including details like source and destination IP addresses, ports, and protocol.

Key points:
- Source IP address for communication is logged.
- Rule counter information is recorded.
- Useful for diagnosing traffic filtering issues at the level of:
  - Virtual machines.
  - Virtual machine scale sets.
  - Application gateways.

Storage:
- NSG flow log data is written to an Azure Storage account.

IP Flow Verify:
- helps you diagnose connectivity issues related to virtual machine connectivity.
- It checks whether a packet is allowed or denied to or from an Azure virtual machine based on the configured security and admin rules.

![alt text](image-251.png)

**IP flow verify first looks at the rules for all Network Security Groups (NSGs) applied to the network interface**, such as a subnet or virtual machine NIC.   
Traffic flow is then verified based on the configured settings to or from that network interface.   

<font color="red">It is useful in confirming if a rule in a Network Security Group is blocking ingress or egress traffic to or from a virtual machine.</font>  

---

:question: 3-40

Adatum Corporation hosts its applications in their Singapore datacenter. 

The Singapore datacenter consists of the following servers:  
![alt text](image-252.png)  

Your network contains an Active Directory forest named adatum.com. 

All servers and client computers are joined to Active Directory.

A private connection is used for traffic in between offices. Each office has a network device that can be used for VPN connections.

`Adatum` uses two web applications named `AdatumApp1` and `AdatumApp2`.

:m: Planned Changes
Adatum Corporation plans to implement the following modifications for their migration to Azure:
1. Establish a private connection to Azure from the headquarters in Singapore.
2. Move the virtual machines located in the Singapore datacenter to Azure.
3. Move AdatumApp1 and AdatumApp2 to two Azure App Service named AdatumWeb1 and AdatumWeb2.
4. Ensure that the on-premises active directory is synchronized with Azure Active Directory.


Technical Requirements
1. Minimize administrative effort and cost whenever possible.
2. Ensure that the information technology department receives an email whenever the CPU utilization `vm3.adatum.com` reaches 75%.
3. Ensure that you create an Azure custom role named AdatumAdministrator that is based on the built-in Contributor role.  
4. Enable Multi-Factor Authentication (MFA) for the information technology department only.  
5. The servers in the Montreal office must be able to establish a connection over port `443` to `vm3.adatum.com`.  
6. Ensure that the London office can send encrypted traffic to Azure over the public internet.  
7. Ensure that `AdatumWeb2` can automatically increase the number of instances based on CPU utilization.  
8. According to the sales department, `vm3.adatum.com` does not have connectivity to the Montreal office.  

You need to determine if a network security group is causing the issue.

What Azure Network Watcher feature should you use?  
- NSG Flow Logs
- Traffic Analytics
- Next hop
- IP flow verify

:o: IP flow verify

:x: NSG Flow Logs is incorrect. 
- It is only a feature of Azure Network Watcher that allows you to log information about IP traffic flowing through a network security group.

## Alert Rule x action group

An action group is a collection of notification preferences set by the Azure subscription's owner.

**an action group is a global service, it is not bound to a specific Azure region and can handle any client requests.**
- For example, if one region of the action group service is unavailable, traffic is routed and processed by other regions.
- A catastrophe recovery solution is provided by an action group as a global service.

When you use the Email Azure Resource Manager role type of notification, you can send email to members of a subscription's role.  
- Emails are only sent to Azure AD user members who are members of the role.   
- Azure AD groups and service principals are not emailed.   
- Also, a notification email will only be sent to the primary email address.  

https://learn.microsoft.com/en-us/azure/azure-monitor/alerts/action-groups#email-azure-resource-manager-role

https://learn.microsoft.com/en-us/azure/azure-monitor/alerts/action-groups

---

:question: 3-45 

Your organization Azure subscription contains the following identities:  
![alt text](image-254.png)  

You created an alert rule and configured an action group with the `notification type Email Azure Resource Manager Role`, which sends an email to the `Monitoring Reader role`.

The Monitoring Reader role is assigned to the user, service principal and group. 

:a: : 

:o: the correct answer is: TDU3.
![alt text](image-255.png)

All of the other options are incorrect 
- because only TDU3 will able to receive the email notification since emails are only sent to Azure AD user members who are members of the role.  

## backup policy in Recovery Services Vault Resource setup

To create a backup policy, you need to create a Recovery Services vault first. 

Take note that the services supported by Azure Backup are virtual machine, file share, SQL server, and SAP HANA. 

Based on the given policy, the retention period for monthly backup is 36 months. 

Since January 15 is not configured as a yearly backup point, this backup is considered a monthly backup.

- The created backup on January 15 will be retained for 36 months.
- The created backup on December 15 will be retained for 5 Years.

## Change the RSV of a VM

You can use Recovery Services vaults to hold backup data for various Azure services such as `IaaS VMs (Linux or Windows)` and `Azure SQL databases`. 

Recovery Services vaults support `System Center DPM`

To change the Recovery Services vault of a virtual machine, you need to stop the backup first **since Azure VMs may only be assigned a single Recovery Services Vault (RSV) at a time. After the backup stops**, you can now assign a new vault to your VM. 

![alt text](image-257.png)

Reference :
https://learn.microsoft.com/en-us/azure/backup/backup-azure-arm-vms-prepare

https://learn.microsoft.com/en-us/azure/backup/backup-azure-recovery-services-vault-overview

---

:question: 3-49

You have been assigned to manage two Azure VMs and Recovery Services vaults.  

Both VMs currently store back up to a single vault.     

You must configure the other VM to backup in a different vault.  

**ANS :**
Stop the backup of one VM.

:x: Delete the backup data is incorrect 
- because you need to stop the backup before you can delete the backup data.

:x: Change the VM target vault is incorrect
- because you also need to stop the backup of one VM to change the RSV.

:x: Stop the backup of both VM is incorrect 
- because you don't need to stop the backup of both VMs to change the vault of one VM.


## :O RSV for resources

 
---

:question: 3-50
Your company Azure Subscription contains the following resources:  

![Alt text](image-109.png)  

You have created a file share named `FS1` and a blob container named `BC1`.  

Which of the following resources can be backed up in the RSVs?  
- Backups can be performed using `RSV1` ?  
- Backups can be performed using `RSV2` ?  

:a: :

In this scenario, you need to identify which resources can be backed up by RSV1 and RSV2.

**The first thing that you need to take a look at is the location or region of the resource.**   
- Since you can only backup using RSV if the resource and vault are in the same location.

You can only use Recovery Services vaults to hold backup data for various Azure services such as `IaaS VMs (Linux or Windows)` and `SQL Server` in Azure VMs. 
![Alt text](image-110.png)

After knowing which resources can be backed up using RSV, the remaining resources would be VM and File Share.

## Azure Backup & How to Restore VM

Azure Backup 
- **takes a snapshot of the existing VM before replacing the disk, and stores it in the staging location you specify.**    
- The existing disks connected to the VM are replaced with the selected restore point.
![Alt text](image-112.png)  

:mag: snapshot
**The snapshot is copied to the vault, and retained in accordance with the retention policy.**   
- After the replace disk operation, the original disk is retained in the resource group.  
- You can choose to manually delete the original disks if they aren’t needed.  

Azure Backup provides several ways to restore a VM:  
- Create a new VM
Quickly creates and gets a basic VM up and running from a restore point.  
- Restore disk 
Restores a VM disk, which can then be used to create a new VM.  
- Replace existing disk (on the existing VM)
Restore a disk, and use it to replace a disk on the existing VM.
- Cross-Region (Secondary Region)
Restore Azure VMs in the secondary region, which is an Azure paired region.

https://docs.microsoft.com/en-us/azure/backup/backup-azure-arm-restore-vms

https://docs.microsoft.com/en-us/azure/backup/backup-azure-vms-first-look-arm

---

**Q 4-2**
Your company eCommerce website is deployed in an Azure virtual machine named `TD-BGC`.

You created a backup of the TD-BGC and implemented the following changes:
- Change the local admin password.
- Create and attach a new disk.
- Resize the virtual machine.
- Copy the log reports to the data disk.

You received an email that the admin restore the `TD-BGC` using the `replace existing` configuration.  

Which options should you perform to bring back the changes in TD-BGC?  
- Create and attach a new disk.
- Change the local admin password.
- Resize the virtual machine.
- Copy the log reports to the data disk.

:a: 

:o: Copy the log reports to the data disk.
**Since you restore the VM using the backup data, the new disk won't have a copy of the log reports.**  
- To bring back the changes in the `TD-BGC` virtual machine, you will need to copy the log reports to the disk.  

:x: Change the local admin password is incorrect 
- because the new password will not be overridden with the old password using the restore VM option. Therefore, you can use the updated password to connect via RDP to the machine.

:x: Create and attach a new disk is incorrect 
- because the new disk does not contain the log reports. Instead of creating a new disk, you should attach the existing data disk that contains the log reports.

:x: Resize the virtual machine is incorrect 
- because the only changes that will retain after rolling back are the VM size and the account password.

## :star2::star2: A Recovery Services Configuration  

https://docs.microsoft.com/en-us/azure/site-recovery/tutorial-prepare-azure-for-hyperv

https://docs.microsoft.com/en-nz/azure/site-recovery/hyper-v-azure-tutorial

https://docs.microsoft.com/en-us/windows-server/virtualization/hyper-v/hyper-v-technology-overview

:question: 4-12

Your company created several Azure virtual machines and a file share in the subscription `TD-Boracay`.   

Condition
The VMs are all part of the same virtual network.  

Requirement : 
You have been assigned to manage the `on-premises Hyper-V` server replication to Azure.

To support the planned deployment, you will need to create additional resources in `TD-Boracay`.

Which of the following options should you create?
- VNet Service Endpoint
- Azure Storage Account
- Hyper-V site
- Azure ExpressRoute
- Azure Recovery Services Vault
- Replication Policy

:a: : 

To set up disaster recovery of `on-premises Hyper-V` VMs to Azure, you should complete the following steps:

:one: Select your replication source and target 
- To prepare the infrastructure, you will need to create a Recovery Services vault Resource. 

After you created the vault, you can now accomplish the protection goal, as shown in the image below :arrow_down:.
![Alt text](image-122.png)

:two: Set up the source replication environment, including on-premises Site Recovery components and the target replication environment 
- to set up the source environment, you need to create a Hyper-V site and add to that site the Hyper-V hosts containing the VMs that you want to replicate. 
- The target environment will be the subscription and the resource group in which the Azure VMs will be created after failover.

:three: Create a replication policy

:four: Enable replication for a VM

---

https://docs.microsoft.com/en-us/azure/site-recovery/tutorial-prepare-azure-for-hyperv

https://docs.microsoft.com/en-nz/azure/site-recovery/hyper-v-azure-tutorial

https://docs.microsoft.com/en-us/windows-server/virtualization/hyper-v/hyper-v-technology-overview

A Recovery Services vault is a management entity that stores recovery points created over time and provides an interface to perform backup-related operations.

A replication policy defines the settings for the retention history of recovery points. The policy also defines the frequency of app-consistent snapshots.

## The Linux Diagnostic Extension For METRIC & LOG

https://docs.microsoft.com/en-us/azure/virtual-machines/extensions/diagnostics-linux

https://docs.microsoft.com/en-us/azure/azure-monitor/platform/diagnostics-extension-overview

Azure Diagnostics extension is an agent in Azure Monitor that collects monitoring data from the guest operating system of Azure compute resources including virtual machines. It collects guest metrics into Azure Monitor Metrics and sends guest logs and metrics to Azure storage for archiving.  

Azure Performance Diagnostics VM Extension helps collect performance diagnostic data from Windows VMs. 
The extension performs analysis and provides a report of findings and recommendations to identify and resolve performance issues on the virtual machine.  

---

**:question: 4-18**

You deployed an Ubuntu server using an Azure virtual machine.  

You need to monitor the system performance metrics and log events.  

:a: : 

The Linux Diagnostic Extension will help you monitor the health of a Linux VM running on Microsoft Azure. 

With this extension, you can now monitor the system performance metrics and log events of the virtual machine.

It has the following capabilities:
- Collects system performance metrics from the VM and stores them in a specific table in a designated storage account.
- Retrieves log events from syslog and stores them in a specific table in the designated storage account.
- Enables users to customize the data metrics that are collected and uploaded.
- Enables users to customize the syslog facilities and severity levels of events that are collected and uploaded.
- Enables users to upload specified log files to a designated storage table.
- Supports sending metrics and log events to arbitrary EventHub endpoints and JSON-formatted blobs in the designated storage account.

Hence, the correct answer is: Linux Diagnostic Extension.

:x: Azure Performance Diagnostics VM Extension is incorrect
- because this extension only collects performance diagnostic data from Windows VMs.

:x: Boot diagnostics is incorrect 
- because this feature is **primarily used to diagnose VM boot failures** and not for monitoring the system performance metrics and log events.

:x: Connection monitor is incorrect 
- because this is simply used for end-to-end connection monitoring.


## Azure Monitor Networks 

**Q 4-19**
You have an Azure subscription that contains hundreds of network resources.

You need to recommend a solution that will allow you to monitor resources in **one centralized console** for network monitoring.

What solution should you recommend?
- Azure Advisor
- Azure Monitor Network Insights
- Azure Traffic Manager
- Azure Virtual Network

**ANS :**
the correct answer is: Azure Monitor Network Insights.

---

![Alt text](image-128.png)

Azure Monitor Network Insights provides a **comprehensive view of health and metrics for all deployed network resources without requiring any configuration.**  

**It also provides access to network monitoring capabilities like Connection Monitor, flow logging for network security groups (NSGs), and Traffic Analytics.** And it provides other network diagnostic features. 

Key features of Network Insight:
- Single console for network monitoring
- No agent configuration required
- Access to health state, metrics, alerts, & data from traffic and connectivity monitoring tools in one place
- View network topology with functional dependencies for simpler troubleshooting
- Access resources metrics to debug issues without writing queries or authoring workbooks

:x: Azure Traffic Manager is incorrect because this is simply a DNS-based traffic load balancer that enables you to distribute traffic optimally to services across global Azure regions while providing high availability and responsiveness. However, you cannot use this to monitor your network resources.

:x: Azure advisor (錢+安全性) is incorrect because this service just helps you improve the cost-effectiveness, performance, reliability (formerly called high availability), and security of your Azure resources.

## Azure Application Insights Service

**28.** QUESTION   
Your organization has two web applications running in different environments:
![Alt text](image-138.png)
You have been tasked to monitor the performance of the applications using Azure Application Insights.

The operation should have minimal changes to the code.

What should you do?

The main requirement in the scenario is to use Azure Application Insights to track the performance of the applications. 

But the condition is to implement it with minimal changes in the code. 

That is why the first approach satisfies the requirement since you only need to install the agent in the machine.

The option that says: Install the Application Insights SDK is incorrect because, in order to implement this method, you will need to do some changes in the application code. Take note that the requirement is to implement monitoring with minor changes in the code.

The option that says: Install the Windows Azure VM Agent is incorrect because this won’t help you track the performance of the application. The VM agent is commonly used when you need to create a backup of the virtual machine. Therefore, this option is incorrect and won’t satisfy the requirement in the scenario.

The option that says: Install the Azure Monitor Agent is incorrect because it is already indicated in the scenario that you need to use Azure Application Insights to track the performance of the application. Also, the Azure Application Insights is a feature of Azure Monitor. Hence, this method is incorrect and will not meet the given requirement in the scenario.

---

https://docs.microsoft.com/en-us/azure/azure-monitor/app/app-insights-overview

https://docs.microsoft.com/en-us/azure/azure-monitor/app/azure-web-apps

https://docs.microsoft.com/en-us/azure/azure-monitor/app/status-monitor-v2-overview

Application Insights is a feature of Azure Monitor that provides extensible application performance management (APM) and monitoring for live web apps. It also supports a wide variety of platforms, including .NET, Node.js, Java, Python and works for apps hosted on-premises, hybrid, or on any public cloud.
![Alt text](image-139.png)

There are two ways to enable application monitoring for hosted applications:

1. Agent-based application monitoring (Application Insights Agent)

– This method is the easiest to enable, you only need to install the Application Insights Agent, and code changes or advanced configurations are not required.

2. Manually instrumenting the application through code (Application Insights SDK)

– The alternative approach is you need to install the Application Insights SDK. This means that you have to manage the updates to the latest version of the packages by yourself. The second method is recommended if you need to make custom API calls to track events/dependencies not captured by default with agent-based monitoring.

## :star2: AZ Monitor Log Analytics Workspace for Storage Backup

:memo: What is Azure Backup Report
- Azure Backup Report provides a **reporting solution that uses Azure `Monitor logs` and Azure `workbooks`**.  
- These resources help you get rich insights on your backups across your entire backup estate.   

:memo: Region & Subscription for Azure Monitor Log Analytics workspace
- <font color="red"> When you create a Log Analytics workspace, it does not matter if the vault is located in a different region or subscription. </font>

:memo: A common requirement for backup admins is to obtain insights on backups **based on data that spans a long period of time.**   

:memo: Use cases for such a solution include :

Backup Reports serve as a one-stop destination for tracking usage for 
- `Allocating` and `Forecasting` of cloud STORAGE consumed.
- `Auditing` of backups and restores.
- `Identifying Key Trends` at different levels of granularity.

:memo: Retention Of Log Analytics Data 
- **By default, the data in a Log Analytics workspace is retained for 30 days.**   
- To see data for a longer time horizon, change the retention period of the Log Analytics workspace.  

---

:question: 3-11
There is a requirement that requires you to configure Azure Backup reports using `TDBackup1` to determine which backup items consume the most storage.  

![alt text](image-238.png)

:a: : 

:o: the correct answer is: `TDAnalytics1`, `TDAnalytics2`, and `TDAnalytics3`.

## :star: RSV backup pre-checks

:question: 4-24

Your company has a web app hosted in Azure Virtual Machine.

You plan to create a backup of TD-VM1 but the backup pre-checks displayed a warning state.

What could be the reason?

:a: :

![alt text](image-263.png)

Backup Pre-Checks, as the name implies, check the configuration of your VMs for issues that may affect backups and aggregate this information so that you can view it directly from the Recovery Services Vault dashboard. It also provides recommendations for corrective measures to ensure successful file-consistent or application-consistent backups, wherever applicable.

Backup Pre-Checks are performed as part of your Azure VMs’ scheduled backup operations and result in one of the following states:

Passed: This state indicates that your VMs configuration is conducive for successful backups and no corrective action needs to be taken.
Warning: This state indicates one or more issues in VM’s configuration that might lead to backup failures and provides recommended steps to ensure successful backups. Not having the latest VM Agent installed, for example, can cause backups to fail intermittently and falls in this class of issues.
Critical: This state indicates one or more critical issues in the VM’s configuration that will lead to backup failures and provides required steps to ensure successful backups. A network issue caused due to an update to the NSG rules of a VM, for example, will fail backups as it prevents the VM from communicating with the Azure Backup service and falls in this class of issues.
As stated above, the reason why backup pre-checks displayed a warning state is because of the VM agent. The Azure VM Agent for Windows is automatically upgraded on images deployed from the Azure Marketplace. As new VMs are deployed to Azure, they receive the latest VM agent at VM provision time.

If you have installed the agent manually or are deploying custom VM images you will need to manually update to include the new VM agent at image creation time. To check for the Azure VM Agent in your machine, open Task Manager and look for a process name WindowsAzureGuestAgent.exe.

Hence, the correct answer is: The latest VM Agent is not installed in TD-VM1.

The option that says: The Recovery Services vault lock type is read-only is incorrect because you can’t create a backup if the configured lock type is read-only. If you attempted to backup a virtual machine with a resource lock, the operation won’t be performed, and notify you to remove the lock first.

The option that says: The TD-VM1 data disk is unattached is incorrect because you don’t need to attach a data disk to the virtual machine when creating a backup. To enable VM backup, you need to have a VM agent and Recovery Services vault.

The option that says: The status of TD-VM1 is deallocated is incorrect because you can still create a backup even if the status of your virtual machine is stopped (deallocated).

References:

https://docs.microsoft.com/en-us/azure/backup/backup-azure-arm-vms-prepare

https://azure.microsoft.com/en-us/blog/azure-vm-backup-pre-checks

https://github.com/MicrosoftDocs/azure-docs/blob/main/articles/backup/backup-azure-manage-windows-server.md

## 

:question: 4-28

Your organization has two web applications running in different environments:

![alt text](image-264.png)

You have been tasked to monitor the performance of the applications using Azure Application Insights.

The operation should have minimal changes to the code.

What should you do?
- TDWebApp1 
- TDWebApp2

:a: :

The main requirement in the scenario is to use Azure Application Insights to track the performance of the applications. 

But the condition is to implement it with minimal changes in the code. 

That is why the first approach satisfies the requirement since you only need to install the agent in the machine.

![alt text](image-265.png)

There are two ways to enable application monitoring for hosted applications:

Agent-based application monitoring (Application Insights Agent)
- This method is the easiest to enable, you only need to install the Application Insights Agent, and code changes or advanced configurations are not required.

Manually instrumenting the application through code (Application Insights SDK)
- The alternative approach is you need to install the Application Insights SDK. 
- This means that you have to manage the updates to the latest version of the packages by yourself. The second method is recommended if you need to make custom API calls to track events/dependencies not captured by default with agent-based monitoring.


:x: Install the Application Insights SDK is incorrect 
- because, in order to implement this method, you will need to do some changes in the application code. Take note that the requirement is to implement monitoring with minor changes in the code.

:x: Install the Windows Azure VM Agent is incorrect 
- because this won’t help you track the performance of the application. 
- The VM agent is commonly used when you need to create a backup of the virtual machine. 

:x: Install the Azure Monitor Agent is incorrect 
- because it is already indicated in the scenario that you need to use Azure Application Insights to track the performance of the application. 
- Also, the Azure Application Insights is a feature of Azure Monitor.

https://docs.microsoft.com/en-us/azure/azure-monitor/app/app-insights-overview

https://docs.microsoft.com/en-us/azure/azure-monitor/app/azure-web-apps

https://docs.microsoft.com/en-us/azure/azure-monitor/app/status-monitor-v2-overview
