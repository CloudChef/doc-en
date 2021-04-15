**Components Library**


The cloud component of the SmartCMP cloud management platform has the core capability of providing any resources as a service. It not only has rich component resources and common operations built in, but also has a highly scalable capability. It can flexibly customize component resources and configure operations. The definition of components adopts an object-oriented design method, uses a unified data structure for modeling, and standardizes configuration properties. Software architects can also create reusable software components as needed and use operation scripts to accurately specify the deployment operation process. Platform supports rewriting these operation scripts at any time, releases them in real time, and synchronously updates installed software components. By defining attributes and passing attributes as parameters to action scripts, software components can be deployed in different environments without modifying the script. Support to use Ansible, Terraform, Shell, Python, Json, Ruby and other languages to customize software components, and customize the life cycle operations of software components (including creation, configuration, start, stop, delete, backup, inspection, etc.). System has built-in create, configure and start operations, call stop and delete operations when removed, and support flexible custom operations to achieve full lifecycle management of software and applications. 

Components in SmartCMP consist of attributes and interfaces. Software components are composed of scripts, attributes, metadata, and lifecycle management. Flexible software components can be associated with mainstream product libraries. The specific concepts are as follows:

 -   Script: Each phase of the lifecycle is controlled by scripts. Thanks to the powerful underlying class library, SmartCMP supports languages such as Shell, Powershell, Ruby, Python, etc., which can quickly integrate application deployment into the cloud management platform.

 -   Attributes: Different application systems have custom requirements for resource requirements and capacity control. Attribute items can pass custom parameters according to different system deployment requirements. The software architect can expose the configuration parameters that the application component needs to fill out to the request interface by setting the custom attribute. The SmartCMP cloud management platform will automatically invoke the relevant parameters to execute the installation configuration of the application

 -   Metadata: Metadata contains properties of the application component itself, including application component versions, related descriptions, regular inheritance relationships, and dependent system types

 -   Lifecycle Management: SmartCMP cloud management platform provides complete lifecycle management of creation, configuration, start, stop, and removal of applications. All software configuration from deployment to expiration uninstallation is done through script correspondence

 -   Software components are associated with the mainstream product library, supporting the docking of Jfrog Artifactory, the Nexus product library, and implementing software version updates.

 -   Software architects can manage components through the component management interface. In the navigation on the left, choose Service Design - SW Components. A list of all components appears in the right navigation area.



# Rich Component Library{#Component Library}

Out-of-the-box component resources. SmartCMP cloud management platform has a large number of commonly-used component resources, including IaaS (cloud hosts, networks, storage, etc. for different cloud platforms), PaaS (servers, databases, RDS, etc.), containers (Kubernetes , Docker), software (MySQL, Oracle, Nginx, etc.), agents (monitoring agents, automation agents). Different types of resources are created and managed in a unified interface, using a tree-like grouping catalog, supporting custom component grouping, secondary editing, quick copy, importing, and exporting components.


## Tree Grouping Catalog


Supports a grouped catalog of components and a tree structure. You can search for tree displays in creating components page and component lists. The tree structure on the component list page can be added, deleted, and modified. Existing component catalogs cannot be deleted. 
The tree structure is a logical folder concept and has no binding relationship with the resource type of the component. The tree structure allows users to adjust. 
For example, some users have a cloud platform at the first level, and computing, storage, and network components under the cloud platform at the second level; and some users have computing, network, and storage at the first level, and each has a second level. cloud platform. 
Details:

+ IaaS is used to describe all IaaS components. Each component has its own cloud platform type. The secondary nodes under IaaS mainly include computing, network, storage, object storage, load balancing, security group, file system, etc. 
The following subdirectories are added by default. 
Cloud host  
Storage  
OSS: Object storage  
Disk: Block storage  
NAS Network: Network  
Subnet: Subnet  
Router: Routing 
SecurityGroup: Security group  
Firewall  
Load balancing  
Load balancing listener  
Floating IP  
Domain name  
Gateway 



+ PaaS is used to describe all PaaS components. Each component has its own cloud platform type. The secondary nodes under PaaS mainly include the service capabilities provided by the cloud platform. 
By default, the following subdirectories are added. 
Web  
APP  
MQ  
Cache: cache  
RDS  
NoSQL  
BigData : Big Data Services

+ Container is used to describe all the components of the container platform.  
Docker  
Kubernetes

+ Software component is used to describe all software components. Each component has its own cloud platform type. The software is divided into two types, one is binary installed software that runs inside the machine, and the other is container image software running in the container. 
The container image component can be distinguished by type, and an attribute resource.software is added to mark whether the software is running in the machine or the container. 
The following subdirectories are added by default: 
Web  
APP  
MQ  
Cache: Cache  
RDS  
NoSQL  
BigData: Big Data Service 


+ Agent, which means all agent components, including automation components, monitoring components, etc., for subsequent agent management. 
Monitoring agents and automation agents 

>「Note」 Monitoring component: If you need to use cloud platform monitoring to view cloud server indicator data and generate alerts, you need to properly install the monitoring component on the cloud server. Cloud server indicator data collection depends on the monitoring component. 


## Edit component

Select a component in the component list to enter the edit component view. Editing a component is similar to creating a component. In order to ensure that the blueprints created using this component will not be unusable due to component updates, during editing, there are some items in each sub view of the component that are not allowed to change. Click the "Back" button at any time during the process of editing the component to abandon editing the component.



## Import and export components

You can import components according to the following steps:

1.  Select "Service Design"-"Component Library"

2.  Click the "Import"

3.  Click "Browse", select the local component (ZIP format), and click "Submit"

4.  The component is imported successfully



You can export components according to the following steps:

1.  Select "Service Design"-"Component Library"

2.  Select a component in the component list, the "Export" button on the menu bar will become available, click "Export"

3.  The component is exported successfully



## Copy / delete components

You can follow these steps to copy components:

1.  Select "Service Design"-"Component Library"

2.  Select a component in the component list, the "Copy" button on the menu bar will become available, click "Copy"

3.  Enter the editing page of the replication component to change the basic information, attributes, script list, and node interface information. The component name needs to be modified as the component does not allow duplicate names


You can remove components according to the following steps:

1.  In the component list view, select the component to be deleted

2.  After clicking the "Delete" button in the list toolbar, confirm in the confirmation dialog box and the component will be deleted




# Create Components{#Create Components}

Users can create reusable components according to their needs, componentize any resource, and standardize the process of configuring components, including defining resource types, versions, attributes, component operations, etc., and all configuration interfaces are open to user customization. For example, when a DBA creates a database cluster and an Oracle database needs to be deployed, DBA can add Oracle components to the component library and configure components according to requirements, including configuring component	 profiles, instructions, properties, scripts, and operations (create, start, stop, restart, delete, etc. the specified database)

Support software architects to customize software components. Specific steps for adding components:

1.  Click the "Add" button to enter the create component view.

2.  The create component view contains "Basic Information", "Attributes", "Script List", "Operations", "History Version", and "Artifacts".

## Component Overview
In the "Basic Information" view, define the component name, description, component version, component type (define the resource type of the component and determine the properties and operations of the component. For example, when you select the component type as Software when adding an Oracle component, the newly created Oracle component will be Inherit the properties and operations of the software component of the parent class. You can also customize the properties to obtain different functions from the parent class.), cloud platform information and upload icon. You can also add a description of the component.
+ After selecting Artifact, you can select the binary software artifact library on the " Artifacts" tab to configure the software version. For specific steps, refer to associating mainstream artifact libraries.
+ Check Instantiate. After checking, the component can be arranged by Blueprint Design. In the left navigation, select "Service Design"-"Blueprint Design", and a list of all components appears in the right navigation area.



## Component Attributes
Attributes: It is used to meet the specific requirements of resource deployment and parameter control of different systems. It is composed of primary key, type, default value, alternatives and description. You can add optional values to the alternatives, so that when you apply for service, you can only choose from the values defined in the default and alternatives. You can create software attributes that require the use of characters, floating point numbers, passwords, Booleans, or integer values. Support for setting validation rules. Enter regular expressions and the attribute parameter must pass the validation of the expression. (Example: Integer type: Use integer attribute types for zero and positive or negative integers. Boolean type: Use Boolean attribute types to provide True and False options in the Value drop-down menu.) 

In the Properties view, add the properties of the component. After the addition is complete, you can pass them as parameters to the operation script. For example, when the component Oracle is created, different application systems have specific requirements and custom requirements for Oracle's deployment requirements and parameter control. "Attributes" can be set according to the deployment requirements of different systems, by setting custom attributes, exposing configuration parameters that application components need to fill out to the interface configuration, and passing custom parameters.

When Oracle is deployed automatically, the SmartCMP cloud management platform automatically invokes relevant parameters to perform application installation and configuration, which meets different requirements for Oracle deployment in different data clusters.



## Script List
Scripts: Each stage of the component life cycle is controlled by scripts. Thanks to the powerful underlying class libraries, it supports customizable scripts including Ansible, Terraform, Shell, Python and other methods.
In the "Script " view, you can add a script file by creating a new file. These script files should be associated with an operation in the component interface or referenced by other script files. At the same time, you can add text files, which are typically used to provide configuration information for the component. Multiple clicks to create a new file can add multiple files. After entering the file name and file type, click Action-Edit Content. You can write the file content on the right.


## Actions
Action: You can perform complete life cycle management on the application system creation, configuration, start, stop, and delete processes. Through script correspondence, complete all software configuration work from installation and deployment to uninstallation after expiration.

In the "Action" view, you can associate the script file added in the "Script List" view to the corresponding operation of the component, which is implemented under each operation action-please select the script file corresponding to this operation from the drop-down list.

Built-in actions include configuration, creation, delete, start, stop, and more. Take the refresh operation as an example, the operation is configured in system in advance, and the implementation methods, scripts, tasks, and parameters necessary for the operation are used. The built-in operation can be applied to any resource on the platform. Therefore, when the component Oracle is created, the built-in "start, stop, restart, delete, refresh" operations are automatically inherited. 

Encapsulation hides the implementation details of complex operations and only provides public access to the outside world. The platform has complex operations built-in and works out of the box, reducing differences and difficulty in understanding. For example: "adjust virtual machine configuration" operation (adjust virtual machine calculation specifications and cloud platform specifications), when the cloud platform type is different, the SmartCMP cloud management platform hides the details of the flow of resource operations, only exposing public access interfaces. For example, the "Adjust virtual machine configuration" operation is applied to a virtual machine on the Hyper-V platform and a virtual machine on the OpenStack platform. The specific technical implementation is different, but the user configuration interface displays the same content.

At the same time, you can also add more component actions here and associate the corresponding script files. Click the Add button. After all required fields are added, click the Save button to generate a new component. You can see the newly added component on the component list. Click the "Back" button at any time during the process of adding components to discard adding components. 


Life cycle action | Description | Example
:------:|:------:|:------:
Create |     Create Software|     Create a Tomcat service, and scripts written for the Create lifecycle operation will run when the software is first installed.
Configuration  |	Configurate software  |	Configure Tomcat and set JAVA_OPTS and CATALINA_OPTS. The configuration script runs after the installation operation is complete.
Start  |	Start software  |	Use the startup command in the Tomcat server to start the Tomcat service. The startup script runs after the configuration operation is complete.
Stop  |	Stop software	|  Use the stop command in the Tomcat server to stop the Tomcat service. The stop script runs after the start operation is complete.
Delete  |	Delete software  |	Perform specific actions in the application before destroying the deployment. The delete script runs after the software component is destroyed.


###	Configuration Action{#Configuration Action}

While a large number of common actions are built in, system supports the operation of custom components, and the configuration interface is open to users, including the implementation of custom actions (supporting scripts / tasks); scripts (scripts come from custom script files); filter conditions, the components action supports the filter condition of EL expression. When the expression is customized, the action can be displayed in the action list only when the filter condition is satisfied. After the display becomes effective, it can be selected for execution. Otherwise, the action will not be displayed in the action list.

> The format of the expression, for example: $ {param}, $ {param> 1}, $ {param == 'abc'}, $ {param! = Null}, $ {param == null}, when you fill in the expression $ {componentType! = 'resource.iaas.instance.vSphere'} indicating that the component type needs to be a virtual machine of the vSphere cloud platform, and the customized action can take effect on the component resources that "fulfill the above conditions", that is, it will be displayed in the " vSphere cloud platform virtual machine action list "and support the corresponding operations.

Action grouping (actions are grouped, for example: start, stop, suspend, restart, etc. under common actions; change setting labels, adjust virtual machine configuration, update cloud host name, etc. under configuration actions)

And the specific parameter configuration (timeout time and maximum number of retries) performed.

 For example: add a backup operation to the IaaS cloud host resource (the Linux virtual machine of the vSphere cloud platform). Customize the basic information of the operation. Customize the "backup script backup.sh" in the script list. When configuring the operation, select the script backup.sh, bind the script to the operation, and select the operation mode as "Shell".


>「Note」The Linux virtual machine of the vSphere cloud platform. The added operations are supported on the "Deployments"-"Instance" page. For details, please refer to:  [Cloud Resource Operation Entitlement](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/Workflow.html#Cloud%20Resource%20Operation%20Entitlement%20.afff6)

![操作-脚本列表](../../picture/Admin/操作-脚本列表.png)

![操作-基本信息](../../picture/Admin/操作-基本信息.png)


Software component form configuration: In the software component, parameters and forms can be configured for the "create" action and other custom actions, where the form is dynamically generated based on attributes. The content of the completed form is configured (supports JSON format), and the preview of the form can also be displayed directly to meet various needs.

![表单配置-参数](../../picture/Admin/表单配置-参数.png)

![表单配置-表单](../../picture/Admin/表单配置-表单.png)


Support for secondary update operation. The system has provided the implementation of this operation. If you need to override, you can enable the option "Override system action". In the "Action" view, click any action to enter the basic information tab page. When the selected primary key name matches the existing built-in action of the system, the option and prompt to overwrite the operating system will appear. Select "Overwrite system action" and later information such as implementation configuration, execution configuration, and form configuration will appear.



## Dependencies

Some component resources cannot be deployed separately. For example, software components need to be deployed in conjunction with other component resources to support the creation and management of dependencies between the current component and other components. Dependencies are used to define the different sequence of multiple components in the scenario of simultaneous orchestration and deployment, and runtime parameters can be passed between components that have dependencies.

In the "Dependencies" view: Select the type (included / dependent), and then select the target component. For example, in the vSphere cloud platform, the MySQL component and Serve component are included, and the Serve component and Network component are dependent.





## Version Management

When you update the component, each updated version will be recorded and supported to fall back to the historical version. The specific steps are as follows:

1.  Click the "Any component" button on the toolbar of the component list to enter the software component view

2.  In the “History Version” view, you can see all the historical versions. When you make changes, the platform will record your historical version information by default: version number, version description, creator and creation time.

3.  You can check the corresponding version v1, click “Restore Version” to return from the version v2 to the historical version v1, and click “Save and Synchronize” to synchronize the component information.

4.  At the same time, it also supports one-click to delete any historical version, check the version to be deleted, click “Delete” to confirm the deletion and delete successfully.




## Associate Mainstream Product Libraries

Support software components’ association with mainstream product libraries, docking Jfrog Artifactory, Nexus product library matching package management platform and software version update. The version of the package management tool supports the latest tag, indicating that the latest version is used.

1. In the Products view, you can select endpoints, warehouses (Jfrog Artifactory, Nexus), groups, names, versions
2. Click the Save button to associate the component with the package management platform.





