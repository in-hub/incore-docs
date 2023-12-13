
.. _object_HttpServer:


:index:`HttpServer`
-------------------

Description
***********



This object was introduced in InCore 2.8.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`error <property_HttpServer_error>`
  * :ref:`errorString <property_HttpServer_errorString>`
  * :ref:`localHost <property_HttpServer_localHost>`
  * :ref:`port <property_HttpServer_port>`
  * :ref:`routes <property_HttpServer_routes>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_HttpServer_errorOccurred>`
  * :ref:`routesDataChanged() <signal_HttpServer_routesDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_HttpServer_Error>`



Properties
**********


.. _property_HttpServer_error:

.. _signal_HttpServer_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`HttpServer.NoError <enumitem_HttpServer_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_HttpServer_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_HttpServer_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_HttpServer_errorString:

.. _signal_HttpServer_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_HttpServer_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_HttpServer_localHost:

.. _signal_HttpServer_localHostChanged:

.. index::
   single: localHost

localHost
+++++++++

This property holds whether the server should listen for incoming connections on the local loopback interface only. If set to ``true`` the server will not be reachable by other hosts on the network but internal clients such as docker containers (:ref:`DockerContainer <object_DockerContainer>`) only.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: localHostChanged()
:**› Attributes**: Writable


.. _property_HttpServer_port:

.. _signal_HttpServer_portChanged:

.. index::
   single: port

port
++++

This property holds the port which to listen at.

:**› Type**: SignedInteger
:**› Default**: ``80``
:**› Signal**: portChanged()
:**› Attributes**: Writable


.. _property_HttpServer_routes:

.. _signal_HttpServer_routesChanged:

.. index::
   single: routes

routes
++++++

This property holds a list of header objects to use when sending a HTTP request.

:**› Type**: :ref:`List <object_List>`\<:ref:`HttpServerRoute <object_HttpServerRoute>`>
:**› Signal**: routesChanged()
:**› Attributes**: Readonly

Signals
*******


.. _signal_HttpServer_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_HttpServer_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_HttpServer_error>` property this signal is also emitted several times if a certain error occurs several times in succession.



.. _signal_HttpServer_routesDataChanged:

.. index::
   single: routesDataChanged

routesDataChanged(SignedInteger index)
++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`routes <property_HttpServer_routes>` list itself emitted the dataChanged() signal.


Enumerations
************


.. _enum_HttpServer_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in HttpServer objects. The most recently occurred error is stored in the :ref:`error <property_HttpServer_error>` property.

.. index::
   single: HttpServer.NoError
.. index::
   single: HttpServer.ListenError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_HttpServer_NoError:
  * - ``HttpServer.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_HttpServer_ListenError:
  * - ``HttpServer.ListenError``
    - ``1``
    - Failed to listen at the specified port.

