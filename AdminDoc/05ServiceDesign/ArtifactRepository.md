
**Artifact Repository**



# Functions
+ The cloud platform manages the storage and version control of cloud components by connecting to mainstream artifact repositorys. The cloud components associate with artifact repositorys and customize application deployment methods and related parameters.
+ Artifact repository management is the management of artifacts generated in the software development process. Artifacts are generally released and delivered as final deliverables. All artifact packages and dependent components can be integrated into the artifact library for unified management.
+ Integrate VMware Harbor container image library to help users quickly build a private image source that can be deployed inside the organization, helping enterprises to manage images continuously and safely across cloud-native computing platforms such as Kubernetes and Docker.
+ It can quickly realize unified data entry and automated storage of image libraries and artifacts in multiple environments on the cloud management platform, and provide them for continuous integration systems and publishing systems.
+ Build a Harbor image library for internal use in the organization, which is more secure and guarantees business continuity. Unified image library management services ensure application consistency in development, testing and released environments.

# Configuration Steps
+ The cloud platform supports the realization of custom application software through the component library function, which associates the artifact repository with software components, and the artifact repository performs storage association and version control management for software components.
+ Take the integration of Harbor and provide unified image and library management services as an example, and introduce the detailed steps:
    + In the left navigation, select "Service Design"-"Artifact Repository", create multiple artifact repositories for different environments.
    ![添加制品库入口](../../picture/Admin/添加制品库入口.png)
    ![添加制品库入口-参数配置](../../picture/Admin/添加制品库入口-参数配置.png)
    + Associate Harbor artifact repositories for cloud components, which automatically store cloud components and perform version management. The specific steps are as follows: Click the software name in the software component list to enter the component view. In the "Artifacts" view, you can select Endpoint, Library (Nexus), Group, Name, and Version. Click the save button to associate the component with the package management platform.
    + In the service request interface, users can also select or use the Harbor image deployment container configured by the administrator to generate the application environment.
    ![服务申请界面选择镜像源](../../picture/Admin/服务申请界面选择镜像源.png)
    + Provide self-service operation capabilities. After a new round of iterations of development and testing, the new image built is saved in Harbor. At this time, the user can obtain the latest image from the image library and update the application environment through the self-service operation function of the cloud platform.
   ![从Harbor获取最新镜像](../../picture/Admin/从Harbor获取最新镜像.png)

