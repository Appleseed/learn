
=============================
Theme / Layout Designer Guide
=============================

Overview
--------
The files for updating the design of an Appleseed site are located in the /Design folder of the site. 

Making a Layout
---------------
The files for editing or creating a layout are located in the /Design/DesktopLayouts folder.
Each layout should have it own uniquely named folder wothin this folder. 
This folder will include ascx (ASP.NET control) files, which are basically HTML files to which C# and ASP.NET code can be added for functionality. They will have some code in <% … %> tags which should generally left to developers.

A basic layout should have the following files :

- DesktopAdmin.ascx - Sets up the layout of the Admin Bar that appears when an Admin user is logged in.
- DesktopPortalBanner.ascx - Sets up the layout of the Header section of the site including the top menu. 
- DesktopFooter.ascx - Optionally sets up the layout of the Footer section. Fat Footer Layout that may be edited by the admin user should be put in an HTML module in the Bottom Pane of the site.
- PanesMaster.ascx - Sets up the layout of the default Panes section of the site. Bootstrap classes should be added the <div> elements as necessary.
- SiteMaster.ascx - Sets up the Head section of the HTML document, and the general layout, including the <body> element and the wrapping <form> element, if Web Forms is being used. Javascript files can be registered at the top of the file. Bootstrap classes should be added the <div> elements as necessary.

An alternate or child layout can be set up with just one file:

- PanesMaster.ascx 

The C# code at the top of this file should ppoint back to the parent theme.

Making a Theme
--------------
The files for editing or creating a theme are located in the /Design/Themes folder:

- Theme.xml - required, generally no need to change. 
- default.css - basic CSS required for Appleseed
- as-admin-bar.css - CSS for the Admin Bar
- jquery-ui-1.9.2.custom.css - CSS for dialog boxes and other UI elements

/css - CSS files specific to the theme should be in this folder

Responsive design should be handle by the latest boostrap,css file. 
Menu Design should be handles by the main theme CSS. 


Setting/Switching Global Themes / Layouts
-----------------------
Global Layouts and Themes for the whole site can be set or switched on the Site Settings page from the **Site Manager** dropdown in the top Admin Menu. Under the **Theme and layout setting**” tab, there are fields for **Page Layout** and **Theme** with dropdown menu arrows on the right, so you can choose from those available.

.. image:: ../images/site-settings-screenshot.jpg

Page Themes / Layouts
---------------------
Individual pages can also be set to a layout or theme different from those of the Site default. 
For example one or more pages may wish to have a different panes layout from that of the Home page. Setting up such a child layout has been described above. The layout or theme for a page can be changed by clicking on the **Edit This Page** button in the top Admin Menu, then selecting the **Page Settings** tab. Similar to above, under the **Theme and layout setting**” tab, there are fields for **Custom Layout** and ** Custom Theme** with dropdown menu arrows on the right, so you can choose from those available. 

