
.. _object_CloudOfThingsDeviceManager:


:index:`CloudOfThingsDeviceManager`
-----------------------------------

Description
***********

The CloudOfThingsDeviceManager object communicates with the Cloud of Things and handles commands from the cloud. The :ref:`updateRepositoryUrl <property_CloudOfThingsDeviceManager_updateRepositoryUrl>` property is updated when the corresponding command is send from the cloud. The :ref:`updateManager <property_CloudOfThingsDeviceManager_updateManager>` property will receive calls to :ref:`UpdateManager.check() <method_UpdateManager_check>`, :ref:`UpdateManager.download() <method_UpdateManager_download>` and :ref:`UpdateManager.install() <method_UpdateManager_install>` from the cloud.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`error <property_CloudOfThingsDeviceManager_error>`
  * :ref:`errorString <property_CloudOfThingsDeviceManager_errorString>`
  * :ref:`updateManager <property_CloudOfThingsDeviceManager_updateManager>`
  * :ref:`updateRepositoryUrl <property_CloudOfThingsDeviceManager_updateRepositoryUrl>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_CloudOfThingsDeviceManager_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_CloudOfThingsDeviceManager_Error>`



Properties
**********


.. _property_CloudOfThingsDeviceManager_error:

.. _signal_CloudOfThingsDeviceManager_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`CloudOfThingsDeviceManager.NoError <enumitem_CloudOfThingsDeviceManager_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_CloudOfThingsDeviceManager_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_CloudOfThingsDeviceManager_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_CloudOfThingsDeviceManager_errorString:

.. _signal_CloudOfThingsDeviceManager_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_CloudOfThingsDeviceManager_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_CloudOfThingsDeviceManager_updateManager:

.. _signal_CloudOfThingsDeviceManager_updateManagerChanged:

.. index::
   single: updateManager

updateManager
+++++++++++++

This property holds the :ref:`UpdateManager <object_UpdateManager>` which methods :ref:`UpdateManager.check() <method_UpdateManager_check>`, :ref:`UpdateManager.download() <method_UpdateManager_download>` and :ref:`UpdateManager.install() <method_UpdateManager_install>` are used to update the device if the process is started in the Cloud of Things.

:**› Type**: :ref:`UpdateManager <object_UpdateManager>`
:**› Signal**: updateManagerChanged()
:**› Attributes**: Writable


.. _property_CloudOfThingsDeviceManager_updateRepositoryUrl:

.. _signal_CloudOfThingsDeviceManager_updateRepositoryUrlChanged:

.. index::
   single: updateRepositoryUrl

updateRepositoryUrl
+++++++++++++++++++

This property holds the URL string to the repository which should be used to update the device. This property will be updated by a command from Cloud of Things and should be assigned to a :ref:`HttpRepository <object_HttpRepository>` in the :ref:`updateManager <property_CloudOfThingsDeviceManager_updateManager>` property.

:**› Type**: String
:**› Signal**: updateRepositoryUrlChanged()
:**› Attributes**: Readonly

Signals
*******


.. _signal_CloudOfThingsDeviceManager_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_CloudOfThingsDeviceManager_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_CloudOfThingsDeviceManager_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_CloudOfThingsDeviceManager_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in CloudOfThingsDeviceManager objects. The most recently occurred error is stored in the :ref:`error <property_CloudOfThingsDeviceManager_error>` property.

.. index::
   single: CloudOfThingsDeviceManager.NoError
.. index::
   single: CloudOfThingsDeviceManager.InvalidClient
.. index::
   single: CloudOfThingsDeviceManager.InvalidUpdateManager
.. index::
   single: CloudOfThingsDeviceManager.MultipleDeviceManagers
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_CloudOfThingsDeviceManager_NoError:
  * - ``CloudOfThingsDeviceManager.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_CloudOfThingsDeviceManager_InvalidClient:
  * - ``CloudOfThingsDeviceManager.InvalidClient``
    - ``1``
    - Parent is not an CloudOfThingsClient object.

      .. _enumitem_CloudOfThingsDeviceManager_InvalidUpdateManager:
  * - ``CloudOfThingsDeviceManager.InvalidUpdateManager``
    - ``2``
    - No UpdateManager set or found.

      .. _enumitem_CloudOfThingsDeviceManager_MultipleDeviceManagers:
  * - ``CloudOfThingsDeviceManager.MultipleDeviceManagers``
    - ``3``
    - Multiple CloudOfThingsDeviceManagers found.


.. _example_CloudOfThingsDeviceManager:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    import InCore.CloudOfThings 2.0
    import InCore.Http 2.0
    
    Application {
    
        CloudOfThingsClient {
            id: client
            tenant: "mustercloud"
            transport {
                protocol: CloudOfThingsTransport.MQTT
                tenantForMQTT: "nb-iot"
    
                requestOperationsIntervalMQTT: 5 * 1000
    
                //log important state changes
                onConnected: console.log( "Cloud of Things client connected" )
                onErrorChanged: console.log( "oh... error occurred", errorString )
            }
    
            registrator {
                isRegistered: true
                password: "y0urAwes@meP4ssword"
            }
    
            CloudOfThingsDeviceManager {
                id: deviceManager
    
                updateManager: UpdateManager {
    
                    // use this configuration to update incremental via Cloud of Things
                    // else set all to true
                    autoInstall: false
                    autoDownload: false
                    autoReboot: true
    
                    repositories: [
                        HttpRepository { url: deviceManager.updateRepositoryUrl }
                    ]
    
                    UpdateTarget {
                        bundlePrefix: "siineos"
                        currentVersion: system.osVersion
                    }
                }
            }
    
            //do your stuff here
            /*
            CloudOfThingsMeasurementWriter
            {
                ...
            }
            */
        }
    }
    