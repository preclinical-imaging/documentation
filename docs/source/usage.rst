User Instructions
=====

Using XNAT
------------
The `XNAT platform`_ provides a rich environment for managing imaging data with reporting, container-based processing and modular extensibility.
The PIXI plugin is one example of extending XNAT for a new purpose.
PIXI users should read and understand `How To Use XNAT`_ for baseline information.
The information provided below will describe functions that are specific to PIXI.

Batch Data Entry
----------------

Core XNAT provides forms that allow the user to enter data for various items managed by XNAT and the PIXI plugin.
PIXI adds a new capability where many of the data types managed by PIXI can be created or modified using a spreadsheet model and web user interface.
Core XNAT normally provides a form that operates on one item (e.g., subject) at a time.
Because many experiments in small animal imaging involve multiple subjects imaged or otherwise processed at the same time,
the PIXI plugin will allow the user to enter data in batch mode in a spreadsheet.

As with core XNAT, the PIXI system will extract metadata from DICOM files and store those directly in the XNAT database.
Mentioning data entry does not imply that users will re-enter acquisition and other metadata found in a DICOM image.
PIXI maintains the automated data extract from DICOM images into the XNAT database.


Small Animal Subject Model
--------------------------

PIXI includes a new data type to support attributes for small animal imaging that are not present in the human model in core XNAT.
Details of this and other data types are found in `PIXI Data Model <pixi_data_model.html>`_

PIXI and core XNAT support three mechanisms for creating research subjects in the database:

- User creates subjects in the web UI
- XNAT accepts DICOM files and creates subjects per data in the DICOM files (assuming subjects do not already exist)
- External software can invoke the XNAT REST API to create a subject.

We will discuss the first method on this page.
Select New -> Subjects from the main menu.

.. image:: ./pixi_create_subjects.png
 :align: center

You can then select "Create a Single Subject" for the traditional web form or "Create Multiple Subjects" for batch entry.
Select "Create Multiple Subjects" to direct PIXI to the Subject Data Manager page.

.. image:: ./pixi_subject_data_manager.png
 :align: center

In this context, you can batch enter multiple research subjects using a spreadsheet model.

- Select the project where the subject information will be stored.
- The software defaults to a spreadsheet with 5 rows, but you can increase the number of rows.

You will likely find it convenient to fill in one row and then copy/paste common data into the following rows.

*Note: You cannot copy/paste into the Subject ID row as that column requires unique values.
Copy and paste into the other cells, but enter the Subject ID information separately.*

This same page will allow you to update multiple subjects in batch mode. See the screen capture below.

.. image:: ./pixi_update_multiple_subjects.png
 :align: center

1. Select "Update existing subjects"
2. Select the project of interest
3. Shift-click multiple subjects
4. PIXI fills in the rows with existing values. Edit as necessary and then Submit to commit the changes.


Experiments for Small Animal Imaging
------------------------------------

XNAT and PIXI support a wide range of *experiments* that are in the data model just below subject.
`The XNAT wiki describes an experiment as follows <https://wiki.xnat.org/documentation/how-to-use-xnat/understanding-the-xnat-data-model>`_:

   An experiment is an event by which data is acquired.
   This data can be imaging data, or non-imaging data.
   Similar to subject, an experiment cannot exist outside the context of a project.
   It is owned by the project which first added it.
   It can additionally be shared into other projects.
::


Imaging sessions like CT, MR and PET are XNAT *experiments* and are strongly typed items that are managed in the XNAT database.
PIXI adds *experiment* types to XNAT and manages those as first class items in the XNAT database.
The table belows lists the experiment types that are added by the PIXI plugin.
The models for these data types are found in `PIXI Data Model <pixi_data_model.html>`_

+---------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------+
|  Type                     | Comments                                                                                                                                           |
+===========================+====================================================================================================================================================+
| Caliper Measurements      | An event in which a subject's tumor volume is measured manually using a caliper measurement tool.                                                  |
+---------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------+
| Drug Therapy              | An event in which a subject is administered a drug or medication.                                                                                  |
+---------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------+
| Weight                    | An event in which a subject's weight is obtained outside the context of an imaging experiment.                                                     |
+---------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------+
| Cell Line                 | An event in which a cell line is injected into a small animal subject to create an animal model that can be used for preclinical research.         |
+---------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------+
| Patient Derived Xenograft | An event in which human tumor tissue is engrafted into a small animal subject to create an animal model that can be used for preclinical research. |
+---------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------+
| Animal Husbandry          | Record animal feeding and housing information over an interval during which conditions are relatively homogeneous.                                 |
+---------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------+

Hotel Splitter
--------------

The PIXI platform supports the standard practice of scanning multiple small animals at one time using a hotel apparatus.
We anticipate that scanner vendors have yet to implement the parts of the DICOM Standard that support hotel scans,
and PIXI includes software to split the composite images into separate images that are then linked to an
individual subject.
The workflow is mostly managed through the XNAT web user interface, but there is one step to be completed at
the scanner or if the images are submitted to XNAT using the compressed uploader or XNAT Desktop Client.

#. Assign distinct labels to the individual subjects to distinguish them. This can be done before or after the imaging session.
#. Use the fixed string "Hotel" as the subject label when uploading DICOM images to XNAT.
 - The string "Hotel" can be entered at the scanner console in the field that maps to *XXXX*
 - The string "Hotel" can be added to the images at a later time before the images are uploaded using the XNAT compressed uploader.
 - The string "Hotel" can be entered as the Subject ID value when the images are uploaded using the XNAT Desktop Client








Searches
--------




.. _XNAT platform: https://www.xnat.org
.. _How To Use XNAT: https://wiki.xnat.org/documentation/how-to-use-xnat
.. _pixi_data_model:

