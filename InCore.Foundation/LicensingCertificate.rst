
.. _object_LicensingCertificate:


:index:`LicensingCertificate`
-----------------------------

Description
***********

The LicensingCertificate object is a specialized version of :ref:`DataObjectView <object_DataObjectView>` with additional properties for :ref:`Measurement <object_Measurement>` objects.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`data <property_LicensingCertificate_data>`
  * :ref:`deviceId <property_LicensingCertificate_deviceId>`
  * :ref:`expiryDate <property_LicensingCertificate_expiryDate>`
  * :ref:`id <property_LicensingCertificate_id>`
  * :ref:`issueDate <property_LicensingCertificate_issueDate>`
  * :ref:`licensee <property_LicensingCertificate_licensee>`
  * :ref:`productName <property_LicensingCertificate_productName>`
  * :ref:`valid <property_LicensingCertificate_valid>`
  * :ref:`version <property_LicensingCertificate_version>`
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


.. _property_LicensingCertificate_data:

.. _signal_LicensingCertificate_dataChanged:

.. index::
   single: data

data
++++

This property holds the license certificate data.

:**› Type**: String
:**› Signal**: dataChanged()
:**› Attributes**: Writable


.. _property_LicensingCertificate_deviceId:

.. _signal_LicensingCertificate_deviceIdChanged:

.. index::
   single: deviceId

deviceId
++++++++



:**› Type**: String
:**› Signal**: deviceIdChanged()
:**› Attributes**: Readonly


.. _property_LicensingCertificate_expiryDate:

.. _signal_LicensingCertificate_expiryDateChanged:

.. index::
   single: expiryDate

expiryDate
++++++++++



:**› Type**: DateTime
:**› Signal**: expiryDateChanged()
:**› Attributes**: Readonly


.. _property_LicensingCertificate_id:

.. _signal_LicensingCertificate_idChanged:

.. index::
   single: id

id
++



:**› Type**: String
:**› Signal**: idChanged()
:**› Attributes**: Readonly


.. _property_LicensingCertificate_issueDate:

.. _signal_LicensingCertificate_issueDateChanged:

.. index::
   single: issueDate

issueDate
+++++++++



:**› Type**: DateTime
:**› Signal**: issueDateChanged()
:**› Attributes**: Readonly


.. _property_LicensingCertificate_licensee:

.. _signal_LicensingCertificate_licenseeChanged:

.. index::
   single: licensee

licensee
++++++++



:**› Type**: String
:**› Signal**: licenseeChanged()
:**› Attributes**: Readonly


.. _property_LicensingCertificate_productName:

.. _signal_LicensingCertificate_productNameChanged:

.. index::
   single: productName

productName
+++++++++++



:**› Type**: String
:**› Signal**: productNameChanged()
:**› Attributes**: Readonly


.. _property_LicensingCertificate_valid:

.. _signal_LicensingCertificate_validChanged:

.. index::
   single: valid

valid
+++++



:**› Type**: Boolean
:**› Signal**: validChanged()
:**› Attributes**: Readonly


.. _property_LicensingCertificate_version:

.. _signal_LicensingCertificate_versionChanged:

.. index::
   single: version

version
+++++++



:**› Type**: SignedInteger
:**› Signal**: versionChanged()
:**› Attributes**: Readonly

