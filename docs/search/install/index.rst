Appleseed Search Installation
=============================


Quick Install
-------------

Root Page for Installation instructions for Appleseed Search

Appleseed Search Web User Installation and Customization on Appleseed Portal.

If you have not already installed Appleseed Portal, refer to the instructions here  `<http://learn.appleseedapp.net/en/latest/docs/Portal/install/#quick-install>`_

* Steps to set up Angular Search Interface on an Appleseed Site.

   * Open a code editor (such as Visual Studio 2015, or another compatible version).
   * Go to the folder in which you installed Appleseed 
   
     * Navigate to ...\Appleseed\Design\DesktopLayouts\[Theme used]\DesktopPortalBanner.ascx
     * Make sure you choose the file in the folder for the theme used not the one directly in the .\Appleseed\Design\DesktopLayouts\ folder
     * add the Following script:
     
       // Add attributes to html element for Angular Search
       
         $("html").attr({
         
              "xmlns":"http://angularjs.org",
              
              "id":"ng-app",
              
              "ng-app":"solr-ajax"
              
          });

       .. image:: ../images/Script-Update.PNG

     * Verify that the script is working.
     
       * Navigate to the Appleseed portal page.
       * Right click and click inspect elements. 
       * Check if the code has been added to the <html> element

       


