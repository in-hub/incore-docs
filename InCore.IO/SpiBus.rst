
.. _object_SpiBus:


:index:`SpiBus`
---------------

Description
***********

The SpiBus object represents an SPI bus with attached :ref:`SpiDevice <object_SpiDevice>` objects. This abstract base object provides common properties and methods only. Use a dedicated SPI bus implementation such as :ref:`SystemSpiBus <object_SystemSpiBus>`.

This object was introduced in InCore 2.8.

:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`SystemSpiBus <object_SystemSpiBus>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`bitsPerWord <property_SpiBus_bitsPerWord>`
  * :ref:`devices <property_SpiBus_devices>`
  * :ref:`mode <property_SpiBus_mode>`
  * :ref:`speed <property_SpiBus_speed>`
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

  * :ref:`devicesDataChanged() <signal_SpiBus_devicesDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Mode <enum_SpiBus_Mode>`



Properties
**********


.. _property_SpiBus_bitsPerWord:

.. _signal_SpiBus_bitsPerWordChanged:

.. index::
   single: bitsPerWord

bitsPerWord
+++++++++++

This property holds the number of bits per word to use for transfers on the bus.

:**› Type**: SignedInteger
:**› Default**: ``16``
:**› Signal**: bitsPerWordChanged()
:**› Attributes**: Writable


.. _property_SpiBus_devices:

.. _signal_SpiBus_devicesChanged:

.. index::
   single: devices

devices
+++++++

This property holds a list of Spi devices to use on this bus.

:**› Type**: :ref:`List <object_List>`\<:ref:`SpiDevice <object_SpiDevice>`>
:**› Signal**: devicesChanged()
:**› Attributes**: Readonly


.. _property_SpiBus_mode:

.. _signal_SpiBus_modeChanged:

.. index::
   single: mode

mode
++++

This property holds the SPI mode to use for transfers on the bus.

:**› Type**: :ref:`Mode <enum_SpiBus_Mode>`
:**› Default**: :ref:`SpiBus.Mode0 <enumitem_SpiBus_Mode0>`
:**› Signal**: modeChanged()
:**› Attributes**: Writable


.. _property_SpiBus_speed:

.. _signal_SpiBus_speedChanged:

.. index::
   single: speed

speed
+++++

This property holds the desired communication speed in *Hz*.

:**› Type**: UnsignedInteger
:**› Default**: ``1000000``
:**› Signal**: speedChanged()
:**› Attributes**: Writable

Signals
*******


.. _signal_SpiBus_devicesDataChanged:

.. index::
   single: devicesDataChanged

devicesDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`devices <property_SpiBus_devices>` list itself emitted the dataChanged() signal.


Enumerations
************


.. _enum_SpiBus_Mode:

.. index::
   single: Mode

Mode
++++



.. index::
   single: SpiBus.Mode0
.. index::
   single: SpiBus.Mode1
.. index::
   single: SpiBus.Mode2
.. index::
   single: SpiBus.Mode3
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_SpiBus_Mode0:
  * - ``SpiBus.Mode0``
    - ``0``
    - 

      .. _enumitem_SpiBus_Mode1:
  * - ``SpiBus.Mode1``
    - ``1``
    - 

      .. _enumitem_SpiBus_Mode2:
  * - ``SpiBus.Mode2``
    - ``2``
    - 

      .. _enumitem_SpiBus_Mode3:
  * - ``SpiBus.Mode3``
    - ``3``
    - 
