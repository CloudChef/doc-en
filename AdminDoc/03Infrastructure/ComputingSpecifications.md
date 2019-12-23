
**Computing Specifications**

Computing specification defines the CPU and memory configuration specifications of the virtual machine (e.g., 2 core CPU, 4G memory) and can set the cloud platform specifications. The service is automatically selected according to the cloud platform when configuring the service.

Go to the menu "Infrastructure" - "Computing specifications" to manage the computing specifications. The configuration of the compute node can be configured at the service configuration node detailed settings.

# Add Computing specifications

The computing specifications of different types of cloud platforms are configured differently. The differences are as follows:

-   vSphere and Hyper-V only need to define the computing specifications. You do not need to configure the cloud platform specifications. The following takes vSphere as an example.

-   OpenStack needs to define computing specifications and cloud platform specifications

-   Azure, AWS, and Aliyun need to define computing specifications and cloud platform specifications (a cloud platform specification needs to be defined for each public cloud zone). Let's take Azure as an example.

「Note」Following chapters shows 3 types of adding computing specifications.

Go to the menu "Infrastructure" - "Computing specifications" to manage the computing specifications. The platform defaults to four computing specifications: micro (1 core 1GB), small (2 core 4GB), medium (4 core 8GB), and large (8 core 16GB). You can also customize the computing specification type as needed.

## Add vSphere Computing Specifications {#Add vSphere Computing Specifications}

1.  Go to the menu "Infrastructure" - "Calculate Specifications" and enter the new specification basic information page

Computing Specifications|Basic Information   
:------:|:------: 
  Name  |             vSphere Computing Specifications
  CPU       |             2
  CPU Unit   |            Core
  Memory    |             4
  Memory Unit    |           GB

2.  Click “Save” to add a new vSphere computing specification.

## Add OpenStack Computing Specifications {#Add OpenStack Computing Specifications}

1.  Go to the menu "Infrastructure" - "Calculate Specifications" and enter the new specification basic information page

Computing Specifications |Basic Information   
:------:|:------: 
  Name     |                   OpenStack Computing Specifications
  CPU         |                    2
  CPU Unit    |                    Core
  Memory        |                    4
  Memory Unit    |                    GB

2.  Click “Save” to add a new OpenStack computing specification.

3.  Click “Cloud Platform Specification” and click the “Add” button at the top of the list to jump to the new cloud platform specification page and enter the following cloud specification information:

CMP Specifications   |Basic Information
 :------:|:------: 
  Cloud Platform Type   |              OpenStack
  Cloud Platform     |               OpenStack
  Specifications        |               Select: CPU: 1, memory (GB) 2, root disk (GB) 
  Set as default   |          There can only be one default specification for the cloud platform in each region.

4.  Click “Submit” to add a new cloud platform specification.

5.  Configure the specifications of the compute nodes in the detailed settings of the OpenStack template service node configuration.

## Add Azure Computing Specifications {#Add Azure Computing Specifications}

1.  Go to the menu "Infrastructure" - "Calculate Specifications" and enter the new specification basic information page

Computing Specifications   |Basic Information   
:------:|:------: 
Name|    Azure Computing Specifications
CPU      |     2
CPU Unit   |     Core
Memory     |    4
Memory Unit  |    GB

2.  Click “Save” to add a new Azure computing specification.

3.  Click “Cloud Platform Specification” and click the “Add” button at the top of the list to jump to the new cloud platform specification page and enter the following cloud specification information:

CMP Specifications   |Basic Information
 :------:|:------: 
  Cloud Platform Type|            Azure
  Cloud Platform   |            Azure
  Region  |            Region corresponding to the cloud platform, for example: South China 1 (Shenzhen)
  Specifications     |             Select: CPU: 1, memory (GB) 2, Number of disks: 1
  Set as default|        There can only be one default specification for the cloud platform in each region.

4.  Click “Submit” to add a new cloud platform specification.

5.  Configure the specifications of the compute nodes in the detailed settings of the Azure template service node configuration.

# View Computing specifications

Go to the Computing specifications page and you will see a list of specifications that will list all currently available computing specifications.

Displays the specification name, CPU, CPU unit, memory, memory unit, and creation time.。

# Edit Computing specifications

In the list, click on the specification name to edit the calculated calculations for the click.

# Deleting Computing specifications

You can also select a computing specification in the list and click the "Delete" button to delete the selected computing specification. If the computing specification is in use, it will prompt that it cannot be deleted.
