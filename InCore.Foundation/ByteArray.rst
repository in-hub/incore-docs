
.. _object_ByteArray:


:index:`ByteArray`
------------------

Description
***********

The ByteArray object is used to store and transport binary data and convert it to/from various representations easily. Whenever one of the :ref:`data <property_ByteArray_data>`, :ref:`arrayBuffer <property_ByteArray_arrayBuffer>` or :ref:`string <property_ByteArray_string>` property is changed the other properties are updated automatically.

This object was introduced in InCore 2.0.

:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`Resource <object_Resource>`, :ref:`UdpDatagram <object_UdpDatagram>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`arrayBuffer <property_ByteArray_arrayBuffer>`
  * :ref:`base64 <property_ByteArray_base64>`
  * :ref:`data <property_ByteArray_data>`
  * :ref:`hex <property_ByteArray_hex>`
  * :ref:`string <property_ByteArray_string>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`remove() <method_ByteArray_remove>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_ByteArray_arrayBuffer:

.. _signal_ByteArray_arrayBufferChanged:

.. index::
   single: arrayBuffer

arrayBuffer
+++++++++++

This property holds the binary data as a JS ``ArrayBuffer`` object.

:**› Type**: ArrayBuffer
:**› Signal**: arrayBufferChanged()
:**› Attributes**: Writable


.. _property_ByteArray_base64:

.. _signal_ByteArray_base64Changed:

.. index::
   single: base64

base64
++++++

This property holds the base64 encoded representation of the binary data, e.g. ``SW5Db3JlIGlzIGdyZWF0IQ==``.

:**› Type**: String
:**› Signal**: base64Changed()
:**› Attributes**: Writable


.. _property_ByteArray_data:

.. _signal_ByteArray_dataChanged:

.. index::
   single: data

data
++++

This property holds the individual bytes as a JS value list, e.g. ``[0xaf, 0xfe, 0xd0, 0x0f]``.

:**› Type**: Variant
:**› Signal**: dataChanged()
:**› Attributes**: Writable


.. _property_ByteArray_hex:

.. _signal_ByteArray_hexChanged:

.. index::
   single: hex

hex
+++

This property holds the hexadecimal encoded representation of the binary data, e.g. ``badc0ded``.

:**› Type**: String
:**› Signal**: hexChanged()
:**› Attributes**: Writable


.. _property_ByteArray_string:

.. _signal_ByteArray_stringChanged:

.. index::
   single: string

string
++++++

This property holds the binary data encoded as an UTF-8 string.

:**› Type**: String
:**› Signal**: stringChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_ByteArray_remove:

.. index::
   single: remove

remove(SignedInteger position, SignedInteger length)
++++++++++++++++++++++++++++++++++++++++++++++++++++

This method removes ``length`` bytes starting at index ``position``. To remove the first ``length`` bytes (e.g. after processing this part of a buffer), pass ``0`` for ``position``.


