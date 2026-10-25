# AZ-104-Labs
This is used to track my progress of AZ104 labs. I will also write the commands and other notes which I feel will be important.

**Day - 1: **

**Using Microsoft Entra to create groups and members**
-> New-AzADGroup -DisplayName "displayName" -MailNickname "nickname" (this is used to create a new group in Entra via Azure CLI)

**Managing Subscriptions & Governance**
-> We can manage the roles and other policies using Microsoft Entra. We have to set the roles, permissions, members from Entra. It is also possible for the members to set locks on the resources and prevent from accidental deletion.
-> We can also set the tags, and based on those tags we can also use Azure policies.

**Azure Resource Templates:**
-> We can also deploy using templates. For example, I created a sample disk - and downloaded its template and modified it again to redeploy the resources again.
-> We deploy it using the below process:
   - in Azure CLI, we first upload the parameters and template (json) files and the use the commands:  **New-AzResourceGroupDeployment -ResourceGroupName az104-rg3 -TemplateFile template.json -TemplateParameterFile parameters.json**
