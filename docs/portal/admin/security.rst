Secure Appleseed Portal
=========================

Below are options that Administrators can use to secure Appleseed Portal

HTTPS Security
---------------------

* Install URL Redirect 2.0
* Add the below rule to your web.config <system.webserver> node

.. code-block:: guess
    <rule name="Redirect to HTTPS">
        <match url="(.*)" />
        <conditions>
            <add input="{HTTPS}" pattern="OFF"/>
        </conditions>
        <action type="Redirect" url="https://{HTTP_HOST}{HTTP_URL}" redirectType="Permanent" appendQueryString="false" />
    </rule>


.. toctree::
    :titlesonly:
