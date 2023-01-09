
.. _object_HttpContent:


:index:`HttpContent`
--------------------

Description
***********

The HttpContent object represents the content of a HTTP request or response which is sent to or received from a HTTP server.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`data <property_HttpContent_data>`
  * :ref:`type <property_HttpContent_type>`
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

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Type <enum_HttpContent_Type>`



Properties
**********


.. _property_HttpContent_data:

.. _signal_HttpContent_dataChanged:

.. index::
   single: data

data
++++

This property holds the actual data to send or which has been received. The data type depends on the format specified through the :ref:`type <property_HttpContent_type>` property. See the :ref:`HttpContent.Type <enum_HttpContent_Type>` enumeration for details.

:**› Type**: Variant
:**› Signal**: dataChanged()
:**› Attributes**: Writable


.. _property_HttpContent_type:

.. _signal_HttpContent_typeChanged:

.. index::
   single: type

type
++++

This property holds the type specifying in which format to send or receive data.

:**› Type**: :ref:`Type <enum_HttpContent_Type>`
:**› Default**: :ref:`HttpContent.PlainText <enumitem_HttpContent_PlainText>`
:**› Signal**: typeChanged()
:**› Attributes**: Writable

Enumerations
************


.. _enum_HttpContent_Type:

.. index::
   single: Type

Type
++++

This enumeration describes the type specifying in which format to send or receive data.

.. index::
   single: HttpContent.Unknown
.. index::
   single: HttpContent.PlainText
.. index::
   single: HttpContent.Binary
.. index::
   single: HttpContent.Json
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_HttpContent_Unknown:
  * - ``HttpContent.Unknown``
    - ``0``
    - 

      .. _enumitem_HttpContent_PlainText:
  * - ``HttpContent.PlainText``
    - ``1``
    - Send and receive data as plaintext.

      .. _enumitem_HttpContent_Binary:
  * - ``HttpContent.Binary``
    - ``2``
    - Send and receive data as raw bytes which can be accessed as an ``ArrayBuffer``.

      .. _enumitem_HttpContent_Json:
  * - ``HttpContent.Json``
    - ``3``
    - Send and receive data as JSON objects.

Example
*******
See :ref:`HttpHeader example <example_HttpHeader>` on how to use HttpContent.
