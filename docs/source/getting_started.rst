Getting Started: The PIXI Plugin and Related Plugins, XNAT Deployment
=======================================

---------------
Identify Plugins
---------------
XNAT provides a rich set of features that are extended for preclinical imaging by the PIXI plugin as well as other plugins.
An XNAT plugin is a jar file that will be placed in a plugins folder as part of the deployment process.
The fact that you are reading this page means that you will want to install the `PIXI plugin`_ as part of XNAT installation.
Core XNAT plugins are found on the `XNAT Downloads page`_.
In addition to the PIXI plugin, you will find these plugins useful:

- XNAT OHIF Viewer: The XNAT OHIF Viewer allows users to view, create and edit ROI collections and annotations on XNAT image sessions. This viewer was developed by the Institute for Cancer Research, London and is based on the Javascript-based OHIF Viewer.
- Container Service: The Container Service plugin allows you to execute external processing tools as lightweight containers, mounting and reading XNAT data, then posting outputs back to your XNAT project.
- Batch Launch: The Batch Launch plugin is a companion to the Container Service and allows you to launch containers or pipelines in batches based on project listings or search listings of XNAT data.
- JupyterHub Integration: The JupyterHub Integration plugin allows your XNAT to connect to a running JupyterHub server and creates integration points for launching and saving Jupyter Notebooks.

---------------
XNAT Deployment
---------------
XNAT can be deployed to support different environments ranging from a single user running on a laptop to a larger, enterprise-level system.
Please review descriptions below and choose the deployment environment that best suits your needs.
The broad categories provide suggestions about the intended about the owner and administrator of the system.
When you select an installation procedure and work through the steps, please remember it will be useful to have the plugin jar files before you start.

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

.. _XNAT Downloads page: https://www.xnat.org/download/
.. _PIXI plugin: https://www.pixi.org/
