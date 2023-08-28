Getting Started: XNAT Deployment, the PIXI Plugin, Related Plugins
=======================================

---------------
Identify Plugins
---------------
XNAT provides a rich set of features that are extended for preclinical imaging by the PIXI plugin.
The fact that you are reading this page means that you will want to install the PIXI plugin as part of XNAT installation.
These are other plugins that can be useful:

- OHIF Viewer: The supported mechanism for viewing DICOM images, making measurements and recording contours and regions of interest in XNAT.
- Container Service: Used by XNAT to delegate compute jobs to a Docker container environment.

Identify and download the PIXI plugin and other desired plugins. You will find a master list of XNAT plugins here:

---------------
XNAT Deployment
---------------
XNAT can be deployed to support different environments ranging from a single user running on a laptop to a larger enterprise system.
Please review descriptions below and choose the deployment environment that best suits your needs.

+---------------------------------------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------+
| Broad Category                              | Comments        |  Installation Instructions                                                                                                           |
+=============================================+=================+======================================================================================================================================+
| Student / Personal Data Management          | Docker Desktop  | https://wiki.xnat.org/documentation/getting-started-with-xnat/running-xnat-in-a-dockerized-container-with-configurable-dependencies  |
+---------------------------------------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------+
| Developer / Local Deployment                | Vagrant         | https://wiki.xnat.org/documentation/getting-started-with-xnat/running-xnat-in-a-vagrant-virtual-machine                              |
+---------------------------------------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------+
| Lab Installation / No Digital Certificates  |Tomcat / Postgres| https://wiki.xnat.org/documentation/getting-started-with-xnat/xnat-installation-guide                                                |
+---------------------------------------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------+
| Enterprise Level / Comprehensive IT Support | Reverse Proxy   | https://wiki.xnat.org/documentation/getting-started-with-xnat/xnat-installation-guide                                                |
+---------------------------------------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------+


---------------
PIXI Plugin and Related Plugins
---------------

The deployment instructions above assume