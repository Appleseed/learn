Upgrade Instructions
=======================================================

.. note ::
  This site is a work in progress. Topics marked with a  |stub-icon|  are placeholders that are currently being written. You can track the status of these topics through our public documentation `issue tracker <https://github.com/appleseed/learn/issues>`_.

Backup your website files
Backup your database
Make sure you completed steps 2 and 3
Download the latest stable release of Appleseed Portal.
Restore the backed up website to a new folder path on your web server.
Configure IIS for a new website on a different port ( 81)
Setup Permissions on the file system
Restore the database to a NEW database name.
Modify the web.config of the new website to point to the new database
Extract the contents of the UPGRADE package into a folder on your computer, it is not recommended that you extract directly over your website.
Copy the files from the extracted UPGRADE package over the contents of your website's folder.
Once you have the upgraded website running you can modify your website settings in IIS to utilize the new website, rather than the non-upgraded website.
Check to see if the client is using any modules that were removed from the upgrade
Check to see if the client's custom modules are still working as they did before the upgrade.

.. toctree::
    :titlesonly:
  
.. include:: common.txt
