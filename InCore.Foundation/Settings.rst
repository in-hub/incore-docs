
.. _object_Settings:


:index:`Settings`
-----------------

Description
***********

The Settings object can be used to store settings nonvolatile.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`category <property_Settings_category>`
  * :ref:`saveInterval <property_Settings_saveInterval>`
  * :ref:`saveMode <property_Settings_saveMode>`
  * :ref:`storage <property_Settings_storage>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`load() <method_Settings_load>`
  * :ref:`save() <method_Settings_save>`
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

  * :ref:`SaveMode <enum_Settings_SaveMode>`



Properties
**********


.. _property_Settings_category:

.. _signal_Settings_categoryChanged:

.. index::
   single: category

category
++++++++

This property holds a custom string which is used to group settings properties. In a group each property name has to be unique, otherwise it would be overwritten.

:**› Type**: String
:**› Signal**: categoryChanged()
:**› Attributes**: Writable


.. _property_Settings_saveInterval:

.. _signal_Settings_saveIntervalChanged:

.. index::
   single: saveInterval

saveInterval
++++++++++++

This property holds the interval in which the settings are written to :ref:`storage <property_Settings_storage>` if :ref:`saveMode <property_Settings_saveMode>` is set to \enumitem{Settings:SaveMode::SavePeriodically}. Otherwise or if it is set to ``0`` this property does nothing.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: saveIntervalChanged()
:**› Attributes**: Writable


.. _property_Settings_saveMode:

.. _signal_Settings_saveModeChanged:

.. index::
   single: saveMode

saveMode
++++++++

This property holds the save mode which should be used.

:**› Type**: :ref:`SaveMode <enum_Settings_SaveMode>`
:**› Default**: :ref:`Settings.SaveManually <enumitem_Settings_SaveManually>`
:**› Signal**: saveModeChanged()
:**› Attributes**: Writable


.. _property_Settings_storage:

.. _signal_Settings_storageChanged:

.. index::
   single: storage

storage
+++++++

This property holds the storage where the data will be saved. If left blank a :ref:`LocalStorage <object_LocalStorage>` will be used.

:**› Type**: :ref:`Storage <object_Storage>`
:**› Signal**: storageChanged()
:**› Attributes**: Writable, Optional

Methods
*******


.. _method_Settings_load:

.. index::
   single: load

load()
++++++

This method loads all properties from the file and discard possible changes made.



.. _method_Settings_save:

.. index::
   single: save

save()
++++++

This method saves all properties in the corresponding :ref:`category <property_Settings_category>`


Enumerations
************


.. _enum_Settings_SaveMode:

.. index::
   single: SaveMode

SaveMode
++++++++

This enumeration describes all available save modes for the settings object.

.. index::
   single: Settings.SaveManually
.. index::
   single: Settings.SavePeriodically
.. index::
   single: Settings.SaveOnChange
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_Settings_SaveManually:
  * - ``Settings.SaveManually``
    - ``0``
    - save settings manually whenever save() is called.

      .. _enumitem_Settings_SavePeriodically:
  * - ``Settings.SavePeriodically``
    - ``1``
    - save settings periodically depending on :ref:`saveInterval <property_Settings_saveInterval>`.

      .. _enumitem_Settings_SaveOnChange:
  * - ``Settings.SaveOnChange``
    - ``2``
    - save settings whenever one or more settings have changed.


.. _example_Settings:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    
    Application {
    
        Settings {
            id: settings
    
            property bool updatesEnabled: true
            property int updateInterval: 100
            property var fileName: "file.csv"
            property var sensorNames: [
                "temp1",
                "temp2",
                "temp3"
            ]
            onCompleted: save();
        }
    
        CsvWriter {
            Repeater on objects {
                model: 3
                Measurement {
                    id: measurement
                    name: settings.sensorNames[index]
                    property var updateTimer : Timer {
                        interval: settings.updateInterval
                        running: settings.updatesEnabled
                        onTriggered: measurement.data = Math.random() * 100;
                    }
                }
            }
    
            output: File {
                fileName: settings.fileName
                storage: LocalStorage { }
                onErrorChanged: console.log(errorString)
            }
    
            outputMode: CsvWriter.OutputTruncate
            submitMode: CsvWriter.SubmitOnCompleteDataset
        }
    
    }
    