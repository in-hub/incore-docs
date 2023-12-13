
.. _object_HttpServerRoute:


:index:`HttpServerRoute`
------------------------

Description
***********



:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`asynchronous <property_HttpServerRoute_asynchronous>`
  * :ref:`method <property_HttpServerRoute_method>`
  * :ref:`path <property_HttpServerRoute_path>`
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

  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_HttpServerRoute_asynchronous:

.. _signal_HttpServerRoute_asynchronousChanged:

.. index::
   single: asynchronous

asynchronous
++++++++++++

This property holds the whether the route is being handled asynchronuously, i.e. the handler method receives a :ref:`HttpServerResponder <object_HttpServerResponder>` in the second parameter (first is the request) and has to send the response manually.

:**› Type**: Boolean
:**› Signal**: asynchronousChanged()
:**› Attributes**: Writable


.. _property_HttpServerRoute_method:

.. _signal_HttpServerRoute_methodChanged:

.. index::
   single: method

method
++++++

This property holds the HTTP method which the route should handle.

:**› Type**: :ref:`HttpServerRequest.Method <enum_HttpServerRequest_Method>`
:**› Signal**: methodChanged()
:**› Attributes**: Writable


.. _property_HttpServerRoute_path:

.. _signal_HttpServerRoute_pathChanged:

.. index::
   single: path

path
++++

This property holds the path which the route should handle.

:**› Type**: String
:**› Signal**: pathChanged()
:**› Attributes**: Writable

Example
*******
See :ref:`HttpServer example <example_HttpServer>` on how to use HttpServerRoute.
