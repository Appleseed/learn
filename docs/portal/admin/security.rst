.. toctree::
   :titlesonly:
   
=========================
Secure Appleseed Portal
=========================

Below are options that Administrators can use to secure Appleseed Portal

HTTPS Security
---------------------

* Install your SSL Certification to your web server
* For IIS Installations, Let's Encrypt is highly recommended 
* Make sure at least one SSL cert is installed on your site domain
* Install URL Redirect 2.0 for enforcing SSL redirection 
* Add the below rule to your web.config <system.webserver> node
* Browse your site domain and test to see if the redirect happens

.. code-block:: guess

    <rule name="Redirect to HTTPS">
        <match url="(.*)" />
        <conditions>
            <add input="{HTTPS}" pattern="OFF"/>
        </conditions>
        <action type="Redirect" url="https://{HTTP_HOST}{HTTP_URL}" redirectType="Permanent" appendQueryString="false" />
    </rule>



To- Do :

Add information on common problems with SSL Especially Lets Encrypt
Add information by Verfying in IIS SSL Common issues
    Add scenario where certification expires and then lest encrypt cannot reach out to the certification server.  Therefore portal will appear down if https is being forced.

.. toctree::
    :titlesonly:

.. include:: /./common.txt
