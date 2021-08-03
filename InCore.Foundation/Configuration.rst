
.. _object_Configuration:


:index:`Configuration`
----------------------

Description
***********

The Configuration object is used as a base class of other configuration objects. Mostly it is used to generate a custom configuration group in the configuration tab of the fluentum dashboard. Also it saves the settings taken.

:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`ApplicationConfiguration <object_ApplicationConfiguration>`, :ref:`NetworkConfiguration <object_NetworkConfiguration>`, :ref:`SystemConfiguration <object_SystemConfiguration>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`error <property_Configuration_error>`
  * :ref:`errorString <property_Configuration_errorString>`
  * :ref:`name <property_Configuration_name>`
  * :ref:`objects <property_Configuration_objects>`
  * :ref:`saveMode <property_Configuration_saveMode>`
  * :ref:`storage <property_Configuration_storage>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`load() <method_Configuration_load>`
  * :ref:`save() <method_Configuration_save>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`aboutToBeUpdated() <signal_Configuration_aboutToBeUpdated>`
  * :ref:`errorOccurred() <signal_Configuration_errorOccurred>`
  * :ref:`objectsDataChanged() <signal_Configuration_objectsDataChanged>`
  * :ref:`updated() <signal_Configuration_updated>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_Configuration_Error>`
  * :ref:`SaveMode <enum_Configuration_SaveMode>`



Properties
**********


.. _property_Configuration_error:

.. _signal_Configuration_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`Configuration.NoError <enumitem_Configuration_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_Configuration_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_Configuration_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_Configuration_errorString:

.. _signal_Configuration_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_Configuration_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_Configuration_name:

.. _signal_Configuration_nameChanged:

.. index::
   single: name

name
++++

This property holds the name property which usually is used as headline in the configuration tab of fluentum.

:**› Type**: String
:**› Signal**: nameChanged()
:**› Attributes**: Writable


.. _property_Configuration_objects:

.. _signal_Configuration_objectsChanged:

.. index::
   single: objects

objects
+++++++

This property holds a list of :ref:`ConfigurationObject <object_ConfigurationObject>` objects which should be saved.

:**› Type**: :ref:`List <object_List>`\<:ref:`ConfigurationObject <object_ConfigurationObject>`>
:**› Signal**: objectsChanged()
:**› Attributes**: Readonly


.. _property_Configuration_saveMode:

.. _signal_Configuration_saveModeChanged:

.. index::
   single: saveMode

saveMode
++++++++

This property holds the save mode of this configuration.

:**› Type**: :ref:`SaveMode <enum_Configuration_SaveMode>`
:**› Default**: :ref:`Configuration.SaveOnUpdate <enumitem_Configuration_SaveOnUpdate>`
:**› Signal**: saveModeChanged()
:**› Attributes**: Writable


.. _property_Configuration_storage:

.. _signal_Configuration_storageChanged:

.. index::
   single: storage

storage
+++++++

This property holds the :ref:`Storage <object_Storage>` where the configuration will be saved.

:**› Type**: :ref:`Storage <object_Storage>`
:**› Signal**: storageChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_Configuration_load:

.. index::
   single: load

load()
++++++

This method loads the configuration from configured :ref:`storage <property_Configuration_storage>`.



.. _method_Configuration_save:

.. index::
   single: save

save()
++++++

This method saves the configuration to the configured :ref:`storage <property_Configuration_storage>`.


Signals
*******


.. _signal_Configuration_aboutToBeUpdated:

.. index::
   single: aboutToBeUpdated

aboutToBeUpdated()
++++++++++++++++++

This signal is emitted before the configuration is being updated through object deserialization, e.g. when using in conjunction with an :ref:`JsonRpcService <object_JsonRpcService>` and loading settings through RPC calls.



.. _signal_Configuration_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_Configuration_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_Configuration_error>` property this signal is also emitted several times if a certain error occurs several times in succession.



.. _signal_Configuration_objectsDataChanged:

.. index::
   single: objectsDataChanged

objectsDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`objects <property_Configuration_objects>` list itself emitted the dataChanged() signal.



.. _signal_Configuration_updated:

.. index::
   single: updated

updated()
+++++++++

This signal is emitted after the configuration has been updated through object deserialization, e.g. when using in conjunction with an :ref:`JsonRpcService <object_JsonRpcService>` and loading settings through RPC calls.


Enumerations
************


.. _enum_Configuration_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in Configuration objects. The most recently occurred error is stored in the :ref:`error <property_Configuration_error>` property.

.. index::
   single: Configuration.NoError
.. index::
   single: Configuration.ConfigurationFileReadError
.. index::
   single: Configuration.ConfigurationFileWriteError
.. index::
   single: Configuration.ConfigurationFileParseError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_Configuration_NoError:
  * - ``Configuration.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_Configuration_ConfigurationFileReadError:
  * - ``Configuration.ConfigurationFileReadError``
    - ``1``
    - Could not open configuration file for reading.

      .. _enumitem_Configuration_ConfigurationFileWriteError:
  * - ``Configuration.ConfigurationFileWriteError``
    - ``2``
    - Could not open configuration file for writing.

      .. _enumitem_Configuration_ConfigurationFileParseError:
  * - ``Configuration.ConfigurationFileParseError``
    - ``3``
    - Could not parse configuration file.


.. _enum_Configuration_SaveMode:

.. index::
   single: SaveMode

SaveMode
++++++++

This enumeration describes when and under which circumstances the configuration is saved to the configured :ref:`storage <property_Configuration_storage>`.

.. index::
   single: Configuration.SaveManually
.. index::
   single: Configuration.SaveOnUpdate
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_Configuration_SaveManually:
  * - ``Configuration.SaveManually``
    - ``0``
    - Save configuration manually whenever :ref:`save() <method_Configuration_save>` is called.

      .. _enumitem_Configuration_SaveOnUpdate:
  * - ``Configuration.SaveOnUpdate``
    - ``1``
    - Save configuration whenever settings are updated through property deserialization.

