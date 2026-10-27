# AZ-104-Labs
This is used to track my progress of AZ104 labs. I will also write the commands and other notes which I feel will be important.

**Day - 1:**

**Using Microsoft Entra to create groups and members**
-> New-AzADGroup -DisplayName "displayName" -MailNickname "nickname" (this is used to create a new group in Entra via Azure CLI)

**Managing Subscriptions & Governance**
-> We can manage the roles and other policies using Microsoft Entra. We have to set the roles, permissions, members from Entra. It is also possible for the members to set locks on the resources and prevent from accidental deletion.
-> We can also set the tags, and based on those tags we can also use Azure policies.

**Azure Resource Templates:**
-> We can also deploy using templates. For example, I created a sample disk - and downloaded its template and modified it again to redeploy the resources again.
-> We deploy it using the below process:
   - in Azure CLI, we first upload the parameters and template (json) files and the use the commands:  **New-AzResourceGroupDeployment -ResourceGroupName az104-rg3 -TemplateFile template.json -TemplateParameterFile parameters.json**

**Day - 2:**

Using Virtual Networks to create ASG and NSG.
-> We used Virtual Network to create a NSG and ASG. Then used subnets to use SharedServiceSubnet to connect the asg subnet to nsg.
-> We also used several inbound and outbound security rules to restrict the access over the internet.
-> Created using template: Search for **Deploy a custom template** then use the sample template, make changes and then push that template.
-> Resolve using both public and private DNS zones.

**Day - 3:**

Using Network Watcher, Route Tables, and implement intersite connectivity
-> Created two VMS, VNETs.
-> Tested the connection between them using Network Watcher and then Connection Troubleshoot. It failed, since we have not connected both of the VNETs.
-> Configured Virtual network peering between virtual networks.
-> Used:  Enable-NetFirewallRule -DisplayGroup "Remote Desktop" to run the powershell script in one VM.
-> Used:  Test-NetConnection <first VM private IP address> -port 3389 to test the TCP connection.
-> Created custom route. Then wanted to control network traffic between the perimeter subnet (new subnet created within first VM) and the internal core services subnet (existing subnet of first VM). A virtual network appliance will be installed in the perimeter subnet and all traffic should be routed there.
-> Created route table, then went to Subnets within Route table and selected it to associate.
