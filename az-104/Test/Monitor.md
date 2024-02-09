## Monitor and Maintain Azure Resources

### Alert Rule x action group

**Q :**
You created an alert rule and configured an action group with the notification type Email Azure Resource Manager Role, which sends an email to the Monitoring Reader role.

The Monitoring Reader role is assigned to the user, service principal and group.

**ANS :**

An action group is a collection of notification preferences set by the Azure subscription's owner. 

**Since an action group is a global service, it is not bound to a specific Azure region and can handle any client requests. **
- For example, if one region of the action group service is unavailable, traffic is routed and processed by other regions.
- A catastrophe recovery solution is provided by an action group as a global service.

When you use the Email Azure Resource Manager role type of notification, you can send email to members of a subscription's role. 
Emails are only sent to Azure AD user members who are members of the role.   
Azure AD groups and service principals are not emailed.   
Also, a notification email will only be sent to the primary email address.  

Hence, the correct answer is: TDU3.

All of the other options are incorrect because only TDU3 will able to receive the email notification since emails are only sent to Azure AD user members who are members of the role.

### backup policy in Recovery Services Vault Resource setup

To create a backup policy, you need to create a Recovery Services vault first. 

Take note that the services supported by Azure Backup are virtual machine, file share, SQL server, and SAP HANA. 

Based on the given policy, the retention period for monthly backup is 36 months. 

Since January 15 is not configured as a yearly backup point, this backup is considered a monthly backup.

- The created backup on January 15 will be retained for 36 months.
- The created backup on December 15 will be retained for 5 Years.

## Azure Network Watcher

3-24. QUESTION  

A web application is hosted on TD-VM1(within TDVNet1) and the data is retrieved and processed by TD-VM2 (within TDVNet2).  

Several users reported that the web application has a sluggish performance.  

You are instructed to track the average round-trip time (RTT) of the packets from TD-VM1 to TD-VM2.

![Alt text](image-94.png)

**In this scenario, you can use Connection Monitor to track the average round-trip time (RTT) of the packets from TD-VM1 to TD-VM2.** 

In Azure Network Watcher, Connection Monitor provides unified end-to-end connection monitoring. 

**The Connection Monitor feature also supports hybrid and Azure cloud deployments.**

Benefits of using the Connection Monitor:

– Unified, intuitive experience for Azure and hybrid monitoring needs

– Cross-region, cross-workspace connectivity monitoring

– Higher probing frequencies and better visibility into network performance

– Faster alerting for your hybrid deployments

– Support for connectivity checks that are based on HTTP, TCP, and ICMP

– Metrics and Log Analytics support for both Azure and non-Azure test setups

Hence, the correct answer is Connection Monitor.

IP flow verify is incorrect because this feature only looks at the rules for all Network Security Groups (NSGs) applied to the network interface. It is stated in the scenario that you must track the packets from TD-VM1 to TD-VM2. IP flow verify is not capable of providing the average round-trip time of the packets from the source to the destination.

Connection Troubleshoot is incorrect because it simply checks connectivity between source and destination. Take note that you need to track the average round-trip time of the packets from VM1 to VM2. Therefore, you need to use Connection Monitor to analyze the end-to-end connection and not the Connection Troubleshoot operation.

NSG flow logs is incorrect because it only allows you to log information about IP traffic flowing (ingress and egress) through an NSG. Take note that you can’t use NSG flow logs to track the average RTT of the packets from TD-VM1 to TD-VM2. You need to use Connection Monitor to provide unified end-to-end connection monitoring.