:original_name: en-us_topic_0121682346.html

.. _en-us_topic_0121682346:

Getting Started
===============

This section describes how to make API calls to create a private image from an ECS.

For details about how to call APIs, see :ref:`Calling APIs <en-us_topic_0121671868>`.

.. note::

   -  Before using an ECS to create a private image, ensure that the ECS is stopped.
   -  The token obtained from IAM is valid for only 24 hours. If you want to use a token for authentication, you can cache it to avoid frequently calling the IAM API.

Involved APIs
-------------

If you use a token for authentication, you must obtain the token and add **X-Auth-Token** to the request header of the IMS API when making an API call.

-  IAM API used to obtain the token
-  IMS API used to create a private image

Procedure
---------

#. Obtain the token by referring to :ref:`Authentication <en-us_topic_0121671869>`.

#. Send **POST https://IMS endpoint/v2/cloudimages/action**.

#. Add **X-Auth-Token** to the request header.

#. Specify the following parameters in the request body:

   ::

      {
          "name": "ims_test",  //Image name (a mandatory string)
          "description": "Image creation from an ECS",  //Image description (an optional string)
          "instance_id": "877a2cda-ba63-4e1e-b95f-e67e48b6129a",  //ECS ID (a mandatory string)
          "tags": [
                   "aaa.111",
                   "bbb.333",
                   "ccc.444"
          ]  //Image tag list (optional, List<String>)
      }

   If the request is successful, a job ID is returned.

   If the request fails, an error code and error information are returned. For details, see :ref:`Error Codes <en-us_topic_0022473689>`.

5. Query job details using the job ID by referring to :ref:`Asynchronous Job Query <en-us_topic_0022473688>`.

   If the job status is **SUCCESS**, the private image is successfully created.

   For details about status codes for request exceptions, see :ref:`Status Codes <en-us_topic_0121643825>`.

6. Obtain the image ID from the body of the job and query, delete, and export the private image using the image ID.
