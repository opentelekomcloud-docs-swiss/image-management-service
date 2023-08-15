:original_name: en-us_topic_0030713184.html

.. _en-us_topic_0030713184:

Registering an External Image File as a Private Image
=====================================================

Scenarios
---------

Register an image file uploaded to the OBS bucket as a private image.

Procedure
---------

#. Access the IMS console.

   a. Log in to the management console.

   b. Under **Compute**, click **Image Management Service**.

      The IMS console is displayed.

#. Register an external image file as a private image.

   a. Click **Create Image** in the upper right corner.

   b. Set image parameters.

      :ref:`Table 1 <en-us_topic_0030713184__table050019474117>` and :ref:`Table 2 <en-us_topic_0030713184__table6978715749>` list the parameters in the **Image Type and Source** and **Image Information** areas, respectively.

      .. _en-us_topic_0030713184__table050019474117:

      .. table:: **Table 1** Image type and source

         +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Parameter                         | Description                                                                                                                                                                                                                                                                                                                                   |
         +===================================+===============================================================================================================================================================================================================================================================================================================================================+
         | Type                              | Select **System disk image**.                                                                                                                                                                                                                                                                                                                 |
         +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Source                            | Select **Image File** for **Source**. Select the bucket storing the image file from the list and then select the image file.                                                                                                                                                                                                                  |
         +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Enable Fast Create                | This parameter is available only when you select a ZVHD2 or RAW image file.                                                                                                                                                                                                                                                                   |
         |                                   |                                                                                                                                                                                                                                                                                                                                               |
         |                                   | This function enables fast image creation and supports import of large files (up to 1 TB) as long as the files to be uploaded are converted to ZVHD2 or RAW format and optimized. If you have a file that meets the requirements, select **Enable Fast Create** and select the confirmation information following **Image File Preparation**. |
         |                                   |                                                                                                                                                                                                                                                                                                                                               |
         |                                   | .. note::                                                                                                                                                                                                                                                                                                                                     |
         |                                   |                                                                                                                                                                                                                                                                                                                                               |
         |                                   |    To learn how to convert image file formats and generate bitmap files, see :ref:`Quickly Importing an Image File <en-us_topic_0030713151>`.                                                                                                                                                                                                 |
         +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

      .. _en-us_topic_0030713184__table6978715749:

      .. table:: **Table 2** Image information

         +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Parameter                         | Description                                                                                                                                                                                                                                                                                                                 |
         +===================================+=============================================================================================================================================================================================================================================================================================================================+
         | Enable automatic configuration    | If you select this option, the system will automatically check and optimize the image file. For details, see :ref:`What Will the System Do to an Image File When I Use the File to Register a Private Image? <en-us_topic_0032307025>`                                                                                      |
         +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Function                          | Specifies whether the image is used to create ECSs or BMSs. The value can be **ECS system disk image** or **BMS system disk image**. This section uses **ECS system disk image** as an example.                                                                                                                             |
         +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Boot Mode                         | This parameter is optional. The value can be BIOS or UEFI. For details about the differences between the two, see :ref:`How Is BIOS Different from UEFI? <en-us_topic_0113533721>`                                                                                                                                          |
         |                                   |                                                                                                                                                                                                                                                                                                                             |
         |                                   | For details about which OSs support UEFI boot, see :ref:`OSs Supporting UEFI Boot Mode <en-us_topic_0170853315>`                                                                                                                                                                                                            |
         |                                   |                                                                                                                                                                                                                                                                                                                             |
         |                                   | The boot mode must be the same as that in the image file. You need to confirm which boot mode is used in the image file. After you select the correct boot mode, the boot mode will be configured for the image at the background. Select the right boot mode, or ECSs created using the image will not be able to boot up. |
         +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | OS                                | To ensure that the image can be created and used properly, select an OS consistent with that in the image file. If you do not select an OS, the system attempts to automatically identify the OS in the image file.                                                                                                         |
         |                                   |                                                                                                                                                                                                                                                                                                                             |
         |                                   | .. note::                                                                                                                                                                                                                                                                                                                   |
         |                                   |                                                                                                                                                                                                                                                                                                                             |
         |                                   |    -  If the system detects that the image file OS is different from the one you selected, the OS detected by the system will be used.                                                                                                                                                                                      |
         |                                   |    -  If the system cannot detect the OS in the image file, the OS you selected will be used.                                                                                                                                                                                                                               |
         |                                   |    -  If the OS you selected or identified by the system is incorrect, ECSs created from the image file may be affected.                                                                                                                                                                                                    |
         +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | System Disk (GB)                  | The system disk capacity (value range: 40 GB to 1024 GB). Ensure that this value is at least equal to the system disk size in the image file.                                                                                                                                                                               |
         |                                   |                                                                                                                                                                                                                                                                                                                             |
         |                                   | .. note::                                                                                                                                                                                                                                                                                                                   |
         |                                   |                                                                                                                                                                                                                                                                                                                             |
         |                                   |    If the uploaded VHD image is generated using qemu-img or similar tools, check the system disk size based on :ref:`What Do I Do If the System Disk Size in a VHD Image File Exceeds the One I Have Specified on the Management Console When I Use This File to Register a Private Image? <en-us_topic_0058841396>`        |
         +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Name                              | Set a name for the image.                                                                                                                                                                                                                                                                                                   |
         +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Tag                               | (Optional) Set a tag key and a tag value for the image to make identification and management of your images easier.                                                                                                                                                                                                         |
         +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Description                       | (Optional) Enter a description of the image.                                                                                                                                                                                                                                                                                |
         +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   c. Click **Apply Now**, confirm the configurations, and click **Submit Application**.

#. Go back to the **Private Images** page. The image is successfully registered when its status becomes **Normal**.

   If you add data disks during image creation, a system disk image and data disk images will be generated. The number of data disk images depends on the number of data disks you add (a maximum of 3).

   .. note::

      The time required for image registration is determined by the image file size. You may need to wait a long period of time for the image file to be successfully registered as a private image.
