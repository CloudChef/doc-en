**VM Templates**

The virtual machine template is the abstraction and standardization of the operating system. A template is a virtual machine encapsulated in a file, and a new VM can be quickly deployed through the template. Each template contains installation metadata, which is the setup information required to create a new instance with a specific operating system, optimal storage, CPU, memory, and virtual network configuration.

The platform supports the creation of virtual machine templates. One operating system can correspond to multiple virtual machine templates. 
+ A virtual machine template is associated with a template or image in the cloud platform, such as templates in vSphere vCenter, images on the OpenStack platform and operating system (OS) images for each area of the public cloud platform.

+ The installation mode and account information of the two SmartCMP agents can be configured in the VM template. The two agents are monitoring agents and automation agents.

Some of the automation features of SmartCMP rely on automation agents such as:

-   Blueprint with application deployment or adding disks

-   Service configuration initializes and mounts disks, creating new users 

-   Part of virtual machine operations (including resetting passwords, executing scripts, stopping applications, adding, expanding Linux logical volumes or Windows disks, etc.).

Once a virtual machine template is created, it can be specified directly in the service configuration. SmartCMP automatically recognizes virtual machine templates based on the cloud platform on which the blueprint objects are located.

>「Note」Please use the tenant administrator or infrastructure administrator account to log in to SmartCMP platform. Tenant administrators can assign an infrastructure administrator role to a user. By default, three virtual machine templates are created: Windows 2012 R2, Redhat 7, and CentOS 7. You need to add the corresponding cloud platform information to use.



# Add VM Templates

Here we define two virtual machine templates: Windows 2012 R2 and CentOS 7.

## Add a Linux VM Template

1.  Select Infrastructure - VM Template to enter the VM template list interface. Click "Add", enter the operating system name, description, select the system type Linux, click "Submit"

2.  Click the VM Template tab to enter the VM template list interface

### Add a vSphere VM Template{#Add a vSphere VM Template}

1.  On the VM template list page, click Add. Enter the VM template name, select a vSphere cloud platform, and configure the following:

Clone mode: "Full clone" or "Linked clone"

 >「Note」 Full clone is a completely independent copy of the original virtual machine, it does not share any resources with the original virtual machine, can be used independently from the original virtual machine while linked clones need to share the same virtual disk file with the original virtual machine, cannot be separated from the original virtual machine running independently. But using shared disk files greatly reduces the time it takes to create a cloned virtual machine, while also saving valuable physical disk space.

- Full clone:  Template: Select a Linux CentOS template

- Linked clone: Virtual Machine: Select a template for Linux CentOS 7. Snapshot mode: “Specify a snapshot” by default, you can select two snapshot modes: “Select when applying” and “Always use the latest”. Select "Select when applying" to select a virtual machine snapshot at the time of service request. Snapshot: If the snapshot mode selects “Specify a Snapshot”, a snapshot will be selected.

-   SSH is enabled in the template: Check this option to enable SSH in the template. You can choose to install the monitoring agent and the automation agent through SSH. The default SSH port is 22. If the SSH port is modified in the template, Enter the modified SSH port number in the template.

-   Username and password: If you choose to enable SSH, fill in the user with SSH permission and its password 

-   Monitoring method: No monitoring: The monitoring function of the platform is not available if the monitoring agent is not installed. SSH monitoring agent: If you choose to install SSH, you will access the virtual machine through SSH and install the monitoring agent. Set the monitoring port. The default is 9100. Pre-installation monitoring agent: Pre-installation means that the monitoring agent is already installed in the template. Cloud platform monitoring: directly read the monitoring data of the virtual machine from the vCenter, no need to install the monitoring agent.

-   Install the automation agent: Do not install: If you do not install an automated agent, some of the platform's automation features will not be available, such as blueprints with application deployment or disks adding, some virtual machine operations such as resetting passwords, executing scripts, etc. SSH installation: Select SSH installation, access virtual machine via SSH and install automation agent. Pre-installation: Pre-installation means that an automation agent is already installed in the template.


<!-- -->

-   Admin user: Enter the administrator username configured in the template

-   Administrator password: Enter the administrator password configured in the template

2.  Click Submit, it shows that the virtual machine template has been created. Click "Save" to indicate that the VM template has been updated

### Add OpenStack VM Template{#Add OpenStack VM Template}

1.  Click Add, enter the virtual machine template name, select the OpenStack cloud platform and do the following configuration:

-   Startup source type: boot from image, launch from snapshot, boot from cloud drive, boot from cloud drive snapshot 

<!-- -->

-   Boot from image: Select the image name and snapshot mode. The snapshot mode defaults to “Do not use snapshots”, you may select “Select when applying” and “Always use the latest”. If you select " Select when applying", you will specify a virtual machine snapshot at the time of service request. 

-   Launch from Snapshot: Select Snapshot Name

-   Boot from the cloud drive: Select the image name and snapshot mode. The snapshot mode defaults to “Do not use snapshots”, you may select “Select when applying” and “Always use the latest”. If you select "Select when applying", the virtual machine snapshot will be specified when the service is applied; if "Delete after termination" is checked, the hard disk will be deleted after the host is terminated. Selecting "Boot from Cloud Drive" mode requires volume type and configuration volume size to be selected during service configuration 

-   Boot from the cloud disk snapshot: Select the cloud disk snapshot name. If you select “Delete after termination”, the hard disk will be deleted after the host is terminated. Selecting "Start from Cloud Drive Snapshot" mode requires volume type and configuration volume size to be selected during service configuration 

<!-- -->

-   VM image: Select a CentOS template

-   How to monitor and automate agents: Same as the Linux template for vSphere, you can configure the SSH port. In addition, the SSH user supports the key mode (you can create a new key or import a key in the Infrastructure - Key Pairs). 


-   Administrator username and password: Enter the operating system administrator username and password

2.  Click Submit to prompt that the virtual machine template has been created. Click "Save" to indicate that the VM template has been updated

3.  At this time, the Linux operating system of CentOS 7 is associated with two virtual machine templates. When configuring service, the platform automatically selects the VM template corresponding to the service without repeating the settings.

### Add a Hyper-V VM Templates{#Add a Hyper-V VM Templates}

1.  On the VM template page, click Add. Enter the VM template name, select the Hyper-V cloud platform name, and configure the VM template as follows:

-   Basic information: Select “OS name”, description, and system type (select Linux and Windows as required, select Linux here)

-   Template: Select a template for CentOS

-   Edit the VM template: Enter the template name, cloud platform entry, and SSH enabled in the template. Check this option to enable SSH (in the SSH port configured in the template). You can choose to install the monitoring agent and automation agent through SSH 

-   Monitoring method:

<!-- -->

-   No monitoring: the monitoring function of the platform is not available without the monitoring agent installed.

-   SSH installation monitoring agent: If you choose to install SSH, you will access the virtual machine through SSH and install the monitoring agent. Set the monitoring port. The default is 9100

<!-- -->

-   Install the automation agent:

<!-- -->

-   Do not install: If you do not install an automated agent, some of the platform's automation features will not be available, such as blueprints with application deployment or adding disks, some virtual machine operations such as resetting passwords, executing scripts, etc.

-   SSH installation: select SSH installation, SSH access to the virtual machine and install the automation agent

<!-- -->

-   Username: Enter the username you want to set, for example: root

-   Password: Enter the administrator password you need to set, for example: Passw0rd

2.  Click Submit to prompt that the virtual machine template has been created. Click "Save" to indicate that the VM template has been updated.


### Add an Azure VM Template{#Add an Azure VM Template}

1.  On the VM template page, click Add. Enter the VM template name, select the Azure cloud platform name, and configure the VM template as follows:

-   Basic information: Select “OS name”, description, and system type (select Linux and Windows as required, select Linux here)

-   Edit VM template: Enter the template name, cloud platform entry, select the region name (for example: North China), image name (check the Allow modification, you can modify the image in the service configuration)

-   Monitoring method:

<!-- -->

-   No monitoring: the monitoring function of the platform is not available without the monitoring agent installed.

-   SSH installation monitoring agent: If you choose to install SSH, you will access the virtual machine through SSH and install the monitoring agent. Set the monitoring port. The default is 9100

-   Cloud platform monitoring: directly read the monitoring data of the virtual machine from the Azure cloud platform, no need to install the monitoring agent

<!-- -->

-   Install the automation agent:

<!-- -->

-   Do not install: If you do not install an automated agent, some of the platform's automation features will not be available, such as blueprints with application deployment or adding disks, some virtual machine operations such as resetting passwords, executing scripts, etc.

-   SSH installation: select SSH installation, SSH access to the virtual machine and install the automation agent

<!-- -->

-   Username: Enter the username you want to set, for example: root

-   Password: Enter the administrator password you need to set, for example: Passw0rd

2.  Click Submit to prompt that the virtual machine template has been created. Click "Save" to indicate that the VM template has been updated.

## Add a Windows VM Template

1.  Select Infrastructure - VM Template to enter the VM template list interface. Click "Add", enter the virtual machine template name, description, select the system type: Windows, click "Submit"

2.  Click the VM Template tab to enter the VM template list interface.

### Add a vSphere VM Templates

1.  On the VM template list page, click Add. Enter the VM template name, select a vSphere cloud platform, and configure the following:

-   Clone mode: "Full clone" or "Linked clone"

 >「Note」Full clone is a completely independent copy of the original virtual machine, it does not share any resources with the original virtual machine, can be used independently from the original virtual machine while linked clones need to share the same virtual disk file with the original virtual machine, cannot be separated from the original virtual machine running independently. But using shared disk files greatly reduces the time it takes to create a cloned virtual machine, while also saving valuable physical disk space.

-   Full clone:

<!-- -->

-   Template: Select a Windows 2012 template

<!-- -->

-   Linked clone:

<!-- -->

-   Virtual Machine: Select a template for Windows 2012 

-   Snapshot mode: “Specify a snapshot” by default, you can select two snapshot modes: “Select when applying” and “Always use the latest”. Select "Select when applying" to select a virtual machine snapshot at the time of service request. 

-   Snapshot: If the snapshot mode selects “Specify a Snapshot”, a snapshot will be selected.

<!-- -->

-   Use Specification: Select “Built-in” (Select None, Built-in or Custom Specification as required, the specification helps prevent conflicts when deploying virtual machines with the same settings)

-   WinRM is enabled in the template: Check this option to enable WinRM in the template. You can choose to install the monitoring agent and the automation agent through WinRM. The default WinRM port is 22. If the WINRM port is modified in the template, Enter the modified WinRM port number in the template.

-   Monitoring method:

<!-- -->

-   No monitoring: The monitoring function of the platform is not available if the monitoring agent is not installed

-   WinRM monitoring agent: If you choose to install WinRM, you will access the virtual machine through WinRM and install the monitoring agent. Set the monitoring port. The default is 9182.

-   Pre-installation monitoring agent: Pre-installation means that the monitoring agent is already installed in the template.

-   Cloud platform monitoring: directly read the monitoring data of the virtual machine from the vCenter, no need to install the monitoring agent

<!-- -->

-   Install the automation agent:

<!-- -->

-   Do not install: If you do not install an automated agent, some of the platform's automation features will not be available, such as blueprints with application deployment or disks adding, some virtual machine operations such as resetting passwords, executing scripts, etc.

-   WinRM installation: Select WinRM installation, access virtual machine via WinRM and install automation agent

-   Pre-installation: Pre-installation means that an automation agent is already installed in the template.

<!-- -->

-   Admin user: Enter the administrator username configured in the template

-   Administrator password: Enter the administrator password configured in the template

2.  Click Submit, it shows that the virtual machine template has been created. Click "Save" to indicate that the VM template has been updated

### Add OpenStack VM Template

1.  Click Add, enter the virtual machine template name, select the OpenStack cloud platform and do the following configuration:

-   Startup source type: boot from image, launch from snapshot, boot from cloud drive, boot from cloud drive snapshot 

<!-- -->

-   Boot from image: Select the image name and snapshot mode. The snapshot mode defaults to “Do not use snapshots”, you may select “Select when applying” and “Always use the latest”. If you select " Select when applying", you will specify a virtual machine snapshot at the time of service request. 

-   Launch from Snapshot: Select Snapshot Name

-   Boot from the cloud drive: Select the image name and snapshot mode. The snapshot mode defaults to “Do not use snapshots”, you may select “Select when applying” and “Always use the latest”. If you select "Select when applying", the virtual machine snapshot will be specified when the service is applied; if "Delete after termination" is checked, the hard disk will be deleted after the host is terminated. Selecting "Boot from Cloud Drive" mode requires volume type and configuration volume size to be selected during service configuration 

-   Boot from the cloud disk snapshot: Select the cloud disk snapshot name. If you select “Delete after termination”, the hard disk will be deleted after the host is terminated. Selecting "Start from Cloud Drive Snapshot" mode requires volume type and configuration volume size to be selected during service configuration 

<!-- -->

-   Install monitoring and automation agents in the same way as vSphere's Windows templates

-   Windows username: Enter the Windows administrator username 

-   Authentication type: key pair or password. Select password

-   Windows password: set the password corresponding to the username

2.  Click Submit to prompt that the virtual machine template has been created. Click "Save" to indicate that the VM template has been updated

At this time, the Linux operating system of CentOS 7 is associated with two virtual machine templates. When configuring service, the platform automatically selects the VM template corresponding to the service without repeating the settings.

### Add a Hyper-V VM Templates

1.  On the VM template page, click Add. Enter the VM template name, select the Hyper-V cloud platform name, and configure the VM template as follows:

-   Basic information: Select “OS name”, description, and system type (select Linux and Windows as required, select Windows here)

-   Template: Select a template for Windows 2012

-   Edit the VM template: Enter the template name, cloud platform entry, and WinRM enabled in the template. Check this option to enable WinRM (in the WinRM port configured in the template). You can choose to install the monitoring agent and automation agent through WinRM 

-   Monitoring method:

<!-- -->

-   No monitoring: the monitoring function of the platform is not available without the monitoring agent installed.

-   WinRM installation monitoring agent: If you choose to install WinRM, you will access the virtual machine through WinRM and install the monitoring agent. Set the monitoring port. The default is 9182

<!-- -->

-   Install the automation agent:

<!-- -->

-   Do not install: If you do not install an automated agent, some of the platform's automation features will not be available, such as blueprints with application deployment or adding disks, some virtual machine operations such as resetting passwords, executing scripts, etc.

-   WinRM installation: select WINRM installation, WINRM access to the virtual machine and install the automation agent

<!-- -->

-   Username: Enter the username you want to set, for example: root

-   Password: Enter the administrator password you need to set, for example: Passw0rd

2.  Click Submit to prompt that the virtual machine template has been created. Click "Save" to indicate that the VM template has been updated.

 ### Add an Azure VM Template

<!-- -->

1.  On the VM template page, click Add. Enter the VM template name, select the Azure cloud platform name, and configure the VM template as follows:

-   Basic information: Select “OS name”, description, and system type (select Linux and Windows as required, select Windows here)

-   Edit VM template: Enter the template name, cloud platform entry, select the region name (for example: North China), image name (check the Allow modification, you can modify the image in the service configuration)

-   Monitoring method:

<!-- -->

-   No monitoring: the monitoring function of the platform is not available without the monitoring agent installed.

-   WinRM installation monitoring agent: If you choose to install WinRM, you will access the virtual machine through WinRM and install the monitoring agent. Set the monitoring port. The default is 9182

-   Cloud platform monitoring: directly read the monitoring data of the virtual machine from the Azure cloud platform, no need to install the monitoring agent

<!-- -->

-   Install the automation agent:

<!-- -->

-   Do not install: If you do not install an automated agent, some of the platform's automation features will not be available, such as blueprints with application deployment or adding disks, some virtual machine operations such as resetting passwords, executing scripts, etc.

-   WinRM installation: select WinRM installation, WinRM access to the virtual machine and install the automation agent

<!-- -->

-   Username: Enter the username you want to set, for example: root

-   Password: Enter the administrator password you need to set, for example: Passw0rd

2.  Click Submit to prompt that the virtual machine template has been created. Click "Save" to indicate that the VM template has been updated.

# View the Current VM Template

You can view the virtual machine template by following the steps below:

>「Note」Please use the tenant administrator or infrastructure administrator role to log in to the SmartCMP platform.

1.  Select “Infrastructure” on the left navigation and select the secondary menu “VM Templates” to display the current list of virtual machine templates. The description information and the operating system type corresponding to the virtual machine template can be viewed in the list.

2.  Click the name of the VM template to go to the basic information page to view the operating system name, description, and system type.

3.  Click the VM template to enter the VM template management interface. Add, edit, and delete virtual machine templates