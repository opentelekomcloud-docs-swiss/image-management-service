:original_name: en-us_topic_0125866393.html

.. _en-us_topic_0125866393:

Image Sharing
=============

+---------------------------------------------------------------------+--------------------------------------------------+---------------------+-------------+--------------------+
| Permissions                                                         | APIs                                             | Actions             | IAM Project | Enterprise Project |
+=====================================================================+==================================================+=====================+=============+====================+
| Adding an Image Member (Native OpenStack API)                       | POST /v2/images/{image_id}/members               | -  ims:images:get   | Y           | x                  |
|                                                                     |                                                  | -  ims:images:share |             |                    |
+---------------------------------------------------------------------+--------------------------------------------------+---------------------+-------------+--------------------+
| Updating the Image Sharing Status in Batches (Native OpenStack API) | PUT /v2/images/{image_id}/members/{member_id}    | -  ims:images:get   | Y           | x                  |
|                                                                     |                                                  | -  ims:images:share |             |                    |
+---------------------------------------------------------------------+--------------------------------------------------+---------------------+-------------+--------------------+
| Querying Image Member Details (Native OpenStack API)                | GET /v2/images/{image_id}/members/{member_id}    | -  ims:images:get   | Y           | x                  |
|                                                                     |                                                  | -  ims:images:share |             |                    |
+---------------------------------------------------------------------+--------------------------------------------------+---------------------+-------------+--------------------+
| Querying Image Members (Native OpenStack API)                       | GET /v2/images/{image_id}/members                | -  ims:images:get   | Y           | x                  |
|                                                                     |                                                  | -  ims:images:share |             |                    |
+---------------------------------------------------------------------+--------------------------------------------------+---------------------+-------------+--------------------+
| Deleting an Image Member (Native OpenStack API)                     | DELETE /v2/images/{image_id}/members/{member_id} | -  ims:images:get   | Y           | x                  |
|                                                                     |                                                  | -  ims:images:share |             |                    |
+---------------------------------------------------------------------+--------------------------------------------------+---------------------+-------------+--------------------+
| Adds image members.                                                 | POST /v1/cloudimages/members                     | ims:images:share    | Y           | x                  |
+---------------------------------------------------------------------+--------------------------------------------------+---------------------+-------------+--------------------+
| Updates the status of image members in batches.                     | PUT /v1/cloudimages/members                      | ims:images:share    | Y           | x                  |
+---------------------------------------------------------------------+--------------------------------------------------+---------------------+-------------+--------------------+
| Deletes image members in batches.                                   | DELETE /v1/cloudimages/members                   | ims:images:share    | Y           | x                  |
+---------------------------------------------------------------------+--------------------------------------------------+---------------------+-------------+--------------------+
