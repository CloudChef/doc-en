**Software Components**

Components are the basic unit that makes up the blueprint. SmartCMP has built in many common components, and you can also use SmartCMP to create, update, or delete components.

Components in SmartCMP consist of attributes and interfaces. Software components are composed of scripts, attributes, metadata, and lifecycle management. Flexible software components can be associated with mainstream product libraries. The specific concepts are as follows:

-   Script: Each phase of the lifecycle is controlled by scripts. Thanks to the powerful underlying class library, SmartCMP supports languages such as Shell, Powershell, Ruby, Python, etc., which can quickly integrate application deployment into the cloud management platform.

-   Attributes: Different application systems have custom requirements for resource requirements and capacity control. Attribute items can pass custom parameters according to different system deployment requirements. The software architect can expose the configuration parameters that the application component needs to fill out to the request interface by setting the custom attribute. The SmartCMP cloud management platform will automatically invoke the relevant parameters to execute the installation configuration of the application

-   Metadata: Metadata contains properties of the application component itself, including application component versions, related descriptions, regular inheritance relationships, and dependent system types

-   Lifecycle Management: SmartCMP cloud management platform provides complete lifecycle management of creation, configuration, start, stop, and removal of applications. All software configuration from deployment to expiration uninstallation is done through script correspondence

-   Software components are associated with the mainstream product library, supporting the docking of Jfrog Artifactory, the Nexus product library, and implementing software version updates.

-   Software architects can manage components through the component management interface. In the navigation on the left, choose Service Design - SW Components. A list of all components appears in the right navigation area.

# Out-of-box components

SmartCMP has built-in rich components commonly used in enterprises: computing, networking, storage, application software deployment, such as MySQL, Oracle, and so on. There are also some common web servers, such as WebLogic, JBoss, etc.

# Create Components

You can create components by following the steps below:

1.  Click the "Add" button in the toolbar of the component list to enter the Create Component view.

2.  Create component view contains "Basic Information" "Historical Version" "Properties" "File List" "Node Interface"

3.  In the Basic Information view, you can provide information about which classes, categories, names, component versions, system types, etc. the component inherits, and you can add a description of the component.

4.  In the Properties view, you can add the properties of a component, which consists of components, types, defaults, alternatives, and descriptions. Optional values can be added to the alternates so that when you request a service, you can only choose from the values defined in the default and alternate options. Attribute types are integer type, floating point type, character type, Boolean type

5.  In the File List view, you can add a script file by creating a new file. These script files should be associated with an operation in the component interface or by other script files. At the same time, you can add text files, which are generally used to provide configuration information for components. Multiple clicks to new file creation can add multiple files. Enter the file name, file type and click Action - Edit Content, you can write the file content on the right.

6.  In the Node Interface view, you can associate the script file added in the File List view to the corresponding operation of the component and implement it under each action by selecting the script file corresponding to this operation in the drop-down list. The default operations are configuration, create, delete, start, and stop. At the same time, you can also add more component operations here and make the corresponding script file association. Add component: Click the Add button to the right of the action.

7.  Once all required fields have been added, click the Save button to generate a new component, and the newly added component will be visible on the component list. At any time during the process of adding a component, click the "Back" button to discard the added component.

# Version Management

When you update the component, each updated version will be recorded and supported to fall back to the historical version. The specific steps are as follows:

1.  Click the "Any component" button on the toolbar of the component list to enter the software component view

2.  In the “History Version” view, you can see all the historical versions. When you make changes, the platform will record your historical version information by default: version number, version description, creator and creation time.

3.  You can check the corresponding version v1, click “Restore Version” to return from the version v2 to the historical version v1, and click “Save and Synchronize” to synchronize the component information.

4.  At the same time, it also supports one-click to delete any historical version, check the version to be deleted, click “Delete” to confirm the deletion and delete successfully.

# Associate Mainstream Product Libraries

Support software components’ association with mainstream product libraries, docking Jfrog Artifactory, Nexus product library matching package management platform and software version update. The version of the package management tool supports the latest tag, indicating that the latest version is used.

1. In the Products view, you can select endpoints, warehouses (Jfrog Artifactory, Nexus), groups, names, versions
2. Click the Save button to associate the component with the package management platform.


# Edit components

Select a component in the component list to enter the edit component view. Editing a component is similar to creating a component. To ensure that the blueprint that has been created with the component is not unusable because of the component's update, there are some items in each sub view of the component that are not allowed to change during editing. At any time during the editing of the component, click the "Back" button to discard the editing component.

# Import components

You can import component operations by following these steps:

1.  In the left navigation, select "Service Design" - "SW Components"

2.  Click the "Import" button

3.  Click "Browse", select the local component (ZIP format), and click "Submit"

4.  Component imported successfully

# Export components

You can export component actions by following these steps:

1.  In the left navigation, select "Service Design" - "SW Components"

2.  Select a component in the component list and the Export button on the menu bar will become available. Click Export

3.  Component exported successfully

# 6.1.8	Copy components

You can copy component operations by following these steps:

1.  In the left navigation, select "Service Design" - "SW Components"

2.  Select a component in the component list, the “Copy” button on the menu bar will become available, click “Copy”

3.  Go to the Edit page of the copied component to change the basic information, properties, file list, and node interface information. The component name needs to be modified, and the component does not allow duplicate names. 

# Delete components

You can remove components by following the steps below:

1.  In the component list view, select the component to be deleted

2.  After clicking the "Delete" button in the list toolbar, click confirm in the confirmation dialog, the component will be deleted.

# Ansible Component

SmartCMP has built-in basic components of Ansible type, you can create Ansible components for specific applications according to your needs, and create them in the same way as ordinary components.

1.  When editing a component, you can add variables for playbook dependencies in the Properties view.

2.  Create a playbook file in the File List view. In the playbook file, specify hosts as "local". No need to specify remote user, nor create an inventory file

3.  Transfer variables between multiple components through the blockinfile module of the playbook

4.  In the Node Interface view, select the playbook master file to be executed in the Configuration, Startup, Stop, and Delete drop-down boxes of the lifecycle.


