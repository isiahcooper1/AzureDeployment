<h1>Azure VM Deployment and RBAC with Bicep</h1>

<h2>Description</h2>
Deploys a Linux virtual machine into a segmented virtual network using a Bicep template, then secures it using Role-Based Access Control scoped to the resource group. Demonstrates core Azure compute, networking, and identity concepts including subnet segmentation, NSG rules, and least-privilege access principles.
<br>
<br>


<h2>Utilities Used</h2>

- <b>Azure Bicep — infrastructure deployment</b>
- <b>Azure CLI — deployment execution and verification</b>
- <b>Azure Portal — RBAC assignment and visual verification</b>
- <b>Azure Entra ID — identity and role management</b>

<h2>Environments Used </h2>

- <b>Windows 11 (local workstation)</b>
- <b>Azure Cloud Shell (deployment and CLI commands)</b>
- <b>Azure Portal (verification and RBAC)</b>
- <b>Ubuntu 22.04 LTS (deployed VM OS)</b>

<h2>Lab Architecture</h2>

<h2>Program walk-through:</h2>

<p align="center">
<h align="center">
<h3>Step 1 — Create the Log Analytics Workspace</h3>
<br />
1. Logged into Azure and created a dedicated resource group to contain all lab resources. <br/>
<img src="https://github.com/user-attachments/assets/a70c0f74-b170-46e2-b401-eac67c98a683" height="80%" width="80%" alt="Azure Resource Group"/>
<br />
<br />
<br />
<h3>Step 2 — Review and Deploy the Bicep Template</h3>
<br />
2. Created azuredeploy.bicep and deployed it from the Azure CLI. The template deployed the VNet, NSG, NIC, and VM in dependency order. <br/>
<img src="https://github.com/user-attachments/assets/d7fc65fa-322c-4440-804f-b3481ef546b7" height="80%" width="80%" alt="Bicep Deployment"/>
<br />
<br />
<br />
<h3>Step 3 — Verify the Deployment via CLI</h3>
<br />
3. Ran the following commands to confirm the VM is running and the NSG rules and subnets matched the intended architecture. <br/>
<img src="https://github.com/user-attachments/assets/a27cb234-d04c-4491-a147-9eb0c8888c45" height="80%" width="80%" alt="VM-NSG Confirmation"/>
<br />
<br />
<img src="https://github.com/user-attachments/assets/c3cc47ca-e355-4a3c-a946-db95b2a34543" height="80%" width="80%" alt="VNET Confirmation"/>
<br />
<br />
<br />
<h3>Step 4 — Assign RBAC via the Portal</h3>
<br />
4. Navigated to rg-lab01 > Access Control (IAM) > Add Role Assignment and assigned the Virtual Machine Contributor role to a group, scoped to the resource group. Verified the assignment under Entra ID > Groups > grp-vm-contributors > Azure Role Assignments.<br/>
<img src="https://github.com/user-attachments/assets/5523f417-455f-456a-aa0f-1dbc0f332a70" height="80%" width="80%" alt="Shared Drive"/>
<br />
<br />
<br />
<h3>Step 5 — Cleanup</h3>
<br />
5. Deleted the resource group to remove all provisioned resources and avoid ongoing charges.  <br/>
<img src="https://github.com/user-attachments/assets/01b51beb-a4e2-402f-ac9b-270d29243c63" height="80%" width="80%" alt="Password Policy GPO Linked to Domain"/>
<br />
<br />
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
