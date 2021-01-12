
.. _object_HttpRepository:


:index:`HttpRepository`
-----------------------

Description
***********

The HttpRepository object provides a specialized :ref:`Repository <object_Repository>` object for fetching resources from HTTP servers. In combination with an :ref:`UpdateManager <object_UpdateManager>` it can be used to implement online updates mechanisms. See the :ref:`UpdateManager example <example_UpdateManager>` for details.

:**› Inherits**: :ref:`Repository <object_Repository>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`timeout <property_HttpRepository_timeout>`
  * :ref:`url <property_HttpRepository_url>`
  * :ref:`Repository.error <property_Repository_error>`
  * :ref:`Repository.errorString <property_Repository_errorString>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`Repository.errorOccurred() <signal_Repository_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Repository.Error <enum_Repository_Error>`



Properties
**********


.. _property_HttpRepository_timeout:

.. _signal_HttpRepository_timeoutChanged:

.. index::
   single: timeout

timeout
+++++++

This property holds the timeout for HTTP responses (i.e. complete file downloads).

:**› Type**: SignedInteger
:**› Signal**: timeoutChanged()
:**› Attributes**: Writable


.. _property_HttpRepository_url:

.. _signal_HttpRepository_urlChanged:

.. index::
   single: url

url
+++

This property holds the URL of the HTTP repository.

:**› Type**: String
:**› Signal**: urlChanged()
:**› Attributes**: Writable


.. _example_HttpRepository:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    import InCore.Http 2.0
    
    Application {
    
        UpdateManager {
            repositories: [
                HttpRepository {
                    url: "https://updates.inhub.de"
                }
            ]
        }
    
    }
    