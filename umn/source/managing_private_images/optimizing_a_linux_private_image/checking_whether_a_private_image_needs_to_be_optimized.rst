:original_name: en-us_topic_0037352185.html

.. _en-us_topic_0037352185:

Checking Whether a Private Image Needs to be Optimized
======================================================

-  If the ECS virtualization is KVM and VirtIO drivers are not installed, optimization is required.
-  If the ECS virtualization is KVM and VirtIO drivers are installed, optimization is not required.

Procedure
---------

#. Run the following command to query the virtualization type of an ECS:

   **lscpu**

   -  If the value of **Hypervisor vendor** is **KVM**, go to the next step for further query.


   .. figure:: /_static/images/en-us_image_0125146639.png
      :alt: **Figure 1** Viewing the virtualization type of a Linux ECS

      **Figure 1** Viewing the virtualization type of a Linux ECS

#. Run the following command to check whether the ECS has VirtIO drivers installed:

   **lsinitrd /boot/initramfs-$(uname -r).img \| grep virtio**

   -  If **virtio** is displayed, VirtIO drivers have been installed. For more information, see :ref:`Creating a Linux System Disk Image from an External Image File <en-us_topic_0030713190>`.

      |image1|

   -  Otherwise, VirtIO drivers have not been installed. Optimize the private image as instructed in :ref:`Process <en-us_topic_0047501133__section862461118288>`.

.. |image1| image:: /_static/images/en-us_image_0000001443291393.png
