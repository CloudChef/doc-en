
**Resource tag**



# Resource tag

Core functions of tags: Set resource tags for the managed resource pools and indicate the different uses and attributes of the resource pools, so that they can be filtered and specified when configuring and applying for services. 

Specific steps for adding tags: Click "Infrastructure"-"Resource tags", the administrator has the authority to configure tags and define the parameters of the tags.

+  Configure the "Basic Information" of the resource tag: name (generally configured in Chinese, such as 环境), primary key (only letters and numbers, such as env, as the identification bit), description, order (defines the order of tag selection) , selection type ( Single-selection / multiple-selection, specify how tags select value sets when performing filtering), specified resource types: cloud resources (for example: resource pool), storage resources (for example: vSphere data storage, OpenStack storage type), network resources. Note: You can set multiple tags for the same resource pool. For example, you can choose different tags for storage or network resources in the same vSphere resource pool. 

+  Configure the "value set" of the resource tag. For example, when the key is an environment and supports creation of a value, it supports adding a value set (for example, production environment), and it also supports adding multiple value sets (for example, production environment, test environment and development environment) and each value needs to be configured with a name, a primary key (which can be used for naming rules), and a description. Click the Save button and the resource tag is created. 


# Using Resource Tags

After the resource label is created, bind the resource pool to the resource label. Specific operation steps: Click "Infrastructure"-"Resource pool management" on the left navigation bar and select "Key Value" in the resource label. A resource pool can only select one key but one or more values. for example: vSphere resource pool, key is selected as "environment", select a value "development environment" or multiple values "production environment, test environment, development environment".

Scenarios of resource tags in service configuration: Configure the resource pool of Server or Instance node. The available resource pools are derived from the "shared resource pool or the resource pool bound to the business group". The role of the resource tag in selecting the resource pool: 

+   Select a strategy for manually specifying a resource pool, and then filter based on the selected resource tags, and then select based on the results of the tag filtering and choose whether to allow modification during request or approval. For example: configuration of vSphere Cloud Service Server component. Select the strategy for manually specifying the resource pool, select the resource pool "vSphere Development " with the "Development Environment" resource tag, and check "Allow modification" and "Change only during approval". After the service configuration is completed, when the service is applied, the resource pool can be selected again. 

+   Select the resource pool selection policy of "Automatically select the one with largest remaining capacity, lowest cost or evenly allocate". The platform will automatically allocate according to the policy, and when it is automatically allocated, you can only choose among the resource pools filtered by tags. For more service configuration information, please refer to: [Service Configuration](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/ServiceConfiguration.html)

+   Scenarios of resource tags in service requests: Configure resource pools in the service configuration to allow modification. On the application page, for each key, according to the resource tags configured in the resource pool, only the values already used in the resource pool are displayed. 


>「Note」In the scenario of "multiple keys and each key has multiple values". For example, there are two keys, "Environment, Performance". When the key is the environment, there are three values below, which are "Pro, UAT, Dev"; when the key is performance, the three values below are "high performance, medium performance, and general performance". There are two resource pools (vSphere-dev resource pool and vSphere-test resource pool). The vSphere-dev resource pool has 2 tags Pro and high performance, and the vSphere-test resource pool has 2 tags UAT and general performance. When configuring the display of cloud resources and service request pages, only Pro and UAT are displayed under "Environment", and only high performance and general performance are displayed under "Performance". After selecting one of the resource tag values arbitrarily, the remaining tag display must be dynamically adjusted based on the selection of the value of the first resource tag. For example: first select the value “Pro” of the resource label, and the remaining second label will only show “high performance”. By analogy, in application scenarios with more keys and more values, the selection logic is also consistent. 

