


**Image**
+ Overview: The instance image provides the information required to create the instance. The image file is equivalent to a copy file, and the copy file contains data in one or more cloud disks. Depending on the source, there are many types of images, including:
    + Public image, the basic image of the system provided by Alibaba Cloud official or third-party cooperative merchants, including only the initial system environment while the application environment and related software configuration need to be self-configured according to the actual situation.
    + Marketplace, providing high-quality images based on strict audits, pre-installed operating system, application environment and various software. Support one-click deployment of cloud servers without configuration.
    + Custom, generated based on user system snapshot, including initial environment, application environment and related software configuration. User cans select custom image to quickly deploy cloud server and save time from repeated configuration.

+ Scenarios: In actual business scenarios, there are situations where users need specific image templates. However, cloud platform vendors may not provide public cloud console or private cloud administrator accounts. SmartCMP cloud management platform provides users with self-defined images. When users create a virtual machine and configure the software, they could use this virtual machine as a template for repeated and efficient deployment.

+ SmartCMP supports user-defined Alibaba Cloud images. Users can create system disk snapshots and create custom images based on the snapshots. When requesting an instance, users can specify a custom image for deployment and quickly generate a new instance.





# Add an image

Users can create custom images according to the following steps:

1.  Select "Infrastructure"-"Images" in the left navigation bar and click "Add".

2.  Input the image name, description, select the cloud platform type (Alibaba Cloud), select an existing cloud platform, region, and system disk snapshot that has been created.

3.  Click "OK", the custom image is created successfully.

# Edit and delete images

Click "Infrastructure"-"Images" in the left navigation bar, select an image, click the "Edit" button, input the content to be modified, and click "OK".

Click "Infrastructure"-"Images" in the left navigation bar, select an image, and click the "Delete" button to prompt the successful deletion of the image.


# Use images

When adding a virtual machine template, select "Cloud platform type (Alibaba Cloud)", image from "Custom", select the created image through the drop-down list and submit.
