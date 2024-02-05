{%hackmd @Edixon/dracula %}   
:arrow_left: [AZ-104 Category](/4jvQjF_OTpm1_mkZhcRMoA)  

# AD DS Azure AD, Active Directory 

[TOC]

{%youtube mH48U0PlLKI %}

## Overview

> **IDENTITY** as a Service (IDaaS) for all the apps across cloud and on-premises.

Azure AD is MS **cloud-based identity** and **access management (IAM) solution** that provides authentication, authorization, and security for structured data store of objects in the cloud and on-premises.   

Structured Data store of objects (AD object)
1. `Users`
E.g. Accounts storing passwords, IDs, addresses, and departments.
2. `Computers`  
3. `Groups`  
E.g. group to group, computers to Group or user to group. 
4. `Other Objects`
E.g. printers, (file) shares, GPO/Group Policy
5. `Easily Searchable` (Global Catalog)
6. `Integrated Security`
E.g. security check for the tickets
7. `Logical And Hierarchical`
E.g. Top Domain and its child domains, or departments in Organization.
8. `Schema defines Objects & Attributes`
9. `Efficiently replicated`
E.g. Domain Control Copies  


Usage for AD : 
- Azure AD is the backbone of the Office 365 system, and it can sync with on-premise AD and provide authentication to other cloud-based systems via OAuth.
- Azure AD uses **Representational State Transfer (REST)** APIs to support communication to other web-based services, and cloud-based authentication protocols like `OAuth2`, `SAML`, and `WS-Security` for user authentication.
- AD organizes users and groups into a flat structure called a **tenant, which is a dedicated and isolated instance of Azure AD for each organization**.
- AD enables admins to manage users, groups, apps, and resources from a single portal, and to apply policies and rules to control access and security.
- AD offers various features and services, such as Azure AD Domain Services, Azure AD Connect, Azure AD B2C, Azure AD B2B, Azure AD Identity Protection, Azure AD Privileged Identity Management, and more.

## Active Directory Terminology  

![image](/az-104/images/actermnology.png)

- Domain
An Active Directory Domain is a logical grouping of AD objects on a network  
Domain is an area o a network organized by a ==single authentication database==
- **Domain Computer**: 
A computer that is joined to an AD domain and has an account in the domain.  
A domain computer can authenticate to the domain and access resources that are authorized by the domain policies¹.  
- **AD object**: 
An entity that represents a network resource, such as a user, computer, group, printer, or folder, in Active Directory.  
An AD object has a set of attributes that describe its properties and a unique identifier².  
- **Group Policy Object (GPO)**: 
A collection of settings that define what a system will look like and how it will behave for a defined group of users.  
A GPO can be linked to one or more Active Directory containers, such as a site, domain, or organizational unit, to apply the settings to the AD objects users and computers in those containers.  
- **Organizational Unit (OU)**:  
A type of AD object that can contain other AD objects, such as users, computers, groups, or other OUs. An OU can be used to organize AD objects into logical units based on criteria such as function, location, or department. An OU can also be linked to a GPO to apply specific settings to the AD objects in the OU⁴.
- **Directory Service**:  
A service that stores and manages information about network resources, such as users, computers, groups, printers, or folders, and makes this information available to network users and administrators. Active Directory Domain Services (AD DS) is an example of a directory service that provides identity and access management for Windows-based networks.


## Tenant

> An Organization in Azure AD and AD Service Instance  

![image](https://hackmd.io/_uploads/ry2dO0q8p.png)  
- It is automatically created while signing up for either `MS Azure`, `MS Intune` and `MS 365`
- Each AZ AD tenant is **distinct** and separate from other AZ AD tenant

## Azure Active Directory Domain Services, AD DS

**A managed service** that allows you to use managed domain services (provided by AZ DS), such as Windows Domain Join, GPO, LDAP, and Kerberos authentication, **without having to deploy, manage, or patch domain controllers.**

Some of the key points of Azure AD DS are:
- It is part of Microsoft Entra, the identity and access management platform from Microsoft.  
- It enables you to migrate your on-premises applications to the cloud and run them in a managed domain.  
- It provides high availability and resilience for your domain with multiple domain controllers.
- It simplifies the management and security of your identity infrastructure with the Microsoft Entra admin center.  
- It offers conditional access and security threat intelligence for your users.  
- It has different pricing options based on the size and performance of your domain.  


## Domain Controller

![image](https://hackmd.io/_uploads/Bkp4a0qUp.png)

In Azure, a Domain Controller can refer to two things:  
1. Azure Active Directory Domain Services (Azure AD DS)
This is a managed service provided by Azure which is highly available as it includes multiple domain controllers.
2. Deploying a Domain Controller on Azure 
You can deploy a traditional Domain Controller on an Azure Virtual Machine.  
This is similar to having a Domain Controller in an on-premises environment, but it's hosted in Azure.  
This can be useful for creating a high-availability domain controller or extending your on-premises Active Directory to Azure.  


## Azure AD Connect

Azure AD Connect is a tool that **connects your on-premises AD with Azure AD**, which is the cloud-based identity service for Microsoft 365 and other online services.  

![image](https://hackmd.io/_uploads/SyE13xjLa.png)

It also allows you to synchronize user accounts, groups, passwords, and other identity data between your on-premises AD and Azure AD, so that your users can access both environments with a single sign-on experience. 

Azure AD Connect also supports different authentication methods, such as password hash synchronization, pass-through authentication, and federation with AD FS. Azure AD Connect is designed to help you achieve your hybrid identity goals and simplify the management of your identity infrastructure 

## AD Users

User represent an identity for an person or employee in you domain.  

Two kinds Users
1. Users : A user belongs to your organization  
2. Guest Users : A Guest user belongs to another organization  

If you want to manage AD users in Azure, you have several options to do so. 

You can use the Microsoft Entra admin center, which is a web portal that allows you to `add`, `delete`, or `modify` users, groups, roles, and other identity data in Azure Active Directory (Azure AD). You can also use the Azure CLI, which is a command-line tool that lets you perform various tasks with Azure AD users, such as listing, creating, updating, or deleting them. Another option is to use PowerShell, which is a scripting language that enables you to automate and customize your identity management operations with Azure AD. For more information about these options, you can refer to the following resources:

•  Add or delete users - Microsoft Entrahttps://learn.microsoft.com/en-us/entra/fundamentals/add-users: This article explains how to add or delete users from your tenant using the Microsoft Entra admin center.

•  Microsoft Entra admin centerhttps://aad.portal.azure.com/: This is the web portal where you can access and manage your Azure AD users and other identity data.

•  az ad user | Microsoft Learnhttps://learn.microsoft.com/en-us/cli/azure/ad/user?view=azure-cli-latest: This is the reference page for the Azure CLI commands related to Azure AD users.

•  Get-AzureADUser (AzureAD) | Microsoft Learnhttps://learn.microsoft.com/en-us/powershell/module/azuread/get-azureaduser?view=azureadps-2.0: This is the reference page for the PowerShell cmdlet that gets a user or a list of users from Azure AD.

### AD Groups 

![image](https://hackmd.io/_uploads/r1YJSfjUp.png)

Azure AD groups are a way of organizing users, devices, and other objects in Microsoft Entra ID, which is the cloud-based identity service for Microsoft 365 and other online services. 

Azure AD groups can be used to manage access and permissions to resources, applications, and tasks. 
for example you can assign roles or applications directly to a group 

There are two types of Azure AD groups:  
- Security groups are used to control user and device access to shared resources, such as files, folders, apps, and roles. 
- Microsoft 365 groups are used to enable collaboration among group members, such as sharing a mailbox, calendar, files, SharePoint sites, and more. 

**You can create and manage Azure AD groups using different methods, such as the Microsoft Entra admin center, the Azure portal, PowerShell, or the Graph API.**

#### AD Assign Access Rights 

If you want to assign access rights in Azure AD, you need to use Azure role-based access control (Azure RBAC), which is the authorization system that allows you to manage access to Azure resources. 

To assign access rights, you need to follow these steps:

1. Identify the needed scope: 
Scope is the set of resources that the access applies to. You can specify a scope at four levels: management group, subscription, resource group, or resource. You can search for the scope you want to grant access to in the Azure portal.
2. Open the Add role assignment page: 
Access control (IAM) is the page that you use to assign roles to grant access to Azure resources.  
You can find it in the navigation menu of the scope you selected.  
Click the Role assignments tab to see the current list of role assignments. 
Click `Add > Add role assignment` to open the page.
3. Select the appropriate role: 
On the Role tab, select a role that you want to use. You can search for a role by name or by description.  
You can also filter roles by type and category. You can click View to get more details about a role.  
Click `Next`.
4. Select who needs access: 
On the Members tab, select User, group, or service principal to assign the selected role to one or more Microsoft Entra users, groups, or service principals (applications).  
Click Select members to find and select the users, groups, or service principals. 
Click Select to add them to the Members list. Click `Next`.
5. Review and assign: 
On the `Review + assign` tab, review the role assignment settings.  
Click `Review + assign` to assign the role.

![image](https://hackmd.io/_uploads/H1MBKri8T.png)  

![image](https://hackmd.io/_uploads/HypTtSs8T.png)


## Creating A Tenant

`Azure Active Directory | Create A Tenant`  

![image](https://hackmd.io/_uploads/rJTP5rjLa.png)

Creation  
Tenant Type
1. Azure Active Directory
2. Azure Active Directory (B2C)

Configuration
1. Organization Name
2. Initial Domain Name
3. Country / Region

### License

## Creating User

`Azure Active Directory | Manage | Users | New User`


`Azure Active Directory | Manage | Guest Ueser | New Guest User | invite user`

> Guest User : Invite user to the tenant


---

Azure Active Directory Domain Services (Azure AD DS). https://azure.microsoft.com/en-us/products/active-directory-ds.
What is Azure Active Directory? A Complete Overview - Varonis. https://www.varonis.com/blog/azure-active-directory.
What Is Azure AD And How Azure AD Works? - Azure Lessons. https://azurelessons.com/what-is-azure-active-directory/.
Understanding the Active Directory Logical Model. https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/plan/understanding-the-active-directory-logical-model.
Group Policy Hierarchy | Microsoft Learn. https://learn.microsoft.com/en-us/previous-versions/windows/desktop/Policy/group-policy-hierarchy.
Create an organizational unit (OU) in Microsoft Entra Domain Services .... https://learn.microsoft.com/en-us/entra/identity/domain-services/create-ou.
Organizational Unit (OU): Active Directory Best Practices | tenfold. https://www.tenfold-security.com/en/organizational-unit/.
