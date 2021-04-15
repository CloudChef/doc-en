


**Image**

+ Overview: The instance image provides the information required to create the instance. The image file is equivalent to a copy file, and the copy file contains data in one or more cloud disks.
+ SmartCMP cloud management platform provides users with self-defined images. In actual business scenarios, there are situations where users need specific image templates. However, cloud platform vendors may not provide public cloud console or private cloud administrator accounts.  
+ When users create a virtual machine and configure the software, they could use this virtual machine as a template for repeated and efficient deployment.
    Depending on the source, there are many types of images, including:
       + Public image, the basic image of the system provided by Alibaba Cloud official or third-party cooperative merchants, including only the initial system environment while the application environment and related software configuration need to be self-configured according to the actual situation.
       + Marketplace, providing high-quality images based on strict audits, pre-installed operating system, application environment and various software. Support one-click deployment of cloud servers without configuration.
       + Custom, generated based on user system snapshot, including initial environment, application environment and related software configuration. User cans select custom image to quickly deploy cloud server and save time from repeated configuration.


+ SmartCMP supports user-defined Alibaba Cloud images. Users can create system disk snapshots and create custom images based on the snapshots. When requesting an instance, users can specify a custom image for deployment and quickly generate a new instance.



# Add and Use Images

Taking the deployment of Alibaba Cloud ECS service as an example, users can create a custom Alibaba Cloud image and quickly deploy cloud services according to the following steps:

1.  In the left navigation bar, select "Deployments"-"My Deployments", and select the deployed Alibaba Cloud service. Select system disk resource on the details page, click the snapshot information and add a system disk snapshot.

2.  After creating the snapshot, you can select "Infrastructure"-"Images" and "Add" a custom image based on the system disk snapshot.

3.  Enter the image name and description, select the cloud platform type (Alibaba Cloud), select an existing cloud platform, region, and created system disk snapshot.

4.  Click "OK", the custom image is created successfully.

5.  Next, you need to create a template for the created custom image in the virtual machine template. In the left navigation bar, select "Infrastructure"-"VM Templates"-CentOS 7, and add Alibaba Cloud image template.

6.  Enter the name, cloud platform type and other parameters, select Custom for the image source, and select the custom Alibaba Cloud image just created for the image name. Click save.

7.  At this point, when users apply for the Alibaba Cloud ESC service in the service catalog, they can select the image of the created virtual machine template to achieve rapid and efficient deployment.

# Edit and delete images

Click "Infrastructure"-"Images" in the left navigation bar, select an image, click the "Edit" button, input the content to be modified, and click "OK".

Click "Infrastructure"-"Images" in the left navigation bar, select an image, and click the "Delete" button to prompt the successful deletion of the image.


