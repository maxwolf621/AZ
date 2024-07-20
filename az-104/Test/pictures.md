![alt text](image-279.png)

![alt text](image-280.png)
![alt text](image-281.png)

![alt text](image-282.png)
Answer is B ( No )
Initial will perform a full sync and add the user account created but it will take time,
Delta, will kick off a delta sync and bring only the last change, so it will be "immediately" and will fulfill the requirements.


![alt text](image-283.png)
- On a server with Azure AD Connect installed, navigate to the Start menu and select AD Connect, then `Synchronization` Service.
- You run the Start-ADSyncSyncCycle -PolicyType Initial PowerShell cmdlet.

:x: Solution: You restart the NetLogon service on a domain controller.


![alt text](image-284.png)  
![alt text](image-285.png)  
:o: Solution: You access the Resource Group blade.
:x: Solution: You access the Container blade.


---

![alt text](image-286.png)

---

![alt text](image-287.png)
- You can simply (hot) detach a data disk from one VM and attach it to the other VM without stopping either of the VMs.

---

![alt text](image-288.png)
- The number of fault domains for managed availability sets varies by region - either two or three per region.

---

![alt text](image-289.png)
- 'Each virtual machine in your availability set is assigned an update domain and a fault domain by the underlying Azure platform. 
- **Each availability set can be configured with up to `three` fault domains and `twenty` update domains.'**

---

![alt text](image-290.png)

---

![alt text](image-291.png)

---

![alt text](image-292.png)

:x: Solution: You choose the Allow gateway transit setting on VirtualNetworkB.
:o: You download and re-install the VPN client configuration package on the Windows 10 workstation.

---

![alt text](image-293.png)

![alt text](image-294.png)

No, creating an HTTP health probe on port 1433 does not meet the goal of configuring an Azure internal load balancer as a listener for the SQL Server Always On availability group.

In order to configure an Azure internal load balancer as a listener for the availability group, you need to create a TCP health probe on port 1433. SQL Server uses TCP to communicate on port 1433, so a TCP health probe is the appropriate choice to ensure the availability and health of the SQL Server instances in the availability group.

---

![alt text](image-295.png)
Session Persistence -> Same request to same client

![alt text](image-296.png)
- Yes, enabling Floating IP on the Azure internal load balancer as a listener for the availability group can meet the goal. By enabling Floating IP, the load balancer will use a floating IP address as the source IP address for outbound flows from the backend pool. This will ensure that the IP address used by the backend pool remains the same even if a VM is restarted or replaced, which is important for maintaining the listener for the availability group.

![alt text](image-297.png)
- The answer is now C and E. You can use the Portal or Powershell to make this change.

--- 

![alt text](image-298.png)
5 VM so 5 NIC Cards .we have public and private ip address set to them .however they needs same inbound and outbound rule so create NSG and attach to NIC and this req can be fulfilled 5 NIC hence 5 is right ans

---

![alt text](image-299.png)
- all identical security groups so you will only require 1 security group as all the settings are the same

---

Your company's Azure subscription includes Azure virtual machines (VMs) that run Windows Server 2016.
One of the VMs is backed up every day using Azure Backup Instant Restore.
When the VM becomes infected with data encrypting ransomware, you decide to recover the VM's files.
Which of the following is TRUE in this scenario?  
A. You can only recover the files to the infected VM.
B. You can recover the files to any VM within the company's subscription.
C. You can only recover the files to a new VM.
D. You will not be able to recover the files.

Correct Answer: B

Since all VMs in the subscription are running Win Server 2016, as per below statement, they can be used as target for Instant Restore.

"Backups can't be restored to a target machine that's running an earlier version of the operating system. For example, a backup taken from a Windows 7 computer can be restored on a Windows 7 (or later) computer. A backup taken from a Windows 10 computer can't be restored to a Windows 7 computer."

---

Your company's Azure subscription includes Azure virtual machines (VMs) that run Windows Server 2016.
One of the VMs is backed up every day using Azure Backup Instant Restore.
When the VM becomes infected with data encrypting ransomware, you are required to restore the VM.
Which of the following actions should you take?
A. You should restore the VM after deleting the infected VM.
B. You should restore the VM to any VM within the company's subscription.
C. You should restore the VM to a new Azure VM.
D. You should restore the VM to an on-premise Windows device.

Answer A doesn't say to restore *to* the infected VM. 
It says `"You should restore the VM *after deleting*` the infected VM"

--- 


![alt text](image-300.png)

![alt text](image-301.png)

---

![alt text](image-302.png)

---

You have an Azure Active Directory (Azure AD) tenant named contoso.com.
You have a CSV file that contains the names and email addresses of 500 external users.
You need to create a guest user account in contoso.com for each of the 500 external users.

:x: Solution: You create a PowerShell script that runs the New-AzureADUser cmdlet for each user.

:x: Solution: From Azure AD in the Azure portal, you use the Bulk create user operation.
- "Bulk Create" is for new Azure AD Users.

For Guests:
- Use "Bulk invite users" to prepare a comma-separated value (.csv) file with the user information and invitation preferences
- Upload the .csv file to Azure AD
- Verify the users were added to the directory

:o: 
Solution: You create a PowerShell script that runs the New-AzureADMSInvitation cmdlet for each external user.

---

![alt text](image-303.png)

---

![alt text](image-304.png)

![alt text](image-305.png)

---

![alt text](image-306.png)
resources created before policy creation will not inherit the policy rules. so, VNET1 will only have Department: D1 tag, VNET 2 will have Label : Value1

---

![alt text](image-307.png)

---

![alt text](image-308.png)

```
Set-AzMarketplaceTerms -Publisher <String> -Product <String> -Name <String> [-Accept] [-Terms <PSAgreementTerms>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

---

![alt text](image-309.png)

https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal

---

![alt text](image-310.png)

![alt text](image-311.png)

---

![alt text](image-312.png)

---

![alt text](image-313.png)

Correct; Answer is:
User1 can add Device2 to Group1: No (because User1 is Cloud Device Admin and cannot change the group membership for Group1)

User2 can add Device1 to Group1: Yes (because User2 is Group Owner which has the requisite authority for changing group membership. furthermore, Group1 has Assigned membership type)

User2 can add Device2 to Group2: No (because though User2 is Group Owner with requisite rights but Group2 has Dynamic Device membership type)

---

![alt text](image-314.png)

Option B is the correct answer.

**The User Access Administrator role allows users to manage user access to Azure resources, but it does not provide the ability to assign roles to other users.**

The Network Contributor role grants users the ability to manage networks, but it also does not provide the ability to assign roles to other users.

The Security Admin and Security Reader roles are not relevant to the task at hand.

Therefore, the correct option is to assign User1 the User Access Administrator role for VNet1, which will allow them to assign the Reader role to other users for that specific virtual network.

---

![alt text](image-315.png)

---

![alt text](image-316.png)
![alt text](image-317.png)

---

You have an Azure subscription that contains a virtual network named VNET1 in the East US 2 region. A network interface named VM1-NI is connected to
VNET1.
You successfully deploy the following Azure Resource Manager template.

![alt text](image-321.png)

YES
YES
NO

NIC should be in the same region with the VNet to work properly. 

As you read on the template, VM1 and VM2 are in the same region. 
Then, VM1-NI and VM2-IN could be connected to `VNET1`

---

You have an Azure subscription named Subscription1 that has a subscription ID of c276fc76-9cd4-44c9-99a7-4fd71546436e.
You need to create a custom RBAC role named CR1 that meets the following requirements:
✑ Can be assigned only to the resource groups in Subscription1
✑ Prevents the management of the access permissions for the resource groups
✑ Allows the viewing, creating, modifying, and deleting of resources within the resource groups
What should you specify in the assignable scopes and the permission elements of the definition of CR1? To answer, select the appropriate options in the answer area.
![](image-320.png)


First part should be `"/Subscription/subcription_id"` only. There is nothing called "resourceGroups" only or "resourceGroups/*" . 

You can specify either a subscription, specific resource group, management group or specific resource. 
for example it should `"/subcription/subcription_id/resourceGroups/resource_group_name"`
Check https://github.com/MicrosoftDocs/azure-docs/blob/master/articles/role-based-access-control/role-definitions.md#role-definition-structure

For second box. It is correct but missing "*". It should be "Microsoft.Authorization/*" . if you try this on az cli without "*". you will get an error

---

You have an Azure Active Directory (Azure AD) tenant.
You need to create a conditional access policy that requires all users to use multi-factor authentication when they access the Azure portal.
Which three settings should you configure? To answer, select the appropriate settings in the answer area.
NOTE: Each correct selection is worth one point.
![alt text](image-319.png)

---

Users access the resources in the subscription from either home or from customer sites. From home, users must establish a point-to-site VPN to access the Azure resources. The users on the customer sites access the Azure resources by using site-to-site VPNs.

You have a line-of-business-app named App1 that runs on several Azure virtual machine. The virtual machines run Windows Server 2016.
You need to ensure that the connections to App1 are spread across all the virtual machines.

What are two possible Azure services that you can use? Each correct answer presents a complete solution.
NOTE: Each correct selection is worth one point.
A. an internal load balancer Most Voted
B. a public load balancer
C. an Azure Content Delivery Network (CDN)
D. Traffic Manager
E. an Azure Application Gateway Most Voted

Correct Answer: A and E

A: The customer sites are connected through VPNs, so an internal load balancer is enough.

B: The customer sites are connected through VPNs, so there's no need for a public load balancer, an internal load balancer is enough.

C: A CDN does not provide load balancing for applications, so it not relevant for this situation.

D: Traffic manager is a DNS based solution to direct users' requests to the nearest (typically) instance and does not provide load balancing for this situation.

E: Azure Application Gateway is a valid option, as it provides load balancing in addition to routing and security functions

---

![alt text](image-318.png)  
- Select Users & Groups : Where you have to choose all users.  
- Select Cloud apps or actions: to specify the Azure portal  
- Grant: to grant the MFA.  

---

You have an Azure subscription linked to an Azure Active Directory tenant. The tenant includes a user account named User1.
You need to ensure that User1 can assign a policy to the tenant root management group.
What should you do?
A. Assign the Owner role for the Azure Subscription to User1, and then modify the default conditional access policies.  
B. Assign the Owner role for the Azure subscription to User1, and then instruct User1 to configure access management for Azure resources.  
**C. Assign the Global administrator role to User1, and then instruct User1 to configure access management for Azure resources.** 
D. Create a new management group and delegate User1 as the owner of the new management group.   

![alt text](image-322.png)

---

![alt text](image-323.png)

![alt text](image-324.png)

360license 不影響

---


> Only Admin3, the owner, can assign ownership.

You have an Azure Active Directory (Azure AD) tenant that contains three global administrators named Admin1, Admin2, and Admin3.
The tenant is associated to an Azure subscription. Access control for the subscription is configured as shown in the Access control exhibit. (Click the Access
Control tab.)

![alt text](image-326.png)

You sign in to the Azure portal as Admin1 and configure the tenant as shown in the Tenant exhibit. (Click the Tenant tab.)  
![alt text](image-327.png)

![alt text](image-328.png)

Correct Answer:

Azure (RBAC) and Azure AD roles are independent. 

AD roles do not grant access to resources and Azure roles do not grant access to Azure AD. 

However, a Global Administrator in AD can elevate access to all subscriptions and will be User Access Administrator in Azure root scope.

All 3 users are GA (AD) and Admin3 is owner of the subscription (RBAC).
Admin1 has elevated access, so he is also User Access Admin (RBAC).
To assign a user the owner role at the Subscription scope, you require permissions, such as User Access Admin or Owner.

Box 1: Yes
Admin1 has elevated access, so he is User Access Admin. This is valid.

Box 2: Yes
Admi3 is Owner of the Subscription. This is valid.

Box 3: No
Admin2 is just a GA in Azure AD scope. He doesn’t have permission in the Subscription.


---

![alt text](image-325.png)

---

![alt text](image-329.png)

--

![alt text](image-330.png)

1) Add a subnet to VNET1 = "User1 and User3 only"
2) Assign a user the Reader role to VNEt1 = "User1 only"

Explanation:
User1 - The Owner Role lets you manage everything, including access to resources.
User3 - The Network Contributor role lets you manage networks, including creating subnets.
User2 - The Security Admin role can view security policies, view security states, edit security policies, view alerts and recommendations, dismiss alerts and recommendations.

---

![alt text](image-331.png)
![alt text](image-332.png)

Answer is correct, both Tags and Locks are available to Subscriptions, Resource Groups, and Resources

---

![alt text](image-333.png)

---

![alt text](image-334.png)

![alt text](image-335.png)

N, N, N

## Role to enable Traffic Analytics

![alt text](image-336.png)  

---

![alt text](image-337.png)

## :o LB & User Access Administrator & VM Contributor Role

![alt text](image-338.png)
![alt text](image-339.png)


## Owner Role can assign the Reader Role to Other User

![alt text](image-340.png)

`Owner` 
- Grants full access to manage all resources, including the ability to assign roles in Azure RBAC.

`Contributor` (MANGE BUT NO GRANT FOR ASSIGNMENT)
- Grants full access to manage all resources, but does NOT allow you to assign roles in Azure RBAC. (you cannot add users or changes their rights)

`User Access Administrator` (MANGE ACCESS)
- 這個角色允許你管理使用者對 Azure 資源的存取。具體來說，你可以使用這個角色來授予或撤銷使用者對特定資源的權限。
- 例如，你可以使用這個角色來指派使用者對某個儲存帳戶或虛擬機的存取權限

`Reader`
- View all resources, but does not allow you to make any changes.

`Security Admin`
- View and update permissions for Security Center. 
- Same permissions as the Security Reader role
- Can also update the security policy and dismiss alerts and recommendations.

`Network Contributor` (MANGE NOT ACCESS)
- Lets you manage networks, but not access to them. (so you can add VNET, subnet, etc)

---

![alt text](image-341.png)

![alt text](image-342.png)

correct answer is `dataActions` and `assignableScopes`

the answer is wrong.   

you are not defining a policy but a custom role.

You need to provide either of the following in DataActions:
```bash 
Microsoft.Compute/virtualMachines/login/action
Microsoft.Compute/virtualMachines/loginAsAdmin/action
```

> https://docs.microsoft.com/en-us/azure/role-based-access-control/built-in-roles?source=recommendations#virtual-machine-administrator-login



## Enable AD DS Authentication for storage  

![alt text](image-343.png)  

## 

![alt text](image-344.png)

:x: You instruct User4 to create the user accounts.
- when you create a new tenant, the creator is the only global admin and owner, he must first give access to others to allow anything.

:x: You instruct User3 to create the user accounts.

---

You have two Azure subscriptions named Sub1 and Sub2.

An administrator creates a custom role that has an assignable scope to a resource group named RG1 in Sub1.

You need to ensure that you can apply the custom role to any resource group in Sub1 and Sub2. 

The solution must minimize administrative effort.


## Reader & Storage Data Contributor Role For Storage

![alt text](image-345.png)

## Configure App-Level Credentials For FTPS

![alt text](image-346.png)

## Bulk Insertion 

![alt text](image-347.png)

The question states 
> "You have a CSV file that contains the names and email addresses of 500 external users."

This implies that the required fields (Email and Redirection URL)are missing from the .csv file.

Here are the csv field pre-requisites that are needed for bulk upload of external users:  
https://learn.microsoft.com/en-us/azure/active-directory/external-identities/tutorial-bulk-invite#prerequisites


## Built-in AD roles can't be cloned but built-in subscription roles 

![alt text](image-348.png)

Correct Ans : 
- Role3: Role1 and built-in Azure subscription roles only
- Role4: Role2 only

> Built-in AD roles can't be cloned, but built-in subscription roles can be. 
> Custom roles of either type can be cloned.

---

Can be used as:
```json
"AssignableScopes": [
    "/subscriptions/{Sub1}",
    "/subscriptions/{Sub2}",
]
```

:a: 
The following shows what a custom role looks like as displayed using Azure PowerShell in JSON format.   

This custom role can be used for monitoring and restarting virtual machines.
```json
{
    "Name": "Virtual Machine Operator",
    "Id": "88888888-8888-8888-8888-888888888888",
    "IsCustom": true,
    "Description": "Can monitor and restart virtual machines.",
    "Actions": [
    "Microsoft.Storage/*/read",
    "Microsoft.Network/*/read",
    "Microsoft.Compute/*/read",
    "Microsoft.Compute/virtualMachines/start/action",
    "Microsoft.Compute/virtualMachines/restart/action",
    "Microsoft.Authorization/*/read",
    "Microsoft.ResourceHealth/availabilityStatuses/read",
    "Microsoft.Resources/subscriptions/resourceGroups/read",
    "Microsoft.Insights/alertRules/*",
    "Microsoft.Insights/diagnosticSettings/*",
    "Microsoft.Support/*"
],
    "NotActions": [],
    "DataActions": [],
    "NotDataActions": [],
    "AssignableScopes": [
    "/subscriptions/{subscriptionId1}",
    "/subscriptions/{subscriptionId2}",
    "/providers/Microsoft.Management/managementGroups/{groupId1}"
    ]
}
```

To ensure that you can apply the custom role to any resource group in Sub1 and Sub2 while minimizing administrative effort, you should select the custom role and add both Sub1 and Sub2 to the assignable scopes.  
```json
    "AssignableScopes": [
    "/subscriptions/{subscriptionId1}",
    "/subscriptions/{subscriptionId2}",
    "/providers/Microsoft.Management/managementGroups/{groupId1}"
    ]
```
- By adding both `Sub1` and `Sub2` to the assignable scopes of the custom role, you can ensure that the role can be applied to any resource group in both subscriptions. 

In the Azure portal, navigate to the custom role that has been created and click on it.



This minimizes administrative effort by eliminating the need to create separate custom roles for each subscription.
Option B is not recommended as it would require creating a separate custom role for each subscription, which would increase administrative effort.
Option C is not recommended as it would only allow the custom role to be applied to resource groups in Sub1 and not Sub2.
Option D is not recommended as it would require creating a separate custom role for Sub2, which would increase administrative effort.



## Reader and Data Access Role & Owner Role  

- User1 must view the data in any storage account.
- User2 must assign users the Contributor role for storage accounts  

![alt text](image-349.png)  

`Reader and Data Access` :
- Lets you `view everything` but will not let you `delete` or `create` a storage account or contained resource. 
- It will also allow `read/write access` to all data contained in a storage account via access to storage account keys.

`Owner` : 
- is needed to manage permissions, as "User Access Administrator" is not offered as an option.


## 

![alt text](image-350.png)

## :star::star: Access Package & LifeCycle Management

2-70

You have an Azure AD tenant named `contoso.com`.

You have two external partner organizations named `fabrikam.com` and `litwareinc.com`.   

`Fabrikam.com` is configured as a connected organization.  

You create an access package as shown in the Access package exhibit.  
![alt text](image-351.png)

![alt text](image-352.png)

![alt text](image-353.png)

N 
- Because not Connected

Y 
- Because when it expires it is removed from the group.
When a user's access package assignment expires, they are removed from the group or team, unless they currently have an assignment to another access package that includes 

Y 
- `365 + 30` 


> https://learn.microsoft.com/en-us/azure/active-directory/governance/entitlement-management-access-package-resources


## Private Link to ensure all the traffic from VM to storage

![alt text](image-354.png)

## :o Network Contributor & Storage Account & Contributor

You have an Azure subscription that contains a user named User1 and the resources shown in the following table.

![alt text](image-355.png)

![alt text](image-356.png)  

:a:

> NSG1 is associated to `networkinterface1`.

YES
- User1 can create a storage account in RG1, since User1 has Storage Account Contributor Role inherited from Resource Group.

NO 
- User1 can modify the DNS settings of `networkinterface1`, since it requires `Network Contributor Role` referring to the following link.  

> https://learn.microsoft.com/en-us/azure/virtual-network/virtual-network-network-interface?tabs=network-interface-portal#permissions

YES
- User1 can create an inbound security rule to filter inbound traffic to `networkinterface1`, since User1 has `Contributor` role for NSG1

## :star: MS 360 & Security Group Assignment

![alt text](image-358.png)
![alt text](image-359.png)

1. No
2. No
3. Yes

## Access Administrator Role

![alt text](image-360.png)

You need to have the Owner Role or Access Administrator role to assign roles but Access Administrator role is preferred as it is least privilege.

## User who has User Access Administrator & Reader Role

![alt text](image-361.png)

1) Reader Role provides access to view all items, except secrets

> https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles#reader

2) To Assign `OWNER` role, you need to either Owner role or User Administrator Access Role

> https://learn.microsoft.com/en-us/azure/role-based-access-control/role-assignments-portal-subscription-admin#prerequisites

3) Neither User Access Admin Role nor the Reader Role allows to create new resources.

> https://learn.microsoft.com/en-us/azure/role-based-access-control/role-assignments-steps

## Assign user SMB Share Contributor for file share (IDENTITY-BASED Data Access)

![alt text](image-362.png)

Should be A
I just created a storage account,
then created a file share,
went to IAM,
and it says : To give individual accounts access to the file share (Kerberos), enable identity-based authentication for the storage account.

## :star: Assign Premium P2 License to Security Group

![alt text](image-363.png)

![alt text](image-364.png)

1) Y
- You can assign users MS Defender for Cloud Apps on a per user basis.

2) N, 
- You cant remove the P2 license as User1 is in Group1.

1) N, 
- Nested group assignments don't work


## Users syncing from an On-Prem AD to AAD

![alt text](image-365.png)

JobTitle :   
- User1 (Member and AzureAD Source)  
- User3 (Guest and Microsoft Account) only  

Users syncing from an On Prem AD to AAD cannot have the job title altered in AAD. 
**it would need to be done in local AD** , as AAD by default synchronizes the jobTitle property. 

UsageLocation: 
- All users (User1, User2 and User3)

**UsageLocation is set only on the cloud side** for all users, and Guest users can have their job titles set as well as cloud native (AAD) users.

## Bulk User

![alt text](image-366.png)

:x: Solution: You create a PowerShell script that runs the New-MgUser cmdlet for each external user.
:o: You create a PowerShell script that runs the New-MgInvitation cmdlet for each external user.

## authenticate guest by using email & B2B collaboration  

![alt text](image-367.png)  
![alt text](image-368.png)  

 
## Storage Blob Data Contributor : Read, write, and delete Storage containers and blobs.

![alt text](image-369.png)

## :star: Condition of assigning a Premium P2 License to 360 & Security Group

![alt text](image-370.png)

Answer is B:
- The feature can only be used with security groups, and Microsoft 365 groups that have `securityEnabled=TRUE`.

## Modify the Default user role permissions settings

You have an Azure AD tenant.
- You need to modify the Default user role permissions settings for the tenant. 

The solution must meet the following requirements :
- Standard users must be prevented from creating new service principals.
- Standard users must only be able to use PowerShell or Microsoft Graph to manage their own Azure resources.

![alt text](image-373.png)

## :star: Condition for Role 

![alt text](image-371.png)  

![alt text](image-372.png)  

The conditions are difficult to read, but they mean (according to reference 1):  
- If the user performs a reading operation, then he may only read from `cont1`  
- If the user performs a writing operation, then he may only write to blobs like `*2*`  

Given that, then:
1. User 1 can read Blob2
No, because he is reading, then the condition a. applies, and he is not reading cont1
2. User 1 can read Blob3
No, because he is reading, then the condition a. applies, and he is not reading cont1
3. User 2 can read blob1
Yes, He is not writing, so the condition b. does not apply.   
He has permissions granted by the role on the scope he is reading - Storage Blob Data Owner on storage1, which contains blob1.  

## Co-administrators Role can only be assigned at the subscription scope  

![alt text](image-375.png)  
- **Co-administrators Role can only be assigned at the subscription scope.**  
You cant assign co-administrators to resource groups, management groups, or VMs.  

## You cant delete Groups having a license

![alt text](image-374.png)  

Users = User1, User2, User3, User4 
- can delete all users whether a license is assigned directly or via inheritance from a group membership

Groups = Group 2 and Group 4 
- Groups with active license assignments cannot be deleted.
You get an error

## Service Endpoint & Private Endpoint x  Microsoft backbone network.

![alt text](image-376.png)

## :star::star: ARM

![alt text](image-377.png)

Run `New-AzDeployment –Location westus –TemplateFile “deploy.json”`

![alt text](image-378.png)

1. No
Because it creates 4 Resource Groups and not 3 Resource Groups (RGS0, RGS1, RGroup4 and ResGrp8);  
1.1: The Resource Group named with "`[concat('RGS', copyIndex())]`", creates RGS0 and RGS1;  
1.2: The Resource Group named with "`[concat('ResGrp', '8')]`", creates ResGrp8;  
**1.3: The Resource Group named with "`[concat('RGroup', length(parameters('obj1')))]`", creates RGroup4 (As we can see, obj1 parameter has a length of 4 'propA', 'propB', 'propC' and 'propD');**  
2. No
because it doesn't create a resource group named `RGroup5`;
1. Yes
because all resource groups were created in the East US Azure Region.


## :star: Account Kind & Storage Type can apply for File Export/Import

![alt text](image-379.png)

Correct Answer: D

Azure Import/Export service supports the following of storage accounts:
- Standard General Purpose v2 
recommended for most scenarios
- Blob Storage
- General Purpose v1 
both Classic or Azure Resource Manager deployments

Azure Import/Export service supports the following storage types:
- Import supports **Azure Blob storage and Azure File storage**
- Export supports **Azure Blob storage** only.

Only storage4 can be exported.

## App uses Managed Identity to access storage 

![alt text](image-380.png)  

Box 1: Access Control (IAM)  
- Since the App1 **uses Managed Identity, App1 can access the Storage Account via IAM**.  
- As per requirement, we need to minimize the number of secrets used, so Access keys is not ideal.  

Box 2: Shared access signatures (SAS)  
- We need temp access for App2, so we need to use SAS.  

## SKU & kind for az storage create

![alt text](image-381.png)    
Box 1: StorageV2   
Box 2: Standard_GRS  

## :star::star:  Policy will identify the VM as not compliant but will not put VM in deallocate   

![alt text](image-382.png)  

The status of VM1 is Running.   

You assign an Azure policy  
![alt text](image-383.png)  

Parameters 
```bash 
Microsoft.ClassicNetwork/virtualNetworks
Microsoft.Network/virtualNetworks
Microsoft.Compute/virtualMachines
```
  
![alt text](image-384.png) 
N-N-N  
Policy will identify the VM as not compliant but will not put VM in deallocate   

## Actions of File export/import

Step 1: Prepare the drives (Attach an external disk to Server1 and then run waimportexport.exe)

Step 2: Create an IMPORT JOB (From the Azure portal, create an import job)

Step 3: SHIP the drives to the Azure datacenter (Detach the external disks from Server1 and ship the disks to an Azure data center)

Step 4: UPDATE the job with tracking information (From the Azure portal, update the import job)  


## :star: File added to Cloud or Server Endpoint to Sync

![alt text](image-385.png)

File1: 
- Endpoint1 only  
It is a cloud endpoint, and it is scanned by the detection job every 24 hours.  

File2: 
- Endpoint1, Endpoint2 and Endpoint3
- **With the on-premises servers the file is scanned and synced automatically after it's being added**.

Note: They changed the question in Exam from "within 24 hours" to "after 24 hours".
So, the answer is:
File1: Endpoint1, Endpoint2 and Endpoint3
File2: Endpoint1, Endpoint2 and Endpoint3


## Import Job DataSet and driveSet CSV

![alt text](image-386.png)

## Enable RSV backup Service & VM to access Storage Account

![alt text](image-387.png)

![alt text](image-388.png)

1. The 10.2.9.0/24 subnet is not whitelisted.  
2. Must enable `Allow trusted Microsoft services` to access this storage account   
![alt text](image-389.png)

## Actions File Share Sync 

- Create a Storage Sync Service
The deployment of Azure File Sync starts with placing a Storage Sync Service resource into a resource group of your selected subscription.

- Install the Azure File Sync AGENT on Server1
The Azure File Sync agent is a downloadable package that enables Windows Server to be synced with an Azure file share

- Register Server1.
Register Windows Server with Storage Sync Service
Registering your Windows Server with a Storage Sync Service establishes a trust relationship between your server (or cluster) and the Storage Sync Service.

- Add a server endpoint 
:warning: wCreate a sync group and a cloud endpoint.
A sync group defines the sync topology for a set of files. Endpoints within a sync group are kept in sync with each other. A sync group must contain one cloud endpoint, which represents an Azure file share and one or more server endpoints. A server endpoint represents a path on registered server.

---

1. Prepare Windows Server to use with Azure File Sync
2. Deploy the Storage Sync Service
3. Install the Azure File Sync agent
4. Register Windows Server with Storage Sync Service
5. Create a sync group and a cloud endpoint
6. Create a server endpoint
7. Configure firewall and virtual network settings

![alt text](image-395.png)

## How File Sync works

![alt text](image-390.png)

## Stop backup items (File Share, SQL and VM) before Deleting RSV

![alt text](image-391.png)

## Only VM and File Share is allowed to Backup

![alt text](image-392.png)

Note: To create a Vault to protect VMs, the Vault must be in the same Region as the VMs.

Box 1: VM1 only
VM1 is in the same region as Vault1. 
File1 is not in the same region as Vautl1.   
SQL is not in the same region as Vault1.   
**Blobs cannot be backup up to service vaults.**

Box 2: Share1 only
Storage1 is in the same region as Vault2. 
Share1 is in Storage1.

## Dest of AZ import/export job is File Share

![alt text](image-393.png)

Azure Import/Export service is used to securely import large amounts of data to Azure Blob storage and Azure Files by shipping disk drives to an Azure datacenter. 

This service can also be used to transfer data from Azure Blob storage to disk drives and ship to your on-premises sites. 

**Data from one or more disk drives can be imported either to Azure Blob storage or Azure Files.**   
- The maximum size of an Azure Files Resource of a file share is 5 TB.

Note: There are several versions of this question in the exam. 

The question has two correct answers:
1. Azure File Storage
2. Azure Blob Storage

The question can have other incorrect answer options, including the following:
- Azure Data Lake Store
- Azure SQL Database
- Azure Data Factory

## AzCopy Command is for blob and file only

![alt text](image-394.png)

## Authentication with Blob & File via AzCopy

You need to use AzCopy to copy data to the blob storage and file storage in storage1.

Which authentication method should you use for each type of storage?

You can provide authorization credentials by using Azure Active Directory (AD), or by using a Shared Access Signature (SAS) token.

Blob Storage : 
- Both Azure Active Directory (AD) and Shared Access Signature (SAS) token are supported for Blob storage.

File Storage : 
- Only Shared Access Signature (SAS) token is supported for File storage.

## Update Domain for Planned Maintenance

You have an app named App1 that runs on two Azure virtual machines named VM1 and VM2.
You plan to implement an Azure Availability Set for App1. The solution must ensure that App1 is available during planned maintenance of the hardware hosting
VM1 and VM2.

:a: 
When you create an Availability Set, the hardware in a location is divided into multiple update domains and fault domains.

An update domain is a group of VMs and underlying physical hardware that can be rebooted at the same time.

VMs in the same fault domain share common storage as well as a common power source and network switch.

- During scheduled maintenance, only one update domain is updated at any given time. 
- Update domains aren't necessarily updated sequentially. So, we need two update domains.

## 

![alt text](image-396.png)

- NO
Only one cloud endpoint can be added to sync1
- YES
Server2 has been registered to Sync1 but data2 is not added to server endpoint.   
So we can add data2 as additional server endpoint for Sync1
- NO 
We have to register Server3 first  

## Add Storage Account and Log Analytics workspace to RSV

![alt text](image-397.png)

You plan to configure Azure Backup reports for Vault1.
You are configuring the Diagnostics settings for the AzureBackupReports log.

Which storage accounts and which Log Analytics workspaces can you use for the Azure Backup reports of Vault1?

:a: : 

> analytics are independent of locations

1. `storage3`
2. `analytics 1,2 & 3`

## :star::star: Storage Account type & Access Tier

![alt text](image-398.png)

![alt text](image-399.png)

Box 1: `contoso104 only`
- Premium file shares are hosted in a special purpose storage account kind, called a `FileStorage` account.

Box 2: `contoso101 and contos103 only`
- Object storage data tiering between hot, cool, and archive is supported in `Blob Storage and General Purpose v2 (GPv2) `accounts. 

General Purpose v1 (GPv1) accounts don't support tiering.   
The archive tier supports only LRS, GRS, and RA-GRS.  

## SAS configuration

![alt text](image-400.png)  
![alt text](image-401.png)  

It should be no access for both cases.
- for first case, cause the IP is not matching the SAS requirements
- for second case, since it is using "net use" where it uses SMB. 
**The SMB (Server Message Broker) protocol does not support SAS. it still asks for username/password**.     
Accordingly, it will give error wrong username/pass and will not provide access.  

## Switch to OTher RSV

You have two Azure virtual machines named VM1 and VM2. You have two Recovery Services vaults named RSV1 and RSV2.
VM2 is backed up to RSV1.
You need to back up VM2 to RSV2.

A. From the RSV1 blade, click Backup items and stop the VM2 backup Most Voted  
B. From the RSV2 blade, click Backup. From the Backup blade, select the backup for the virtual machine, and then click Backup  
C. From the VM2 blade, click Disaster recovery, click Replication settings, and then select RSV2 as the Recovery Services vault  
D. From the RSV1 blade, click Backup Jobs and export the VM2 job  

If you want to change the recovery service vault you need to disassociate the previous RSV and delete the backup data. To delete backup data, you need to stop the backup first.
So:
1. Stop the backup in RSV1
2. Remove the backup data.
3. Disassociate the VM in RSV1.
4. Associate the VM in RSV2.

## Lifecycle for which storage

Lifecycle management policies are supported for block blobs and append blobs in   
- general-purpose v2, 
- premium block blob, 
- and Blob Storage accounts. 

Lifecycle management doesn't affect system containers such as the $logs or $web containers

Storage account types offered now without switching to legacy are simply standard (gpv2) and premium. 

Even in legacy, there isn't any such storage account type as "`filestorage`", so storage4 as listed is not valid, period.


## :star: 

![alt text](image-402.png)

![alt text](image-403.png)  

Box 1- Yes. VirtualNetworkRules & IpRules are blank, with the default action Allow.
Box 2- Yes. Individual blobs can be set to the archive tier - ref.https://docs.microsoft.com/en-us/azure/storage/blobs/access-tiers-overview
Bob 3. No. To access blob data in the Azure portal with Azure AD credentials, a user must have the following role assignments:
- A data access role, such as Storage Blob Data Contributor The Azure Resource Manager Reader role

## Platform can use azCopy

![alt text](image-404.png)

## Access Policy to prevent content changing



## lifecycle management rules 

![alt text](image-405.png)

![alt text](image-406.png)

1. No.
You can not read Dept1File.docx , YOu can not read file in archive tier
2. Yes.
Because file is modified on 5 Oct, after 2 days it moved to cool storage and on 10th oct its still in cool storage. You can read file in cool storage.
3. Yes.
Same as File 2 its still in cool storage, because its modified on 2nd oct it still has one day to move to archive tier.


## :warning: Storage Blob Data Contributor & Reader 

![alt text](image-407.png)

ANSWER: BC

Assigning the Storage Account Contributor and Storage Blob Data Reader rolls to the group and having **the user (which is a part of that group)** sign in to the portal, the storage account isn't even listed under storage accounts.  

Remove the Storage Blob Data Reader and assigning the Reader roll to the group, **the storage account is listed and the users of the group can create blobs/file-shares etc.**

:memo: Reader Role  
The Reader role is an Azure Resource Manager role that permits users to view storage account resources, but not modify them.
- **It does not provide read permissions to data in Azure Storage, but only to account management resources.**  
So The Reader role is necessary so that users can navigate to blob containers in the Azure portal.   

:question: Why you need Reader instead of Storage Blob Data Reader ?
For example, if you assign the Storage Blob Data Contributor role to user Mary at the level of a container named sample-container, then Mary is granted read, write, and delete access to all of the blobs in that container.  

However, if Mary wants to view a blob in the Azure portal, then the Storage Blob Data Contributor role by itself will not provide sufficient permissions to navigate through the portal to the blob in order to view it. 

> The additional permissions are required to navigate through the portal and view the other resources that are visible there." - https://docs.microsoft.com/en-us/azure/storage/blobs/assign-azure-role-data-access?tabs=portal


## azcopy copy src dest --parameter

![alt text](image-408.png)

Correct Answer: C
- A: URL of the Storage Account.
- B: The azcopy sync command replicates the source location to the destination location. 
However, the file is skipped if the last modified time in the destination is more recent.
- C: The azcopy copy command copies a directory (and all the files in that directory) to a blob container. 
The result is a directory in the container by the same name.
- D: The az storage blob copy start-batch command copies multiple blobs to a blob container.

## Change the Account type via option `performance`

![alt text](image-409.png)

Select Standard performance for GPv2 storage accounts (default). 
- This type of account is recommended by Microsoft for most scenarios.   

Select Premium for scenarios requiring low latency. 

After selecting Premium, select the type of premium storage account to create. 

The following types of premium storage accounts are available:  
```
Block blobs
File shares
Page blobs
```

## :warning: Blob Container authentication method with Access Key, AAD and SAS to file-share via AZ   

You plan to use `AzCopy` to copy a blob from `container1` directly to `share1`.  

You need to identify which authentication method to use when you use AzCopy.
What should you identify for each account? 

![alt text](image-410.png)

- Each method may be used once, more than once, or not at all. You may need to drag the split bar between panes or scroll to view content.

:a: SAS

To `storage1`, you could authenticate with **Access Key**, **SAS** and **AAD**, but Storage1 has disabled public access, so you can't access it with **AzCopy** even authenticated. 

However in SAS token you can specify authorized IP range from which you can use your access.   
Access Key and AAD do not have that option, hence the only possible authorization method for `storage1` is SAS.  

## Blob Container with encrypted Scope

![alt text](image-411.png)

D) Create an encryption scope

In Azure Storage, encryption of data at rest is done using Azure Storage Service Encryption (SSE). 

Azure Storage SSE uses Microsoft-managed encryption keys to encrypt the data in the storage account.

In the scenario described, you need to use a different key to encrypt data at rest for one of the containers. To do this, you need to create an encryption scope, which is a named configuration that defines the default encryption settings for a container. By creating an encryption scope, you can use a customer-managed key, stored in Azure Key Vault, to encrypt the data in that specific container.

Therefore, option D (Create an encryption scope) is the correct answer as **it allows you to use a different key for data encryption for the specific container.**

## Blobs Rule policy 

![alt text](image-412.png)

N-N-N

- On June 6, File1 will be in archive because File1 is in container 1, and rule 1 applies 3 days after june 1.

- On June 1, File2 will still be in Hot tier because File2 is in container2, Rule3 and Rule4 haven't hit yet.

- On June 16, File2 will be deleted because Rule3 applies 10 days after June 1.

## :star: Storage ARM for allowBlobPublicAccess & SKU & DeleteRetentionPolicy

You plan to deploy a storage account named storage1 by using the following Azure Resource Manager (ARM) template.

![alt text](image-422.png)

![alt text](image-421.png)

N-N-Y

- `deleteRetentionPolicy` is 7 days, so can not be restored after 7 days. Means, backup is deleted after 7 days.
- `allowBlobPublicAccess` is `true`, so anyone can access the blob, not just on Azure.
- `kind` is `Standard_LRS` and `location` is `East US`, so 3 local copies are stored.

## AZ Explorer

![alt text](image-417.png)  

**Azure Storage Explorer does not have the ability to create a new storage account directly.**  
- Instead, you can use Azure Storage Explorer to connect to and manage existing storage accounts in Azure.

## RSV for ZRS 

![alt text](image-416.png)

1. Create RSV 
2. Set Replication ZRS
3. Backup Policy Creation &Configuration

## ARM lifecycle management

`tierToArchive` and `prefixMatch`

- `tierToArchive` because it's the lowest cost tier, and does not say anything about needing to read data after 90 days.   
However, rehydration costs will occur if they did need to read it.  
- `prefixMatch` because we only want the blob in the container1.  

## Storage Account Blades Configuration

![alt text](image-418.png)

![alt text](image-419.png)

IT'S NOW `IAM` AND `REDUDANCY` 
(`REPLICATION` CHANGED TO THIS NAME)

## RSA Customer-managed key encryption for storage container

![alt text](image-420.png)

## 2 blob storage policies & 5 access policies 

![alt text](image-413.png)  

![alt text](image-414.png)  

Max stored access policies: `3`  
- because max total of stored access policy is `5` and we already have `2`, so additional 3 available.  

Max immutable blob storage: `1`  
- because max total of immutable blob storage policy is 2
- one Legal hold policy and one Time-based retention policy.    
 
We already have one, so additional 1 available.

## :star: Connection String key and SAS Access

![alt text](image-423.png)

For storage1, you create a shared access signature (SAS) named SAS1 that has the settings shown in the following exhibit  
![alt text](image-424.png)

To which resources can User1 write by using SAS1 and key1?

![alt text](image-425.png)

:a: 

`key1`: folder1, container1, table1    
`SAS1`: table1   

I think that `key1` is the key of storage account which is created when creating storage account.  
Thus, **it should be able to access all in storage account**.  

SAS1 allows table only which is shown in the exhibit.  

## :star: Lifecycle Management Policies Actions Order

![alt text](image-426.png)

If you define more than one action on the same blob
- **lifecycle management applies the least expensive action to the blob**. 

For example, action `delete` is cheaper than action `tierToArchive`.
Action `tierToArchive` is cheaper than action `tierToCool`.
- `delete -> tierToArchive -> tierToCool`

## :star: Lifecycle management with account kind & redundancy

![alt text](image-427.png)
- You need to identify which storage accounts support lifecycle management, and which storage accounts support moving data to the Archive access tier.

Which storage accounts should you use? 

:a: 

1. storage1, storage2, storage3 (SEE Kind)
Lifecycle management policies are supported for block blobs and append blobs **in general-purpose v2, premium block blob, and Blob Storage accounts.**

2.  storage2 (SEE Redundancy)
Only storage accounts that are configured for `LRS`, `GRS`, or `RA-GRS` support moving blobs to the archive tier.  
    - The archive tier isn't supported for ZRS, GZRS, or RA-GZRS accounts.  

> https://learn.microsoft.com/en-us/azure/storage/blobs/lifecycle-management-overview  
> https://learn.microsoft.com/en-us/azure/storage/blobs/access-tiers-overview  

## ARM for Storage `tierToCool` and `blobTypes`

You create a blob lifecycle rule named rule1.  

You need to configure rule1 to automatically move blobs that were NOT updated for 45 days from contained to the Cool access tier.

![alt text](image-428.png)  

Tiering is not yet supported in a premium block blob storage account. 

**For all other accounts, tiering is allowed only on block blobs and not for append and page blobs.**

## SMB Multichannel (File Share, LRS/ZRS)

You need to ensure that share1 can support SMB Multichannel. 

The solution must minimize costs.

:a: 

According to documentation only Premium file shares (FileStorage), **LRS/ZRS are supported for SMB**.

## use conditions while assigning RBAC to containers and queues

![alt text](image-429.png)  

## :star: K8s & CNI -> VNet

![alt text](image-430.png)  
![alt text](image-431.png)  
Agree with the answer NYY.

1. subnet is not in the same location as cluster 
**If you want to select an existing virtual network, make sure it's in the same location and Azure subscription as your Kubernetes cluster.**

> https://learn.microsoft.com/en-us/azure/aks/configure-azure-cni

2. azure CNI network configuration in same location as cluster and within the total pod no. limit

3. Bring your own subnet and route table with k8s. 
With k8s network configuration, a route table must exist on your cluster subnet(s). 
AKS supports bringing your own existing subnet and route table.

> https://learn.microsoft.com/en-us/azure/aks/configure-kubenet#prerequisites

## Azure Custom Script Extension PostDeployment  

![alt text](image-432.png)  

## default routing tier minimizes storage network cost & managed key can be modified after creating

![alt text](image-433.png)

![alt text](image-434.png)

**to minimize network cost** default routing tier

> https://learn.microsoft.com/en-us/azure/storage/common/network-routing-preference

**what can be changed after creation** customer-managed key
- You can switch between customer-managed keys and Microsoft-managed keys at any time

> https://learn.microsoft.com/en-us/azure/storage/common/customer-managed-keys-overview

## RSA customer-managed key 4096

You need to configure encryption for the account. The solution must meet the following requirements:

• Use a customer-managed key stored in a key vault.
• Use the maximum supported bit length.

![alt text](image-435.png)

## SAS or Role Assignment Condition

![alt text](image-436.png)  

:a: : 

An Azure role assignment condition is an optional check that you can add to your role assignment to provide more fine-grained access control.  

For example, you can add a condition that requires an object to have a specific tag to read the object.  

https://learn.microsoft.com/en-us/azure/role-based-access-control/conditions-role-assignments-portal  

## ARM for Network and Storage Account

You plan to create a role definition to meet the following requirements :  
- Users must be able to view the configuration data of a storage account.  
- Users must be able to perform all actions on a virtual network.  

The solution must use the principle of least privilege.  

![alt text](image-437.png)

## :star: Host Caching & Premium SSD

To VM1, you plan to add a 1-TB data disk that meets the following requirements:  
- Provides data resiliency in the event of a datacenter outage.
- Provides the lowest latency and the highest performance.
- Ensures that no data loss occurs if a host fails.

:a: 

1. **Provides data resiliency in the event of a datacenter outage.**
- Zone-redundant storage (ZRS) provides this capability by replicating data across multiple availability zones, ensuring that if one datacenter fails, the data is still available in other zones.

2. **Provides the lowest latency and the highest performance.**
- Premium SSDs offer better performance and lower latency compared to Standard SSDs.

3. **Ensures that no data loss occurs if a host fails.**
- Write caching can pose a risk of data loss in the event of a host failure. Thus, we need to be careful when enabling write caching.

Given the options:

Storage:
- Premium SSD that uses zone-redundant storage (ZRS) is the right choice as it provides high performance and ensures data resiliency across datacenter outages.

Host caching:
To avoid data loss during a host failure, we should avoid using write caching.
- Read-Only would be the appropriate choice to enhance performance without risking data loss due to host failure.

## VM KEK & Disk Encryption for RSV

![alt text](image-438.png)  

To prepare Vault1 for Azure Disk Encryption with a key encryption key (KEK):

1. `Create a new key`   
**You need to have a key in the Key Vault.** 
This will be the KEK.    
Azure Disk Encryption uses `BitLocker` for Windows VMs, which requires a key for encrypting the data disk.   
**If you're using a KEK, the BEK (BitLocker Encryption Key) will be wrapped by this KEK.** 

2. `Select Azure Disk Encryption for volume encryption.`
**The key vault itself should be configured for Azure Disk Encryption.**   
This ensures the vault is set up to work with Azure VMs and their disks.

So, the correct actions are B and E.

## Usage of Azure Disk Encryption

![alt text](image-439.png)

You can protect your managed disks by using Azure Disk Encryption for Linux VMs, which uses DM-Crypt, or Azure Disk Encryption for Windows VMs, which uses Windows BitLocker, to protect both operating system disks and data disks with full volume encryption.

Encryption keys and secrets are safeguarded in your Azure Key Vault subscription. By using the Azure Backup service, you can back up and restore encrypted virtual machines (VMs) that use Key Encryption Key (KEK) configuration."

> https://learn.microsoft.com/en-us/azure/security/fundamentals/encryption-overview


## :star: SAS configuration

You need to configure a shared access signature (SAS) to ensure that users can only **download blobs securely by name**.

:a:   

![alt text](image-440.png)

Allowed resource types:
- Blob (since you want to access blobs).  
- Service (if you want users to access all blobs within a container)
- **Object (if you want users to access a specific blob by name)**

Allowed permissions: 
- Set to `Read` to allow downloading.

Specify the start and expiry date for the token.
- If you're using a shared access policy, you can select it here. Otherwise, configure the SAS token directly.

## SAS Accessing

![alt text](image-441.png)

## :star: Hierarchical namespace for Azure Data Lake Storage

You need to create an Azure Storage account named storage1

It requires
- Support `Azure Data Lake Storage`.
- Minimize costs for infrequently accessed data.
- Automatically replicate data to a secondary Azure region.

Which three options should you configure for `storage1`

B. The Cool access tier: 
- The Cool access tier is suitable for infrequently accessed data and offers lower storage costs compared to the Hot access tier.

C. Geo-redundant storage (GRS): 
- Geo-redundant storage replicates data to a secondary Azure region, providing data redundancy and disaster recovery capabilities.

E. Hierarchical namespace: 
- T**he hierarchical namespace is required for Azure Data Lake Storage,** as it enables the storage account to support the data lake's file system structure.

## :star: ARM Lifecycle Management Policy

You have an Azure Storage account named storage1 that contains two containers named container1 and container2

You periodically take blob snapshots of critical blobs.

![alt text](image-442.png)
![alt text](image-443.png)

Y 
- See section tierToCool

N 
- `rule1` only applies to `container1`, not `container2`, see section prefixMatch

N 
- This one is a bit complicated.   
Rehydrated files (that were in the archive tier first and then returned to hot or cool) wouldn't necessarily be archived after 30 days    
as there's a condition that the last tier change must be at least 7 days ago.     
(I'll leave it open how these files became archived in the first place, before 30 days after creation...)   


## ARM blockbob for blobs whose prefixMatch is `finance` 

You have an Azure Storage account named `storage1` that contains a container named `container1`. 

The `container1` container stores thousands of image files.

You plan to use an Azure Resource Manager (ARM) template to create a blob inventory rule named `rule1`.  

**You need to ensure that only blobs whose names start with the word `finance` are stored daily as a CSV file in `container1`.**

How should you complete `rule1`?

:a: 

![alt text](image-444.png)  

## 

• Ensure that the SAS can only be used to enumerate and download blobs stored in container1.
• Use the principle of least privilege.

## :star: Roles and Storage Account Permission

![alt text](image-447.png)
![alt text](image-446.png)
![alt text](image-445.png)

1. Yes: Public Access is enabled for blob
2. No: Azure Storage Account Contributor role can't access the file share
3. No: Access Key is disabled on the storage account

ANSWERS = N-N-N

- Storage Account Contributor: DataActions => none
- Reader: DataActions => none
- Storage account access keys: disabled

"These keys can be used to authorize access to data in your storage account via Shared Key authorization, or via SAS tokens that are signed with the shared key."

You can use the access key to authorize requests to Azure Storage using Shared Key authorization or SAS tokens

## AKS deployment

You deploy an Azure Kubernetes Service (AKS) cluster named AKS1. 

:x: Solution: From Azure CLI, you run az aks.
:o: Solution: From Azure CLI, you run the kubectl client.
:x: From Azure CLI, you run `azcopy`.

## create an Alert via Azure Log Analytic & AZ Monitor 

You have an Azure virtual machine named VM1 that runs Windows Server 2016.

You need to create an alert in Azure when more than two error events are logged to the System event log on VM1 within an hour.

:x: **You create an Azure storage account and configure shared access signatures (SASs)**.   
You install the Microsoft Monitoring Agent on VM1. You create an alert in Azure Monitor and **specify the storage account as the source**.  

:x: You create an Azure Log Analytics workspace and configure the data settings. 
**You add the Microsoft Monitoring Agent VM extension to VM1.** 
You create an alert in Azure Monitor and specify the Log Analytics workspace as the source.


> You want to create an Alert which means you need Log analytics and Azure monitor.

```
You add the Microsoft Monitoring Agent VM extension to VM1 > This is WRONG

You Install the Microsoft Monitoring Agent VM agent to VM1 > This is Correct
```

1. Log analytics agent
Install in VM.
1. Log analytics workspace 
Collect the log files from Log Analytics Agent.
1. Azure Monitor
Create alert based on logs read from Log Analytics Workspace.

## Move APP from VNET to another

![alt text](image-451.png)
![alt text](image-452.png)

:a: 

We cannot just move a virtual machine between networks.   

What we need to do is identify the disk used by the VM, delete the VM itself while retaining the disk, and recreate the VM in the target virtual network and then attach the original disk to it.

## Scale in/out

![alt text](image-453.png)
![alt text](image-454.png)

## create how many web app plan

![alt text](image-450.png)

Box 1: ASP1 and ASP3 only
`ASP.NET Core` apps can be hosted both on Windows or Linux.  

The region in which your app runs is the region of the App Service Plan is in.  

ASP2 is in Central US, not the same as WebApp1. 

Different locations.

Box 2: ASP1 only
ASP.NET apps can be hosted on Windows only. Only ASP1 is in the same Location as the WebApp2 (West US).

## post deployment


![alt text](image-448.png)

Correct Answer: A and D

The Custom Script Extension downloads and executes scripts on Azure VMs. 

This extension is useful for post deployment configuration, software installation, or any other configuration / management task. 

Scripts can be downloaded from Azure storage or GitHub, or provided to the Azure portal at extension run-time.

The Custom Script extension integrates with Azure Resource Manager templates, and can also be used with the Azure CLI, Azure PowerShell, Azure portal, or the REST API
The following Custom Script Extension definition downloads a sample script from GitHub, installs the required packages, then writes the VM instance hostname to a basic HTML page.

> https://docs.microsoft.com/en-us/azure/virtual-machine-scale-sets/tutorial-install-apps-template


## Scale up/out web service plan

![alt text](image-455.png)

Correct Answer: A

The app must be running in the Standard, Premium, or Isolated tier in order for you to enable multiple deployment slots. 

If the app isn't already in the Standard, Premium, or Isolated tier, you receive a message that indicates the supported tiers for enabling staged publishing. 
At this point, you have the option to select `Upgrade` and go to the Scale tab of your app before continuing.

- Scale up: Get more CPU, memory, disk space, and extra features like dedicated virtual machines (VMs), custom domains and certificates, staging slots, autoscaling, and more.
- Scale out: Increase the number of VM instances that run your app. 
you can scale out to as many as 30 instances

## Modify variable in resources section

![alt text](image-456.png)

## Scale Set or Update Domain

![alt text](image-457.png)

Correct Answer: A

VM Scale Set consists of a set of identically configured VMs.

Availability Set consists of a set of discrete VMs.

No more than 20% of the Scale Set upgrading at any time, then 2 machines out of 10 will have maintenance, the 8 remaining VMs will be up.

**Virtual machine scale sets are created with five fault domains by default in Azure regions with no zones.**   

For the regions that support zonal deployment of virtual machine scale sets and this option is selected, the default value of the fault domain count is `1` for each of the zones.   
- `FD=1` in this case implies that the VM instances belonging to the scale set will be spread across many racks on a best effort basis.  

Reference:  
- https://docs.microsoft.com/en-us/azure/virtual-machines/manage-availability
- https://docs.microsoft.com/en-us/learn/modules/build-app-with-scale-sets/2-features-benefits-virtual-machine-scale-sets
- https://docs.microsoft.com/en-us/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-automatic-upgrade

## Error Event : Log Analytics & Agent & Monitor

You have an Azure virtual machine named VM1 that runs Windows Server 2016.

You need to create an alert in Azure when more than two error events are logged to the System event log on VM1 within an hour.

:x: You create an event subscription on VM1. You create an alert in Azure Monitor and specify VM1 as the source

:o: You need to specify Log Analytics as the source for this alert, and not the VM as source for the alert.

1. You create an Azure Log Analytics workspace and configure the data settings.
2. You install the Microsoft Monitoring Agent on VM1.
3. You create an alert in Azure Monitor and specify the Log Analytics workspace as the source.

## Redeployment (MOVE VM to Different Host)

You have an Azure virtual machine named VM1.  

VM1 was deployed by using a custom Azure Resource Manager template named `ARM1.json`.    

You receive a notification that VM1 will be affected by maintenance.  

You need to move VM1 to a different host immediately.

:o: From the Redeploy blade, you click Redeploy.
:x: From the Overview blade, you move the virtual machine to a different subscription.
:x: From the Update management blade, you click Enable.

## Custom DNS record for Custom Domain

![alt text](image-458.png)

## :star::star: delete VM when change it to different RG and connects a VM

![alt text](image-459.png)

:o: You delete VM1. You recreate VM1, and then you create a new network interface for VM1 and connect it to VNET2

Instead, you should delete `VM1`. Then recreate VM1 and add the network interface for VM1.

> To migrate a VM from a VNET to another VNET.   
> **The only option is to delete the VM and redeploy it using a new NIC and NIC connected to VNET2.**  

- When you create an Azure Virtual Machine (VM), you must create a Virtual Network (VNet) or use an existing VNet. 
- You can change the subnet a VM is connected to after it's created, but you cannot change the VNet. 
You can also change the size of a VM.
- Changing VNET is not an easy task once VM is deployed and running.  

## VCpu

![alt text](image-462.png)  

![alt text](image-463.png)  

`Total regional vCPUs = 20`

`2 vCPUs (VM1) + 16 vCPUs (VM20) = 18` 
vCPUs, which means that only 2 vCPUs left to exceed usage limit.

Box 1: Yes
We can add 1 vCPU. 2 vCPUs (VM1) + 16 vCPUs (VM20) + 1 vCPU (VM3) = 19 vCPUs

Box 2: No
We cannot add 4 vCPUs. 2 vCPUs (VM1) + 16 vCPUs (VM20) + 4 vCPU (VM4) = 22 vCPUs

Box 3: No
We cannot add 16 vCPU. 2 vCPUs (VM1) + 16 vCPUs (VM20) + 16 vCPU (VM5) = 34 vCPUs

## Load Balancer & K8s Cluster 

![alt text](image-466.png)  

## Update Domain & Fail Domain 計算方式 :star::star:
![alt text](image-464.png)  

You add 14 virtual machines to WEBPROD-AS-USE2.
![alt text](image-465.png)

Correct Answer:

Box 1: 2
There are 10 update domains. 

The 14 VMs are shared across the 10 update domains, so 4 update domains will have 2 VMs and 6 update domains will have 1 VM. 

Only one update domain is rebooted at a time.

D1 D2 D3 D4 D5 D6 D7 D8 D9 D10
vm1 vm2 vm3 vm4 vm5 vm6 vm7 vm8 vm9 vm10
vm11 vm12 vm13 vm14

Maximum Down = 2
Minimum Down = 1
Box 2: 7
There are 2 fault domains. The 14 VMs are shared across the 2 fault domains, so 7 VMs in each fault domain. A rack failure will affect one fault domain so 7 VMs will be offline.
14 VM in 2 Fault Domain

```bash 
Rack 1 Rack 2
vm1    vm8
vm2    vm9
vm3    vm10
vm4    vm11
vm5    vm12
vm6    vm13
vm7    vm14
```

Maximum Down = 7
Minimum Down = 7

## ARM storage Configuration

You plan to deploy an Azure container instance by using the following Azure Resource Manager template.
![alt text](image-467.png)
![alt text](image-468.png)

1) Internet users "can connect to the container from any device"
2) If Internet Information Services (IIS) in the container fails, "the container will restart automatically".

Explanation:
No Access restrictions are specified.
The "restartPolicy" is set as "OnFailure".

## Downtime for VM1 while resizing

![alt text](image-461.png)
While resizing, the VM must be in a stopped state, therefore there will be a downtime.

## test staging and swap it with production

![alt text](image-460.png)  
1. Deploy the App to `webapp1-test` which is staging environment and test it there.
2. Once the test is success swap the slots, so the new changes will be available under production.  

## Using Network Watcher x AZ storage account x Microsoft.Insights  

You have an Azure subscription named `Subscription1` that has the following providers registered :
```
Authorization
Automation
Resources
Compute
KeyVault
Network
Storage
Billing
Web
```

Subscription1 contains an Azure virtual machine named VM1 that has the following configurations:

```
Private IP address: 10.0.0.4 (dynamic)
Network security group (NSG): NSG1
Public IP address: None
Availability set: AVSet
Subnet: 10.0.0.0/24
Managed disks: No
Location: East US
```

You need to record all the successful and failed connection attempts to VM1. 

Which three actions should you perform? Each correct answer presents part of the solution.  

A. Enable Azure Network Watcher in the East US Azure region.  
B. Add an Azure Network Watcher connection monitor.  
C. Register the MicrosoftLogAnalytics provider.  
D. :o: `Create an Azure Storage account. ` 
E. :o: `Register the Microsoft.Insights resource provider. ` 
F. :o: `Enable Azure Network Watcher flow logs.`  


> https://docs.microsoft.com/en-us/azure/network-watcher/network-watcher-monitoring-overview  

> https://docs.microsoft.com/en-us/azure/network-watcher/network-watcher-nsg-flow-logging-portal  


:a: 

**When you create or update a virtual network in your subscription, Network Watcher will be enabled automatically in your Virtual Network's region.** 
- There is no impact to your resources or associated charge for automatically enabling Network Watcher. 


1. Create a VM with a NSG
2. Enable Network Watcher (done by default with the vnet/subnet creation)
3. register the Microsoft.Insights provider 
4. Enable a traffic flow log for an NSG, using Network Watcher's NSG flow log capability

> NSG flow log data is written to an Azure Storage account.
> Complete the following steps to create a storage account for the log data.

5. you need to create a storage account before enable the NSG flow
6. Download logged data
7. View logged data

## Fast Way to Deploy VM Scale Set by ScaleSetVM orchestration mode

![alt text](image-469.png)  

the main idea is to create 5 VMs ASAP. 
- To do this you should let Azure do it for you with the least steps.   
- either by using ARM template which is not mentioned here or VM scale set. 

That leaves us with 2 options C or D. 
- C : `VM (virtual machines) orchestration mode` is like `unmanaged Scale set` where you add the VMs manually to the scale set as a unmanaged group. 

- D : `ScaleSetVM orchestration mode` is managed scale set by Azure where it is based on configuration set during the setup of the VM Scale set

## How many web app service plans you need 

![alt text](image-470.png)

**Since web server app plane can only have one OS** 

The correct answer is still B, but probably this question will soon require some update.
- current LTS version of `.NET` Core is called .NET 6 (goes both in windows and Linux)
- .NET 4.7 is not available (.NET 4.8 is) - this goes in windows only
- PHP is available in versions 8.0, 8.1, 8.2 (this goes in linux only)
- Ruby support has ended in April 2023.

## :star: Budget

You have a pay-as-you-go Azure subscription that contains the virtual machines shown in the following table.

![alt text](image-471.png)

![alt text](image-472.png)

The `AG1` action group contains a user named `admin@contoso.com` only.

Correct Answer:  

Box 1: `VM1` and `VM2` continue to run

- The Budget’s scope is `RG1`, so only `VM1` will be handled.

When the budget thresholds you've created are exceeded, only notifications are triggered.    
- To stop resources, you need to setup additional things, none of which are mentioned in the question.  

Box 2: one email notification will be sent each month.

Budget alerts have scope in`RG1`, which includes VM1, but not VM2.
- VM1 consumes `20 Euro/day`, so 20 euros * 30 days = 600 euros.  

The `50%`, `500` Euro limit, will be reached in 25 days (`25*20 = 500`), so an email will be sent.  
The 70% and 100% alert conditions will not be reached within a month, and they don't trigger email actions anyway, because AG1 action group contains a user.

Credit alerts: Credit alerts are generated automatically at 90% and at 100% of your Azure credit balance.

Whenever an alert is generated, it's reflected in cost alerts and in the email sent to the account owners. `90%` and `100%` will not be reached though.


## :star: RG is not considered as resource

You have an Azure subscription named `Subscription1` that contains the following resource group:  
``` 
Name: RG1
Region: West US
Tag: tag1: value1
```

You assign an Azure policy named `Policy1` to `Subscription1` by using the following configurations:  
```
Exclusions: None
Policy definition: Append a tag and its value to resources
Assignment name: Policy1
Parameters:
Tags: tag2 : value2
```

After `Policy1` is assigned, you create a storage account that has the following configuration :  
```
Name: storage1
Location: West US
Resource group: RG1
Tags: tag3 : value3
```

You need to identify which tags are assigned to each resource.

What should you identify?

![alt text](image-477.png)

Assigning a policy goes through all the items that might be affected.   
- Meaning this new policy would go through resources and check if they fit the filters to take action on.   

In this case, RG1 doesn't get anything assigned to it because **resource groups are not considered resources**. 
- If the first part was not a resource group.
lets say a VM, then the policy would have added (appended) another tag to already existing one and it would have tag 1 and tag 2. 

In case of the storage account, that is considered a resource so it keeps its own tag 3 and the policy adds tag 2 alongside it  (no tag 1 coz it created after tag 1)

## :star: `az aks` AKS configuration & Azure Portal for AKS Autoscaler 

![alt text](image-478.png)

:a: 

We need to configure autoscaler for the AKS cluster. 
- We do not want to scale Kubernetes pods, so kubectl command is not needed.

A: `kubectl` command is used for configuring Kubernetes and not AKS cluster.
B: The `az aks` command is used for the AKS cluster configuration.
C: `Set-AzVm` cmdlet is used for VMs.
D: `Azure portal`, under node pools, press scale, then choose auto scale.
E: `Set-AzAks`, creates or updates an AKS cluster, the correct cmdlet is Set-AzAksCluster.

AKS clusters can scale in one of two ways:
1. The cluster autoscaler watches for pods that can't be scheduled on nodes because of resource constraints. The cluster then automatically increases the number of nodes.

2. The horizontal pod autoscaler uses the Metrics Server in a Kubernetes cluster to monitor the resource demand of pods. If an application needs more resources, the number of pods is automatically increased to meet the demand.

## :star::star: Roles for Local Administrator 

![alt text](image-473.png)  
First the only user who can join Azure AD devices is `User 1`.  
- Since `User1` is admin on machine.  
So, the machine can be added.  

Local Administrators Group on Microsoft Azure-joined Devices
By default, the ones are local admins :  
1. global administrator
2. device owners (device administrators). 

admins are managed under :arrow_down:
![alt text](image-474.png)
Since this is not mentioned, so we can assume default.

---

Local Administrators Group on Microsoft Azure-joined Devices:

- To manage a Windows device, you need to be a member of the local administrators group on that device.

:one: Microsoft Azure `Global Administrator` Role
- This role has broad administrative privileges across the entire Azure environment.

:two: Microsoft Azure `Joined Device Local Administrator` Role: 
- This role is specific to the joined device and provides local administrative rights.

:three: The user (device OWNER)
- performing the Azure join is also added to the local administrators group.

:arrow_up:
By adding these roles, you can update the users who can manage a device anytime in Microsoft Azure ID without modifying anything on the device.


The Joined Device Local Administrator role 
- follows the principle of least privilege (PoLP) by granting only necessary rights to manage the device.

## :star: Alert Rate limit thresholds

You have an Azure subscription named Subscription1.
In Subscription1, you create an alert rule named Alert1.
The Alert1 action group is configured as shown in the following exhibit.
![alt text](image-475.png)
- Alert1 alert criteria triggered every minute.

![alt text](image-476.png)


Box 1: `60`
One alert per minute will trigger one email per minute.


Box 2: `12` or `0`
- If it's a typo and it means Alert1, then Answer = 12 (60/5 = 12)
- If it is actually Alert2 then Answer = 0

Since the rage limiting `No more than 1 SMS every 5 minutes` can be send, which equals 12 per hour (60/5 = 12).

Note: Rate limiting is a suspension of notifications that occurs when too many are sent to a particular phone number, email address or device. 

Rate limiting ensures that alerts are manageable and actionable.

The rate limit thresholds are:
- `SMS`: No more than a SMS every 5 minutes.
- `Voice`: No more than a Voice call every 5 minutes.
- `Email`: No more than 100 emails in an hour.
- Other actions are not rate limited.

Reference:
https://docs.microsoft.com/en-us/azure/azure-monitor/platform/alerts-rate-limiting

## az acr build deploy image to aks

![alt text](image-479.png)

## Web Server 80 & DNS server 53

![alt text](image-480.png)  
![alt text](image-481.png)  

Box 1 :  
- `Rule2` blocks ports` 50-60`, which includes port `53`, the DNS port.  
- Internet users can reach to the Web server, since it uses port 80.  

Box 2 :  
- If `Rule2` is removed internet users can reach the DNS server as well.  

Note: Rules are processed in priority order, with lower numbers processed before higher numbers, because lower numbers have higher priority.  
Once traffic matches a rule, processing stops. 

As a result, any rules that exist with lower priorities (higher numbers) that have the same attributes as rules with higher priorities are not processed.  

## Configure NEW VM from an ARM exported from a VM

What can you configure ? From a ARM exported from a VM ?  
![alt text](image-482.png)  

## :star: Runbook can scale up/down size of VM
![alt text](image-483.png)  

Correct Answer: B

Here we need to modify the size of the VM to increase the number of vCPU's assigned to the VM. 
- This can be included as a task in the runbook. 
- The VM size property can be modified by a runbook that is triggered by metrics, but you can schedule it monthly.

`C`: Scheduled vertical scaling could be a solution, **but then you don't need a scheduled runbook** and it states that it does not support multiple active instances. Scale Set is not a n option.

`E`: DSC is only useful to `keep` the resources on a VM (OS, File shares, etc.) in a consistent state, not to change VM properties.

For example :   
You need to ensure that NGINX is available on all the virtual machines after they are deployed.


## DSC & Azure Custom Script Extension

![alt text](image-484.png)

There are several versions of this question in the exam. The question has two correct answers:
1. a Desired State Configuration (DSC) extension
2. a Azure Custom Script (ACS) Extension

The question can have other incorrect answer options, including the following:
✑ the Publish-AzVMDscConfiguration cmdlet
✑ Azure Application Insights

## :star: Auto-Scale of App Service Plan 

You have the App Service plan shown in the following exhibit.

![alt text](image-485.png)


The scale-in settings for the App Service plan are configured as shown in the following exhibit.
![alt text](image-486.png)

The scale out rule is configured with the same duration and cool down tile as the scale in rule.

![alt text](image-487.png)

Box 1: 2
- 70% for 1h, and then 90% for 5 minutes. 
So, from the default of `1` it will scale out out `1` more. 
So, `2` in total.

Box 2: 4
- 90% for 1h and then 25% for 9 minutes. 
So, from the default of 1 it will it scale in to the max 5 (60/5 = 12, which means 6 times scale out, because we have 5 minutes period of cool down).   
Then when it drops to 25% for 9 minutes and it will scale in once after 5 mins (since the average of the last 5 minutes is under 30% ), so it will decrease by 1, so 4 in total. Then it will have a cooldown of 5 minutes before scaling in again, but since only 4 minutes left from 9 minutes (9-5 = 4), it won't scale in again. So, 4 in total.

## Integration Services

You have an Azure subscription.
You have an on-premises virtual machine named VM1. 

The settings for VM1 are shown in the exhibit  
![alt text](image-488.png)

You need to ensure that you can use the disks attached to VM1 as a template for Azure virtual machines.

What should you modify on VM1?
A. the memory
B. the network adapters
C. the hard drive
D. the processor
E. Integration Services

## Scale Set while VM resizing OR O.S Updating

You have an Azure subscription that contains a virtual machine 
scale set.

The scale set contains **four instances** that have the following configurations  
```bash 
Operating system: Windows Server 2016
Size: Standard_D1_v2
```

![alt text](image-490.png)    
![alt text](image-491.png)  
Box 1: `4`
**If you resize the Scale Set all the VMs get resized at once**, thus 4 is the correct answer.

Box 2: `1`
Automatic OS updates update `20%` of the VMs at once, with a minimum of 1 VM instance at a time. Also `4 * 0.2 = 0.8`.

## ransomware

You have an Azure subscription named `Subscription1`. 

Subscription1 contains two Azure virtual machines VM1 and VM2. VM1 and VM2 run Windows Server 2016.
**VM1 is backed up daily by Azure Backup without using the Azure Backup agent.**

VM1 is affected by ransomware that encrypts data.

You need to restore the latest backup of VM1.

To which location can you restore the backup?

Box 1: Any Windows computer that has Internet connectivity  

For files recovery, you download and run a windows executable to map a network drive.
- It can only run when the OS meets the requirements.   

Any computer running `Windows Server 2016` or `Windows 10` is suitable. 

**File recovery can be done from any machine on the Internet.**  

- Note:  
There might be compatibility issues with any Windows computer, so consider VM1 and VM2 only as an answer.

Box 2: VM1 or a new Azure virtual machine only For restoring a VM, you can choose `Create new` or `Replace existing`.

Reference:
- https://docs.microsoft.com/en-us/azure/backup/backup-azure-restore-files-from-vm
- https://github.com/MicrosoftDocs/azure-docs/blob/master/articles/backup/backup-azure-

## Backup Pre-Check Warning Status : AZ VM AGENT WaAppAgent

![alt text](image-492.png)

## 

You have an Azure virtual machine named VM1. 

VM1 was deployed by using a custom Azure Resource Manager template named `ARM1.json`.  

You receive a notification that VM1 will be affected by maintenance.  

You need to move VM1 to a different host immediately.  

Solution: From the Overview blade, you move the virtual machine to a different resource group.

## ARM update/(2 or 3)fault domain configuration

You have an Azure subscription.  

You plan to use Azure Resource Manager templates to deploy `50` Azure virtual machines that will be part of the same availability set.  

You need to ensure that as many virtual machines as possible are available if the **fabric fails** or **during servicing**.  

How should you configure the template? 
![alt text](image-493.png)  

:a: 

box 1  `2 or 3`
Use two fault domains.
2 or 3 is max, depending on which region you are in.  

box 2 `20`
Use 20 for platformUpdateDomainCount
Increasing the update domain helps with capacity and availability planning when the platform reboots nodes.  
- A higher number for the pool (20 is max) means that fewer of their nodes in any given availability set would be rebooted at once.    

## Error Event Logged

You have an Azure virtual machine named VM1 that runs Windows Server 2016.  

You need to create an alert in Azure when more than two error events are logged to the System event log on VM1 within an hour.  

Solution: You create an Azure Log Analytics workspace and configure the Agent configuration settings. You install the Microsoft Monitoring Agent on VM1. You create an alert in Azure Monitor and specify the Log Analytics workspace as the source.

## Scale Set Scale-in/out

You deploy a virtual machine scale set that is configured  
![alt text](image-494.png)  

![alt text](image-495.png)  

box-1: `3`
box-2: `1`

## SKU of App Service Plan Limit by Region

![alt text](image-496.png)

- You can have 
`10` Free  
and `100` Standard  
`100` Premium ASP per Region.

## ARM VM creation `New-Az` command

![alt text](image-497.png)  
Box 1: `New-AzResourceGroupDeployment`. 

This cmdlet allows you to use a custom ARM template file to deploy resources to a resource group.   
For example :  
```bash 
New-AzResourceGroup `
-Name $resourceGroupName `
-Location $location

New-AzResourceGroupDeployment `
-ResourceGroupName $resourceGroupName `
-TemplateUri "https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/quickstarts/microsoft.compute/vm-simple-windows/azuredeploy.json" `
-adminUsername $adminUsername `
-adminPassword $adminPassword `
-dnsLabelPrefix $dnsLabelPrefix
```

Box 2: `-ResourceGroupName RG1`. 

It's one of parameters of New-`AzResourceGroupDeployment` to specify to which resource group you want to deploy resources.

You could use `New-AzVm` to create a VM, but it doesn't use a template. 
- You would need to provide all parameters in the command line.


## deploy a YAML file to AKS `kubectl apply -f`

You deploy an Azure Kubernetes Service (AKS) cluster named AKS1.
You need to deploy a YAML file to AKS1.

Solution: From Azure Cloud Shell, you run az aks.

```bash 
kubectl apply -f <file_name>.yaml
```

## :star: Daily Backup for App SERVICE into storage acc.

You have an Azure App Service app named `WebApp1` that contains two folders named Folder1 and Folder2.

You need to configure a daily backup of WebApp1. 

The solution must ensure that Folder2 is excluded from the backup.

What should you create first, and what should you use to exclude Folder2? 

![alt text](image-498.png)
:a: 

- You need a `Recovery service vault` if you want to backup VMs, File Shares, SAP HANA in a VM or SQL Server in a VM.
- You need a `Backup vault` if you want to backup Azure Disks, Azure Blobs or Azure Database for PostgreSQL Server.

The question asks about an App Service, this one backs up to a storage account.


## `New-AzResourceGroupDeployment`

You develop the following Azure Resource Manager (ARM) template to create a resource group and deploy an Azure Storage account to the resource group.

D is correct here.

We are creating RG and storage account in this RG.

By using `New-AzResourceGroupDeployment` command means 
> Adds an Azure deployment to a resource group.

## Microsoft Azure Recovery Services Agent 

![alt text](image-499.png)  

:a: 
`Microsoft Azure Recovery Services Agent` also known as `MARS` or `Azure Backup Agent` can be used to restore data for entire volume or just individual folders and files.  

## :star: Create a virtual machine that will have multiple data disks by ARM

You need to use an Azure Resource Manager (ARM) template to create a virtual machine that will have multiple data disks.

How should you complete the template? 

![alt text](image-500.png)

## Multiple NICs in VM

![alt text](image-501.png)  


:memo: A VM must have at least one NIC.  
- **A virtual machine can have more than one NIC**, depending on the size of the VM you create.

:memo: Multiple NICs allow a VM to connect to different subnets.

:memo: **Each NIC attached to a VM must exist in the same location and subscription as the VM**.

:memo: Each NIC must be connected to a VNet that exists in the same Azure location and subscription as the NIC.

## Services allow you run the images for Win or Linux

![alt text](image-502.png)
![alt text](image-503.png)

> Container Apps not supports to WIN Server

## :question: Assign a managed identity to the App.

![alt text](image-504.png)

I'm also in for answer B, since answer A needs a service principal. The only way to get one for a service is a managed identity (system or user generated).

## ARM DependsON NIC for VM

![alt text](image-505.png)


The most direct and crucial dependency for VM1 among the listed resources is NIC1 (Option B). 
- The NIC acts as the bridge between the VM and the other network resources like the VNet, public IP, and NSG. Hence, it's essential to ensure that `NIC1` is deployed before VM1.

## deploy ARM New-AzSubscriptionDeployment 

![alt text](image-506.png)

A is correct because RG is already mentioned in the template.  
How could be C ?
You need to deploy a resource group to the subscription scope. The New-AzReesourceGroupDeployment deploy a resource inside the resource groupe scope.

## -dependsON: resoureceID & -storageProfile: ImageReference

![alt text](image-507.png)

## Pricing plan Standard to auto-scaling, and domain TXT record type

You need to configure a new Azure App Service app named WebApp1. The solution must meet the following requirements:
- WebApp1 must be able to verify a custom domain name of `app.contoso.com`.
- WebApp1 must be able to automatically scale up to eight instances.
- Costs and administrative effort must be minimized.

Which pricing plan should you choose, and which type of record should you use to verify the domain?     
![alt text](image-508.png)

WebApp1 must be able to verify a custom domain name of app.contoso.com. 
- All paid tiers (Basic, Standard, Premium, Isolated) allow for custom domains.

WebApp1 must be able to automatically scale up to eight instances. 
- Auto-scaling is a feature that is available in the `Standard`, `Premium`, and `Isolated` tiers.  
It is not available in the `Basic` tier, which allows you to manually scale up to `3` instances.

Costs and administrative effort must be minimized.
- Pricing Plan: Given these requirements, the best option is the `Standard` tier.   It offers both auto-scaling and custom domains, while being less expensive than the `Premium` or `Isolated` tiers.  
The Basic tier does not support auto-scaling   
The Free and Shared tiers do not support custom domains or auto-scaling.  

For VERIFYING a custom domain, Azure uses a `MX` or `TXT` record. 
- The `A` record cannot be used for domain verification

## num of web service plan depends on OS

Can run only on Windows: .NET, ASP.NET
Can run only on Linux: Python
Can run on either Windows/Linux: PHP

From Azure documentation:
ASP.NET Core (on Windows or Linux)
ASP.NET (on Windows)
PHP (on Windows or Linux)
Ruby (on Linux)
Node.js (on Windows or Linux)
Java (on Windows or Linux)
Python (on Linux)
HTML
Custom container (Windows or Linux)

## :star: web app auto-scale rule with cooling down minute

You have an Azure App Service app named App1 that contains two running instances.

![alt text](image-509.png)

For the Instance limits scale condition setting, you set Maximum to 5.

During a 30-minute period, App1 uses 80 percent of the available memory.

What is the maximum number of instances for App1 during the 30-minute period?

:a: 
Start at 2 instances, after 15 min, > 70%, then +1 instance
Cooling 5 mins, still >70%, then +1 instance  
Cooling 5 mins, still >70%, then +1 instance 
Cooling 5 mins, still >70%, since max 5 instances, keep 5 instances only

## OS disk of VM can be used as a source for a version of image

![alt text](image-513.png)

You create an Azure Compute Gallery named ComputeGallery1
![alt text](image-514.png)

In ComputeGallery1, you create a virtual machine image definition named Image1
![alt text](image-515.png)

Neither the region, vCPU count, nor the VM generation had any impact on my ability to select a particular VM OS disk as a source for an image version.

## ARM New-AzSubscriptionDeployment

![alt text](image-512.png)

![alt text](image-510.png)
![alt text](image-511.png)

1. Yes. `RG0` will be created with location from template file.  
For subscription level deployments, you must provide a location for the deployment.    
The location of the deployment is separate from the location of the resources you deploy.  
**The deployment location specifies where to store deployment data**.
2. No. 
Only `RG0` and `RG3` will be created, `RG1` and `RG2` already exist and can't be created.
3. No. 
`RG3` will be created in `eastus` region.

## ARM Join Devices `type` & `ProtectedSettings` with password

![alt text](image-516.png)  

uses the `Microsoft.Compute/virtualMachines/extensions` resource type to install the Active Directory domain join extension.  

Parameters are used that you specify at deployment time.   

When the extension is deployed, the VM is joined to the specified managed domain.  

> https://docs.microsoft.com/en-us/azure/active-directory-domain-services/join-windows-vm-template  


## K8s Modify the Network configuration setting & AKS-Managed Azure Active Directory

![alt text](image-517.png)      
 
![alt text](image-518.png)  

1) Modify the Network configuration setting
"To run an AKS cluster that supports node pools for Windows Server containers,**your cluster needs to use a network policy that uses Azure CNI (advanced) network plugin.**"

2. If the Network configuration is Kubenet, you will not be able to add a windows node pool, you have to change it from Kubenet to Azure CNI first.  
Next step, you need to add a new node pool  
All AKS clusters are created with a default first node pool, which is Linux-based. This node pool contains system services that are needed for the cluster to function.
- The first Linux-based node pool can't be deleted unless the AKS cluster itself is deleted.  


> Ref: https://learn.microsoft.com/en-us/azure/aks/learn/quick-windows-container-deploy-cli

> Ref: https://learn.microsoft.com/en-us/azure/aks/cluster-container-registry-integration?tabs=azure-cli

## Edit existing Node

• Deploy two new nodes to perform the upgrade.
• Minimize costs.

![alt text](image-519.png)

We want to edit an existing node pool, so we cannot use "add":
"Add a node pool to the managed Kubernetes cluster."

We want to update the properties of the node pool, so we need to use:
`az aks nodepool update` to Update a node pool properties.

We want to set it up to use more nodes during an update, so this one is right:
`--max-surge` to extra nodes used to speed upgrade. 
- **When specified, it represents the number or percent used, eg. 5 or 33%**.  


## New-AzResourceGroup & New-AzResourceGroupDeployment

You create the following file named Deploy.json.
![alt text](image-520.png)  

And Deploy it
![alt text](image-521.png)


![alt text](image-522.png)  

Y: The 4 resources created are the RG1 resource group + the 3 storage accounts

N: the location of the storage accounts is defined by the parameter "location" in the "resources" item that has the value of the Resource Group (stated by the "resourceGroup().location" function that returns the location of the resource group RG1 which is in Central US)

Y: the names of the storages account have the prefix given by the copyIndex() function in 
`"name": "[concat(copyIndex(),'storage',uniqueString(resourceGroup().id))]"`, 
which starts at the position 0

## New-AzResourceGroupDeployment 

• Deploy new resources to RG1.
• Remove all the existing resources from RG1 before deploying the new resources.

![alt text](image-523.png)

## Multi-container groups currently support only Linux containers  

![alt text](image-524.png)  

Answer is D.  
Multi-container groups currently support only Linux containers. For Windows containers, Azure Container Instances only supports deployment of a single container instance.  

While we are working to bring all features to Windows containers, you can find current platform differences in the service

> https://learn.microsoft.com/en-us/azure/container-instances/container-instances-container-groups

## Deploy an instance of AZ firewall Premium with STATIC IPv4 IP address

![alt text](image-525.png)

`B` should be the correct answer instead.

Azure Firewall
- Dynamic IPv4: No
- Static IPv4: Yes
- Dynamic IPv6: No
- Static IPv6: No

Azure Firewall is a cloud-based network security service that protects your Azure Virtual Network resources. 

Azure Firewall requires at least one public static IP address to be configured. 
- This IP or set of IPs are used as the external connection point to the firewall. 

Azure Firewall supports `standard` SKU public IP addresses. 
- `Basic` SKU public IP address and public IP prefixes aren't supported.  

https://learn.microsoft.com/en-us/azure/virtual-network/ip-services/public-ip-addresses#at-a-glance

https://learn.microsoft.com/en-us/azure/ virtual-network/ip-services/configure-public-ip-firewall

## :question:

![alt text](image-526.png)

## Use scope to target the resource group for storage account.

![alt text](image-527.png)  

The answer is scope. 
- We would use scope to target the resource group for storage account.  


https://ochzhen.com/blog/create-resource-group-azure-bicep

## New-AzDeployment -Location westus -TemplateFile "deploy.json"

![alt text](image-526.png)  
![alt text](image-528.png)    

YNY
- The deployment creates 3 RGs called `RG0`, `RG1`, `RG2` as the index is `0`-based.
- You can deploy to RG1 as the lock is delete.
- You can't deploy to RG2 as the lock is read-only, hence it can't be modified.

## :star: Web App with VNet 

![alt text](image-529.png)


![alt text](image-530.png)
YNN
- Yes: 
Using virtual network integration enables your app to access:
Resources in the virtual network you're integrated with.
Resources in virtual networks peered to the virtual network your app is integrated with including global peering connections.
- NO 
Virtual network integration is used only to make outbound calls from your app into your virtual network
- NO 
There are some limitations with using virtual network integration : The feature isn't available for `Isolated` plan apps in an App Service Environment

> https://learn.microsoft.com/en-us/azure/app-service/overview-vnet-integration

## connect to two different machines on the same port

![alt text](image-531.png)

Key is port 3389 from the internet for both VMs. If we want to connect to two different machines on the same port we need to have two different frontend IPs for the port forwarding.

## Minium num of NIC & minimum num of NSGs

You plan to deploy **five virtual machines** to a virtual network subnet.

1. Each virtual machine will have a public IP address and a private IP address.
2. Each virtual machine requires the same inbound and outbound security rules.

![alt text](image-532.png)  

Box 1: 5
- A public and a private IP address can be assigned to a single network interface.

Box 2: 1
You can associate `zero`, or `one`, network security group to each virtual network subnet and network interface in a virtual machine. 

The same network security group can be associated to as many subnets and network interfaces as you choose.

## Azure container registry

![alt text](image-533.png)

## A Record and Private IP Addr

The virtual machines are registered (added) to the private zone as `A` records pointing to their private IP addresses.

Since both VM1 & VM2 are in same VNet1 and the VNet1 is liked under `adatum.com` domain (Private DNS Zone->Setting->virtual network links).

## Log Analytics workspace collect data of NSG flow

![alt text](image-534.png)

Box 1: An Azure Log Analytics workspace
In the Azure portal you can set up a Log Analytics workspace, which is a unique Log Analytics environment with its own data repository, data sources, and solutions.

Box 2: NSG1
NSG flow logs allow viewing information about ingress and egress IP traffic through a Network security group. 

Through this, the IP addresses that connect to the ILB can be monitored when the diagnostics are enabled on a Network Security Group.

We cannot enable diagnostics on an internal load balancer to check for the IP addresses.

As for Internal LB, it is basic one. 
Basic can only connect to storage account. 
Also, Basic LB has only activity logs, which doesn't include the connectivity workflow. 
So, we need to use NSG to meet the mentioned requirements.

##

![alt text](image-535.png)

B - HA ports need are not supported by a basic loadbalancer
C - You need a floating ip for the active-active configuration to switch over quickly
F - You need 2 backend pools for the 2 different services

## Auto registration

You have an Azure subscription. The subscription contains virtual machines that run Windows Server 2016 and are configured as shown in the following table.
![alt text](image-449.png)

You create a public Azure DNS zone named `adatum.com` and a private Azure DNS zone named `contoso.com`.

You create a virtual network link for `contoso.com` as shown in the following exhibit.
![alt text](image-489.png)

![alt text](image-415.png)

:a: 

All three VMs are in VNET2. 
- Auto registration is enabled for private Azure DNS zone named `contoso.com`, which is linked to VNET2. 

So, VM1, VM2 and VM3 will auto-register their host records to `contoso.com`.

- None of the VM will auto-register to the public Azure DNS zone named `adatum.com`. You cannot register private IPs on the internet (`adatum.com`)

Box 1: Yes
Auto registration is enabled for private Azure DNS zone named contoso.com.

Box 2: Yes
Auto registration is enabled for private Azure DNS zone named contoso.com.

Box 3: No
None of the VM will auto-register to the public Azure DNS zone named `adatum.com`

## Actions of Adding new space to peering VNet

![alt text](image-537.png)  
 
![alt text](image-538.png)  

## :star: All resources moved to the new resource groups, but the region did not change

![alt text](image-539.png)  

> All resources moved to the new resource groups, but the region did not change

1. YES. I was able to move the storage from RG1 to RG2, however it stayed in the West US region.  
2. YES. **I was able to move NIC1 from RG1 to RG2 which was associated with VM1 and VNET1 subnet1, however it stayed in the West US region**.  
3. NO. The location of IP2 did not change.   
However I was able to move LP2 from RG2 to RG1 as it isn't associated with any other resource, however it stayed in the East US region.


## Web App access VM via Application Gateway 

![alt text](image-540.png)

## Enable Desired State Configuration Extension for VM

You create an Azure VM named VM1 that runs Windows Server 2019.
VM1 is configured as shown  
![alt text](image-541.png)  

You need to enable Desired State Configuration for VM1.    
A. Connect to VM1.    
B. Start VM1.   
C. Capture a snapshot of VM1.   
D. Configure a DNS name for VM1.   

:a: 

Correct Answer: B

> Status is Stopped (Deallocated). 

The DSC extension for Windows requires that the target Virtual Machine is able to communicate with Azure. 

First you start the VM, because you need VM online to deploy DSC Extension.

## Connect to RDB from TCP 3389 

You have an Azure subscription that contains the following resources:
- A virtual network that has a subnet named `Subnet1`
- Two network security groups (NSGs) named `NSG-VM1` and `NSG-Subnet1`
- A virtual machine named `VM1` that has the required Windows Server configurations to allow Remote Desktop connections

`NSG-Subnet1` has the default inbound security rules only.

`NSG-VM1` has the default inbound security rules and the following custom inbound security rule:
```bash 
Priority: 100
Source: Any
Source port range: *
Destination: *
Destination port range: 3389
Protocol: UDP
Action: Allow
```

`VM1` has a public IP address and is connected to Subnet1. 

NSG-VM1 is associated to the network interface of VM1.   
NSG-Subnet1 is associated to Subnet1.  

You need to be able to establish Remote Desktop connections from the internet to VM1.

Solutions:  
1. :x: You add an inbound security rule to `NSG-Subnet1` that allows connections from the internet source to the VirtualNetwork destination for port range 3389 and uses the UDP protocol.   
:memo:The default port for RDP is TCP port `3389`.   

2. :o: You add an inbound security rule to `NSG-Subnet1` and `NSG-VM1` that allows connections **from the internet source to the VirtualNetwork destination for port range `3389` and uses the TCP protocol**.  

## :question: 

You have a virtual network named VNet1 that has the configuration  
![alt text](image-542.png)  

![alt text](image-543.png)  

Box 1: Add  an address space 
- One can add additional address space (`192.168.0.0/16`) to the VNet1, without having to delete existing (`10.2.0.0/16`).

Box 2: Add subnet 
- Defined 'default' subnet from example (`10.2.0.0/24`) contains 254 IP addresses, with last IP being `10.2.0.254`. 
In order to assign `10.2.1.0/24` IP address to VM we need to create add new subnet.

## apply AZ CLI to move the DNS zone name to an Azure DNS zone in Subscription  

![alt text](image-544.png)

## An inbound NAT rule to direct RDP to a VM

![alt text](image-545.png)

## Basic SKU LB : single availability-Set & Scale Set

![alt text](image-546.png)  

![alt text](image-547.png)  

 
Basic Load Balancer:  
- Backend pool endpoints for VMs in a **SINGLE availability set** or **virtual machine scale set**.  

Load Balancer `LB1` Configuration instructs that  
Subnet `Subnet12` Association will be used to assign an IP for the internal load balancer, not to load balance the VMs in the Subnet.    

Box 1: Yes  
- VM1 and VM are in the Availability Set.  

Box 2: No    
- Both VMs are not part of any Availability Set or Scale Set.  

Box 3: No  
- Both VMs are not part of any Availability Set or Scale Set.  

## You can only LINK VNets to private DNS zones only

![alt text](image-548.png)  
    
Box 1: Private
Box 2: Private

You can only link VNETs to private DNS zones only and accordingly auto register a VNET only to a private DNS zones. 
- Private DNS zones can be linked with VNETs (not public ones). 
- And VM can auto-register to any private DNS zone linked with the VNet and with auto-registration option set.

To resolve the records of a private DNS zone from your VNet, you must link the virtual network with the zone. 
- Linked virtual networks have full access and can resolve all DNS records published in the private zone.

## Actions of Site to Site VPN  

You have an on-premises network that you plan to connect to Azure by using a site-so-site VPN.

In Azure, you have an Azure virtual network named VNet1 that uses an address space of 10.0.0.0/16 VNet1 contains a subnet named Subnet1 that uses an address space of 10.0.0.0/24.

You need to create a site-to-site VPN to Azure.
Which four actions should you perform in sequence? 

:a: : 

:one: Start with a Gateway subnet. 
- You need the subnet in place first before you can associate a VPN gateway with it, which is what is created next.

:two: Create a VPN gateway. Associate the VPN gateway with the gateway subnet you created (there are other steps but for the sake of what is available for answers, the prem side is now configured)

Now for the on-premise side.

:one: Create a local gateway. You need the local gateway in order to complete the tunnel, then you can create a VPN connection

## Managed Disks & Availability Options in VM configuration

You need to ensure that VM1 can be created in an Availability Zone.

Which two settings should you modify

:a: 

Correct Answer: A and C

In `Basic`
A: Your VMs should use managed disks if you want to move them to an Availability Zone by using Site Recovery.

In `Disks` 
C: When you create a VM for an Availability Zone, Under Settings > High availability, select one of the numbered zones from the Availability zone dropdown.

Reference:
https://docs.microsoft.com/en-us/azure/site-recovery/move-azure-vms-avset-azone

https://docs.microsoft.com/en-us/azure/virtual-machines/windows/create-portal-availability-zone

https://docs.microsoft.com/en-us/azure/virtual-machines/manage-availability

https://docs.microsoft.com/en-us/azure/availability-zones/az-overview#availability-zones

## Add VM to VS scale set

![alt text](image-549.png)

## Apply P2S VPN instead of installing the certificate

You have a computer named `Computer1` that has a point-to-site VPN connection to an Azure virtual network named `VNet1`. 

The point-to-site connection uses a self-signed certificate.

From Azure, you download and install the VPN client configuration package on a computer named `Computer2`.

You need to ensure that you can establish a point-to-site VPN connection to `VNet1` from `Computer2`.

Solutions  
:x: You modify the Azure Active Directory (Azure AD) authentication policies.
:x: You join Computer2 to Azure Active Directory (Azure AD).


Apply P2S VPN : 

Instead export the client certificate from Computer1 and install the certificate on Computer2.

A Point-to-Site VPN gateway connection lets you create a secure connection to your virtual network from an individual client computer. 
- A P2S connection is established by starting it from the client computer. 

This solution is useful for telecommuters who want to connect to Azure VNets from a remote location, such as from home or a conference. 

P2S VPN is also a useful solution to use instead of S2S VPN when you have only a few clients that need to connect to a VNet. 
- This article applies to the Resource Manager deployment model.


## Policy to block TCP port 8080 btw VNets 

You have an Azure subscription that contains `10` virtual networks. 

The virtual networks are hosted in separate resource groups.

Another administrator plans to create several network security groups (NSGs) in the subscription.

You need to ensure that when an NSG is created, it automatically blocks TCP port `8080` between the virtual networks.

Solution: 
:x: You create a resource lock, and then you assign the lock to the subscription.
:x: You assign a built-in policy definition to the subscription.

## All VM can resolve DNS using DNS service on a VM

![alt text](image-550.png)  

## SKU load balancer

![alt text](image-551.png)

Solutions   

:x: You create a Basic SKU public IP address, associate the address to the network interface of VM1, and then start VM1.

:x: You create a Standard SKU public IP address, associate the address to the network interface of VM1, and then stop VM2.

:o: You create two Standard SKU public IP addresses and associate a Standard SKU public IP address to the network interface of each virtual machine.

:a: :  

You can only attach virtual machines that are in the same location and on the same virtual network as the LB. Virtual machines must have a standard SKU public IP or no public IP.

The LB needs to be a standard SKU to accept individual VMs outside an availability set or vmss. VMs do not need to have public IPs but if they do have them they have to be standard SKU. Vms can only be from a single network. When they don’t have a public IP they are assigned an ephemeral IP.

Also, when adding them to a backend pool, it doesn’t matter in which status are the VMs.

Note: Load balancer and the public IP address SKU must match when you use them with public IP addresses.

## Priority of NSG rule

![alt text](image-552.png)

You deploy a web server on VM1, and then create a secure website that is accessible by using the HTTPS protocol. VM1 is used as a web server only.

You need to ensure that users can connect to the website from the Internet.

What should you do?
A. Modify the protocol of Rule4
B. Delete Rule1
C. For Rule5, change the Action to Allow and change the priority to 401 Most Voted
D. Create a new inbound rule that allows TCP protocol 443 and configure the rule to have a priority of 501.


Correct Answer: C

HTTPS uses port 443.
Rule2, with priority 500, denies HTTPS traffic.
Rule5, with priority changed from 2000 to 401, would allow HTTPS traffic.

Note: Priority is a number between 100 and 4096. Rules are processed in priority order, with lower numbers processed before higher numbers, because lower numbers have higher priority. Once traffic matches a rule, processing stops. As a result, any rules that exist with lower priorities (higher numbers) that have the same attributes as rules with higher priorities are not processed.

##

You have Azure virtual machines that run Windows Server 2019
![alt text](image-554.png)


## Location of NIC and VNET

![alt text](image-553.png)

## configuring the name servers for `adatum.com` at the domain register

![alt text](image-556.png)

You create a public Azure DNS zone named `adatum.com` and a private Azure DNS zone named `contoso.com`.

For `controso.com`, you create a virtual network link named `link1`.  

![alt text](image-555.png)

You discover that VM1 can resolve names in `contoso.com` but cannot resolve names in `adatum.com`. 

VM1 can resolve other hosts on the Internet.

You need to ensure that VM1 can resolve host names in `adatum.com`.

A. Update the DNS suffix on VM1 to be `adatum.com`.    
B. Configure the name servers for `adatum.com` at the domain registrar.  
C. Create an SRV record in the `contoso.com` zone.  
D. Modify the Access control (IAM) settings for link1.  

:a: 

Correct Answer: B

`Adatum.com` is a public DNS zone. 
- The Internet top level domain DNS servers need to know which DNS servers to direct DNS queries for `adatum.com` to. 
- You configure this by configuring the name servers for `adatum.com` at the domain register.

Domain Registrar :  
- A domain registrar is a company or service that allows you to register and manage domain names (such as `example.com` or `mywebsite.net`).
- When you want to acquire a domain name, you typically go through a domain registrar to purchase it.
- The registrar maintains records of domain ownership, handles domain renewals, and provides tools for managing DNS settings associated with the domain.

## IP flow verify for NSG rule and Connection troubleshoot for endpoint to endpoint

You plan to use Azure Network Watcher to perform the following tasks:  

- Task1: Identify a security rule that prevents a network packet from reaching an Azure virtual machine.
- Task2: Validate outbound connectivity from an Azure virtual machine to an external host.

:a: 

Box 1: IP flow verify
At some point, a VM may become unable to communicate with other resources, because of a security rule. 

The IP flow verify capability enables you to specify a source and destination IPv4 address, port, protocol (TCP or UDP), and traffic direction (inbound or outbound). 

IP flow verify then tests the communication and informs you if the connection succeeds or fails. 
- If the connection fails, IP flow verify tells you which.

Box 2: Connection troubleshoot

Diagnose outbound connections from a VM: 

The connection troubleshoot capability enables you to test a connection between a VM and another VM, an FQDN, a URI, or an IPv4 address.

The test returns similar information returned when using the connection monitor capability, but tests the connection at a point in time, rather than monitoring it over time, as connection monitor does. 

## :star: NIC configured DNS servers takes precedence over VNET configured DNS servers.

You have an Azure subscription that contains the Azure virtual machines shown in the following table.  
![alt text](image-558.png)

You configure the network interfaces of the virtual machines to use the settings shown in the following table.  
![alt text](image-559.png)  

From the settings of VNET1 you configure the DNS servers shown in the following exhibit.  
![alt text](image-536.png)  

The virtual machines can successfully connect to the DNS server that has an IP address of `192.168.10.15` and the DNS server that has an IP address of `193.77.134.10`.

![alt text](image-557.png)

> NIC configured DNS servers takes precedence over VNET configured DNS servers.

Box 1: Yes
- AS per link the DNS is set on the VNET level
- VM1 uses the VNET configured DNS `193.77.134.10`.
You can specify DNS server IP addresses in the VNet settings. The setting is applied as the default DNS server(s) for all VMs in the VNet.

Box 2: No
- VM2 uses the NIC configured DNS `192.168.10.15`.
You can set DNS servers per VM or cloud service to override the default network settings.  
- This VM has `192.168.10.5` set as DNS server, so it overrides the default DNS set on VNET1.  

Box 3: Yes
- VM3 uses the NIC configured DNS `192.168.10.15`  
You can set DNS servers per VM or cloud service to override the default network settings.   
- This VM has `192.168.10.5` set as DNS server, so it overrides the default DNS set on `VNET1`.  

## RO or Delete locks does not have any impact for Move operation

![alt text](image-561.png)  

:a: 

Box 1: IP1, VNET2, and storage1
Box 2: IP2, VNET2, and storage2

**RO or Delete locks does not have any impact for Move operation** and it doesn`t matter if it comes from RG level or are directly attached to the resource.

## P2S export the client certificate from local-device and install it in other local-device

You have a computer named `Computer1` that has a point-to-site VPN connection to an Azure virtual network named `VNet1`. 

The point-to-site connection uses a self-signed certificate.

From Azure, you download and install the VPN client configuration package on a computer named `Computer2`.

You need to ensure that you can establish a point-to-site VPN connection to `VNet1` from `Computer2`.

Solution: 

:o: You export the client certificate from Computer1 and install the certificate on Computer2.

## custom policy definition to block tcp 8080

You have an Azure subscription that contains 10 virtual networks. The virtual networks are hosted in separate resource groups.
Another administrator plans to create several network security groups (NSGs) in the subscription.
You need to ensure that when an NSG is created, it automatically blocks TCP port 8080 between the virtual networks.


Solution: 

:x: From the Resource providers blade, you unregister the Microsoft.ClassicNetwork provider.

:o: You configure a custom policy definition, and then you assign the policy to the subscription.

:a:

You need to use a custom policy definition, because there is not a built-in policy.

Resource policy definition used by Azure Policy enables you to establish conventions for resources in your organization by describing when the policy is enforced and what effect to take. By defining conventions, you can control costs and more easily manage your resources.

## Add VMs to LB

![alt text](image-593.png)

## Peering VNETs

![alt text](image-592.png)

![alt text](image-562.png)


```
VNET1: 10.10.10.0 - 10.10.10.255
VNET2: 172.16.0.0 - 172.16.255.255
VNETA: 10.10.128.0 - 10.10.255.255
```

Box 1: No
To create a VNet to VNet VPN you need to have a special Gateway Subnet. Here, the VNet has no sufficient address space to create a Gateway Subnet and thus to establish a VNet to VNet VPN connection.

Box 2: Yes
For VNet peering the only consideration is that the VNets do not overlap. VNET1 and VNET2 do not overlap.

Box 3: Yes
For VNet peering the only consideration is that the VNets do not overlap. VNET1 and VNETA do not overlap.

## Ensure that connections to `App1` can be established successfully from `131.107.100.50` over TCP port `443`

You have an app named `App1` that is installed on two Azure virtual machines named `VM1` and `VM2`. 

Connections to `App1` are managed by using an Azure Load Balancer.  

NSG for VM2  
![alt text](image-563.png)

You discover that connections to `App1` from `131.107.100.50` over TCP port `443` fail.

You verify that the Load Balancer rules are configured correctly.

You need to ensure that connections to `App1` can be established successfully from `131.107.100.50` over TCP port `443`.

:x: You delete the `BlockAllOther443` inbound security rule.  
:x: You modify the priority of the `Allow_131.107.100.50` inbound security rule.  
:o: You create an inbound security rule that allows any traffic from the `AzureLoadBalancer` source and has a priority  of `150`.


> "Attach network interface" Button is enable! 
> That means, VM is `Stopped` and `deallocated`!

## RTT & Connection Monitor 

You have two Azure virtual networks named VNet1 and VNet2. VNet1 contains an Azure virtual machine named VM1. VNet2 contains an Azure virtual machine named VM2.
VM1 hosts a frontend application that connects to VM2 to retrieve data.
Users report that the frontend application is slower than usual.
You need to view the average round-trip time (RTT) of the packets from VM1 to VM2.

Which Azure Network Watcher feature should you use?
A. IP flow verify
B. Connection troubleshoot
**C. Connection monitor Most Voted**
D. NSG flow logs

## SKU for LB

![alt text](image-564.png)
![alt text](image-565.png)

##

You have an on-premises data center and an Azure subscription. 

The data center contains two VPN devices. The subscription contains an Azure virtual network named VNet1. 

VNet1 contains a gateway subnet.
You need to create a site-to-site VPN. 

The solution must ensure that if a single instance of an Azure VPN gateway fails, or a single on-premises VPN device fails, the failure will not cause an interruption that is longer than two minutes.

What is the minimum number of public IP addresses, virtual network gateways, and local network gateways required in Azure? To answer, select the appropriate options in the answer area.

![alt text](image-574.png)

The "local network gateway" IS an azure resource (the on-prem VPN thing is called "VPN Device" in Microsoft Azure terminology)
(Hence correct answer is: 2-1-2)
You can try to create a "Local NW GW" yourself in Portal "Create a local network gateway to represent the on-premises site that you want to connect to a virtual network. The local network gateway specifies the public IP address of the VPN device and IP address ranges located on the on-premises site. Later, create a VPN gateway connection between the virtual network gateway for the virtual network, and the local network gateway for the on-premises site."

And if you try to create a VPN Gateway Standard in Active-Active mode you will see that only one VNet is required. The A-A config takes care of the rest.

Hence the following _in Azure_:
2 Public IPs (assuming Active-Active, which comes from <2 minutes requirement)
1 VNet (see config of VPN GW in Azure)
2 Local Gateways (as you have 2 "VPN Devices" on-prem)

##

![alt text](image-566.png)

## ARM VNET

You plan to use an Azure Resource Manager template to deploy a virtual network named VNET1 that will use Azure Bastion.
How should you complete the template? 

![alt text](image-567.png)
. All Azure Bastion resources deployed in subnets of size /27 prior to this date are unaffected by this change and will continue to work, but we highly recommend increasing the size of any existing AzureBastionSubnet to /26 in case you choose to take advantage of host scaling in the future.

## packet capture for period of time

You manage a virtual network named VNet1 that is hosted in the West US Azure region.
VNet1 hosts two virtual machines named VM1 and VM2 that run Windows Server.
You need to inspect all the network traffic from VM1 to VM2 for a period of three hours.


:o: From Azure Network Watcher, you create a packet capture.

## Route-base S2P

![alt text](image-568.png)  
P2S client doesn't have fixed IPs.  
Policy based on combinations of prefixes from both networks to define how traffic is encrypted/decrypted through IPsec tunnels.    

## Auto-registration 

![alt text](image-570.png)

In Azure, you create a private DNS zone named adatum.com. You set the registration virtual network to VNet2. The adatum.com zone is configured as shown in the following  
![alt text](image-571.png)

![alt text](image-569.png)

VNet1 (NOT A Registration Network) : VM5
VNet2 (IS A Registration Network) : 
- VM1, VM6 and VM9

So here we go:

1. VM5 is in VNet1 - answer is NO.
2. VM5 is in VNet1 - answer is NO.
3. VM6 is in VNet2 - answer is YES.

##

![alt text](image-573.png)  

A virtual network can be linked to private DNS zone as a registration or as a resolution virtual network.  

Registration virtual network:
- A private DNS zone can have multiple registration virtual networks. 
- However, every virtual network can only have one registration zone associated with it.

Resolution virtual network:
- One private DNS zone can have multiple resolution virtual networks and a virtual network can have multiple resolution zones associated to it.

![alt text](image-572.png)


1. Yes
No registration zone for VNET2.

2. Yes
A virtual network can have multiple resolution zones associated to it.

3. Yes
No registration zone for VNET2.

## 

![alt text](image-575.png)  

1) Remove the Public IP addresses. They are basic Public IPs and we're using a Standard Load Balancer which aren't compatible.
2) Create a backend pool and health probes.
3) Create a load balancer rule.

## S2S

You have an Azure subscription that contains two on-premises locations named site1 and site2.
You need to connect site1 and site2 by using an Azure Virtual WAN.
Which four actions should you perform in sequence

Correct answer:
1. Create Azure Virtual WAN
2. Create Virtual Hub
3. Create VPN sites
4. Connect VPN sites to virtual hub


##

![alt text](image-576.png)

DNS in Peered VNets

Independent DNS Configuration: Each VNet in Azure can be configured with its own DNS servers. When you peer VNets, these configurations remain independent. A VNet does not inherit or override the DNS server settings of the VNet it is peered with.

Resolution Across Peered VNets: Resources in peered VNets can resolve DNS names as per their respective VNet’s DNS settings. If a resource in VNet A needs to resolve a name managed by a DNS server in VNet B, it can do so if the DNS server in VNet B is accessible and if the necessary DNS forwarding or conditional forwarding is set up.

Custom DNS Scenarios: In scenarios where you have custom DNS servers, you might need to configure DNS forwarding or conditional forwarding to ensure proper name resolution across peered VNets.

Azure-Provided DNS: If you are using Azure-provided DNS, the resolution of names for resources in Azure (like VMs) works across peered VNets without additional configuration


## Ping VM with A Records

![alt text](image-577.png)

Correct Answer C: `comp2.contoso.com only`

A record (resolvable) : Is used to map a DNS/domain name to an IP  
> https://www.cloudflare.com/learning/dns/dns-records/dns-a-record/  

TXT records in a lot of cases get used to prove ownership of a domain, it has other purposes too.  
> https://support.google.com/a/answer/2716800?hl=en#:~:text=TXT%20records%20are%20a%20type,and%20to%20ensure%20email%20security.  

PTR: A Reverse DNS lookup is used by remote hosts to determine who 'owns' an IP address.  
> https://www.mailenable.com/kb/content/article.asp?ID=ME020206   

CNAME records get used to redirect a DNS name or subdomain name to another DNS name or domain name or subdomain name.  
> https://support.dnsimple.com/articles/cname-record/   

## SKU of LB and public IP addresses must be the same 
![alt text](image-578.png)  

## Restrict network traffic between the pods with Calico Network Policy 

![alt text](image-579.png)

## Route All Inbound Traffic from VPN Gateway to VNET through a VM

![alt text](image-580.png)

Box 1: `10.0.0.0/16`
Address prefix
destination : VNet 1 (Address space of VNet1)

Box 2: **Virtual appliance**
Next hop type   
VM1 -> Virtual Appliance.  
- You can specify IP address of VM 1 when configuring next hop as Virtual appliance.  

Box 3: **Gateway Subnet**
Assigned to
This route is to be followed by Gateway Subnet for the incoming traffic. 

You can associate routing table to the Subnet from RouteTable -> subnet -> Associate.

## Load balancing rule that will load balance HTTPS traffic between VM1 and VM2  

You have an Azure subscription that contains two virtual machines named VM1 and VM2.

You create an Azure load balancer.

You plan to create a load balancing rule that will load balance HTTPS traffic between VM1 and VM2.

Which two additional load balancer resources should you create before you can create the load balancing rule?

A. a frontend IP address  
B. an inbound NAT rule   
C. a virtual network   
D. a backend pool  
E. a health probe  

D and E.  

You can't create a LB without FrontEnd IP, so if we have a LB we also have a FrontEnd IP already.  

You can however create a LB **without a backend pool** and **without any rules**.  
- **If you want to add a rule to your LB later you have to create a backend pool and health probe first.**  

Those are mandatory properties for a rule.    

## VM connects DB with standard SKU of a static public address assignment

You have an on-premises network that contains a database server named `dbserver1`.  

You have an Azure subscription.  

You plan to deploy 3 Azure virtual machines. 

Each virtual machine will be deployed to a separate availability zone.

You need to configure an Azure VPN gateway for a site-to-site VPN.   

The solution must ensure that the virtual machines can connect to `dbserver1`.  

Which type of public IP address SKU and assignment should you use for the gateway?
 
A. a basic SKU and a static IP address assignment  
**B. a standard SKU and a static IP address assignment** 
C. a basic SKU and a dynamic IP address assignment  

## :star: VNet Link to Private DNS

![alt text](image-581.png)


YES
- For VM1 , `server1.contoso.com` resolves to `131.107.3.3`

VM1 is connected to VNET1 which has Default(Azure-Provided) DNS Server and linked to Azure Private DNS Server `contoso.com` (131.107.3.3 and 131.107.3.4 DNS Servers). 

That means VM1 has these 2 DNS servers for resolving.
DNS Servers for VNET1
- server1.contoso.com = 131.107.3.3
- server2.contoso.com = 131.107.3.4

NO
- For VM2, `server1.contoso.com` resolves to `131.107.3.3`

VM2 belongs to VNET2 has Custom DNS: `192.168.0.5` IP of VM4 ( not takes from default Azure: the `server1.contoso.com = 131.107.3.3` and `server2.contoso.com = 131.107.3.4`) 

VM2 will resolve from VM4 
(DNS Server1.contoso.com=131.107.2.3 and Server2.contoso.com=131.107.2.4)

YES
- For VM3,server2.contoso.com resolves to 131.107.2.4

VM3 belongs to VNET3 has Custom DNS: `192.168.0.5` IP of VM4 ( not takes from default Azure: the `server1.contoso.com = 131.107.3.4` and` server2.contoso.com = 131.107.3.4`)  

VM3 will resolve from VM4 (DNS Server1.contoso.com=131.107.2.3 and Server2.contoso.com=131.107.2.4)

## :star: Azure DHCP service ignores any DNS suffix when it registers the private DNS zone.

![alt text](image-582.png)  
- `fabrikam.com`, you add a virtual network link to `VNet1` and enable auto registration.  
- For `contoso.com`, you assign `vm1` and `vm2` the Owner role.  

![alt text](image-583.png)  

N Y Y

Only private AZ DNS Zones can use auto registration. 
> The set DNS search suffix in the client changes nothing about that https://docs.microsoft.com/en-us/azure/dns/private-dns-autoregistration


**A virtual machine with a DNS suffix configured in Windows will register its DNS record to the private DNS zone.** 
However, the Azure DHCP service ignores any DNS suffix when it registers the private DNS zone. 
- For example, if your VM is configured for `contoso.com` as the primary DNS suffix, but the VNet is linked to the `fabrikam.com` private DNS zone, the VM's registration appears in the `fabrikam.com` private DNS zone.


## The firewall, VNet, and the public IP address all must be in the same resource group

![alt text](image-584.png)

## minimum number of connection monitors you deploy


## Create a route-table 

Route all traffic to the firewall
When you create a virtual network, Azure automatically creates a default route table for each of its subnets and adds system default routes to the table. In this step, you create a user-defined route table that routes all traffic to the firewall, and then associate it with the App Service subnet in the integrated virtual network.
Section3 in document.
https://learn.microsoft.com/en-us/azure/app-service/network-secure-outbound-traffic-azure-firewall

## Routing preference Microsoft point-of-presence (POP)

![alt text](image-585.png)

Routing preference in Azure Traffic Manager allows you to specify how to route traffic to your Azure service endpoints based on various criteria, such as the geographic location of the client or the endpoint, the performance of the endpoint, or the priority of the endpoint.

By configuring routing preference, you can direct incoming user traffic to the Microsoft point-of-presence (POP) closest to the user's location, ensuring the best possible user experience. This can be achieved by selecting the "Performance" routing method in Azure Traffic Manager, which uses DNS-based traffic routing to direct users to the endpoint that offers the best performance from the user's location.


## Delete Peering and re-create to change the status

![alt text](image-586.png)

![alt text](image-560.png)

Box 1: vNET6 only
Peering status to both VNet1 and Vnet2 are disconnected. So, only communication inside vNET6.

Box 2: delete peering1
Peering to vNET1 is enabled but disconnected. We need to delete the peering from both virtual networks, and then re-create them.

## Basic LB for VMs

You have an Azure subscription that contains the resources in the following table.
![alt text](image-587.png)

You install the Web Server server role (IIS) on VM1 and VM2, and then add VM1 and VM2 to LB1.
![alt text](image-588.png)

![alt text](image-589.png)

![alt text](image-590.png)

Box 1: Yes
A Basic Load Balancer supports virtual machines in a single availability set or virtual machine scale set.

Box 2: Yes
When using load-balancing rules with Azure Load Balancer, you need to specify health probes to allow Load Balancer to detect the backend endpoint status. The configuration of the health probe and probe responses determine which backend pool instances will receive new flows. 

You can use health probes to detect the failure of an application on a backend endpoint. You can also generate a custom response to a health probe and use the health probe for flow control to manage load or planned downtime. When a health probe fails, Load Balancer will stop sending new flows to the respective unhealthy instance. Outbound connectivity is not impacted, only inbound connectivity is impacted.

Box 3: No
There will be no loadbalancing between the VMs.

##

You have an Azure virtual machine named VM1 that connects to a virtual network named VNet1. VM1 has the following configurations:
- Subnet: 10.0.0.0/24
- Availability set: AVSet
- Network security group (NSG): None
- Private IP address: 10.0.0.4 (dynamic)
- Public IP address: 40.90.219.6 (dynamic)
You deploy a standard, Internet-facing load balancer named slb1.
You need to configure slb1 to allow connectivity to VM1.

![alt text](image-591.png)

Box 1: Remove the public IP address from VM1
Note: A public load balancer can provide outbound connections for virtual machines (VMs) inside your virtual network. These connections are accomplished by translating their private IP addresses to public IP addresses. Public Load Balancers are used to load balance internet traffic to your VMs. Load balancer and the public IP address SKU must match when you use them with public IP addresses. Only Basic SKU IPs work with the Basic SKU load balancer and only Standard SKU IPs work with Standard SKU load balancers.

Box 2: Create and configure an NSG
NSGs are used to explicitly permit allowed traffic. If you do not have an NSG on a subnet or NIC of your virtual machine resource, traffic is not allowed to reach this resource.

## 2-2-2


![alt text](image-594.png)

## Delete GW and Create Route-base VNet GW

![alt text](image-595.png)


## Actions of adding VM to backend pool with LB

![alt text](image-596.png)

## Action of S2S

![alt text](image-597.png)

1. Create Azure Virtual WAN
2. Create Virtual Hub
3. Create VPN sites
4. Connect VPN sites to virtual hub

## configure an Azure web app named contoso.azurewebsites.net to host www.contoso.com.

![alt text](image-598.png)

## When adding service endpoints on the VNET1 side you only get to choose the service

![alt text](image-599.png)  

First service endpoint: One service endpoint for Microsoft.Storage added to VNET1.

The question asks how many to add to VNET1. 

When adding service endpoints on the VNET1 side you only get to choose the service ( Microsoft.Storage ) not the actual storage accounts. 

Once you add this service endpoint it can be then linked to on the storage side for both accounts.

Second Service Endpoint: Microsoft.AzureActiveDirectory.

## 

![alt text](image-600.png)

No: 
- Server2 uses Server1 for DNS. Server1 has no host2.contoso.com record for 131.107.50.50. It would work if VNET1 hat a virtual network link to the private zone contoso.com.

Yes: 
- Server2 uses Server1 for DNS. Server1 has a host1.contoso.com record for 131.107.10.15

No: 
- Server3 uses 10.10.0.4 as DNS (inherited from VNET2). 10.10.0.4 (Server1) has no record for host2.contoso.com. The virtual network link for the private zone contoso.com on VNET2 won't be used since the DNS from VNET1 is set on VNET2. VNET1 DNS is not aware of the private zone contoso.com. It would work if VNET1 had a virtual network link to the private zone contoso.com.

## public/private LB Network Contributor role

LB1 and LB2 are resources that we want the Network Contributor role to manage,


## Access Review for GUEST

![alt text](image-602.png)

User3 can perform an access review of User1 = No
User1 is a Member and not a Guest Account, Access Review specified Guests only.

User3 can perform an access review of UserA = No
User1 is a Member and not a Guest Account, Access Review specified Guests only.

User3 can perform an access review of UserB = No
Created Group 1 and Group 2, added Group 2 as a member in Group 1,
Added guest Accounts to Group 1 and Group 2,
In the Access Review results only the Guest Accounts in Group 1 appeared for review and "Not" the Guest accounts in Group 2.

## subscription should be moved by can't be added to 2 groups 

![alt text](image-601.png)  

Answer is Wrong : It should Be NO NO NO
- subscription should be moved by can't be added to 2 groups.

## Device Management

![alt text](image-603.png)

User1 can add Device2 to Group1: No
User2 can add Device1 to Group1: Yes
User2 can add Device2 to Group2: No

Groups can contain both registered and joined devices as members.
- As a global administrator or cloud device administrator, you can manage the registered or joined devices. 

Intune Service administrators can update and delete devices. 

User administrator can manage users but not devices.

User1 is a cloud device administrator. 

Users in this role can enable, disable, and delete devices in Azure AD and read Windows 10 BitLocker keys (if present) in the Azure portal. 
- The role does not grant permissions to manage 
any other properties on the device.

User2 is the owner of Group1. 
- He can add Device1 to Group1.

Group2 is configured for dynamic membership. 
- The properties on which the membership of a device in a group of the type dynamic device are defined cannot be changed by either an end user or an user administrator. 

User2 cannot add any device to Group2.

> Reference: https://docs.microsoft.com/en-us/azure/active-directory/devices/device-management-azure-portal

## 

You have an Azure subscription named Subscription1 that contains a virtual network named VNet1. VNet1 is in a resource group named RG1.
Subscription1 has a user named User1. User1 has the following roles:
- Reader
- Security Admin
- Security Reader
You need to ensure that User1 can assign the Reader role for VNet1 to other users.
What should you do?
A. Remove User1 from the Security Reader and Reader roles for Subscription1.  
`B. Assign User1 the User Access Administrator role for VNet1. Most Voted`
C. Assign User1 the Network Contributor role for VNet1.  
D. Assign User1 the Network Contributor role for RG1.  

There are several versions of this question in the exam. The question has two possible correct answers:
- Assign User1 the User Access Administrator role for VNet1.
- Assign User1 the Owner role for VNet1.
