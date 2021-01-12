
.. _object_UpdateManager:


:index:`UpdateManager`
----------------------

Description
***********

The UpdateManager object provides functions and properties for querying and installing system updates.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`autoDownload <property_UpdateManager_autoDownload>`
  * :ref:`autoInstall <property_UpdateManager_autoInstall>`
  * :ref:`autoReboot <property_UpdateManager_autoReboot>`
  * :ref:`checkInterval <property_UpdateManager_checkInterval>`
  * :ref:`downloadStorage <property_UpdateManager_downloadStorage>`
  * :ref:`error <property_UpdateManager_error>`
  * :ref:`errorData <property_UpdateManager_errorData>`
  * :ref:`errorString <property_UpdateManager_errorString>`
  * :ref:`pendingUpdates <property_UpdateManager_pendingUpdates>`
  * :ref:`progress <property_UpdateManager_progress>`
  * :ref:`repositories <property_UpdateManager_repositories>`
  * :ref:`targets <property_UpdateManager_targets>`
  * :ref:`updatesAvailable <property_UpdateManager_updatesAvailable>`
  * :ref:`updatesReady <property_UpdateManager_updatesReady>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`check() <method_UpdateManager_check>`
  * :ref:`download() <method_UpdateManager_download>`
  * :ref:`install() <method_UpdateManager_install>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_UpdateManager_errorOccurred>`
  * :ref:`repositoriesDataChanged() <signal_UpdateManager_repositoriesDataChanged>`
  * :ref:`targetsDataChanged() <signal_UpdateManager_targetsDataChanged>`
  * :ref:`updatesInstalled() <signal_UpdateManager_updatesInstalled>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_UpdateManager_Error>`



Properties
**********


.. _property_UpdateManager_autoDownload:

.. _signal_UpdateManager_autoDownloadChanged:

.. index::
   single: autoDownload

autoDownload
++++++++++++

This property holds whether to automatically download available updates.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: autoDownloadChanged()
:**› Attributes**: Writable


.. _property_UpdateManager_autoInstall:

.. _signal_UpdateManager_autoInstallChanged:

.. index::
   single: autoInstall

autoInstall
+++++++++++

This property holds whether to automatically install downloaded updates.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: autoInstallChanged()
:**› Attributes**: Writable


.. _property_UpdateManager_autoReboot:

.. _signal_UpdateManager_autoRebootChanged:

.. index::
   single: autoReboot

autoReboot
++++++++++

This property holds whether to automatically reboot the system after installing updates.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: autoRebootChanged()
:**› Attributes**: Writable


.. _property_UpdateManager_checkInterval:

.. _signal_UpdateManager_checkIntervalChanged:

.. index::
   single: checkInterval

checkInterval
+++++++++++++

This property holds the interval in milliseconds in which to check the configured repositories for updates. The minimum value is ``5000``.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: checkIntervalChanged()
:**› Attributes**: Writable


.. _property_UpdateManager_downloadStorage:

.. _signal_UpdateManager_downloadStorageChanged:

.. index::
   single: downloadStorage

downloadStorage
+++++++++++++++

This property holds a storage location for storing downloaded update files.

:**› Type**: :ref:`Storage <object_Storage>`
:**› Signal**: downloadStorageChanged()
:**› Attributes**: Readonly


.. _property_UpdateManager_error:

.. _signal_UpdateManager_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`UpdateManager.NoError <enumitem_UpdateManager_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_UpdateManager_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_UpdateManager_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_UpdateManager_errorData:

.. _signal_UpdateManager_errorDataChanged:

.. index::
   single: errorData

errorData
+++++++++

This property holds additional information on errors occurred while checking, downloading or installing updates.

:**› Type**: String
:**› Signal**: errorDataChanged()
:**› Attributes**: Readonly


.. _property_UpdateManager_errorString:

.. _signal_UpdateManager_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_UpdateManager_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_UpdateManager_pendingUpdates:

.. _signal_UpdateManager_pendingUpdatesChanged:

.. index::
   single: pendingUpdates

pendingUpdates
++++++++++++++

This property holds the list of available updates pending for installation.

:**› Type**: StringList
:**› Signal**: pendingUpdatesChanged()
:**› Attributes**: Readonly


.. _property_UpdateManager_progress:

.. _signal_UpdateManager_progressChanged:

.. index::
   single: progress

progress
++++++++

This property holds the progress of the current operation.

:**› Type**: SignedInteger
:**› Signal**: progressChanged()
:**› Attributes**: Readonly


.. _property_UpdateManager_repositories:

.. _signal_UpdateManager_repositoriesChanged:

.. index::
   single: repositories

repositories
++++++++++++

This property holds a list of repositories where to retrieve update bundles from.

:**› Type**: :ref:`List <object_List>`\<:ref:`Repository <object_Repository>`>
:**› Signal**: repositoriesChanged()
:**› Attributes**: Readonly


.. _property_UpdateManager_targets:

.. _signal_UpdateManager_targetsChanged:

.. index::
   single: targets

targets
+++++++

This property holds a list of targets which to install updates for.

:**› Type**: :ref:`List <object_List>`\<:ref:`UpdateTarget <object_UpdateTarget>`>
:**› Signal**: targetsChanged()
:**› Attributes**: Readonly


.. _property_UpdateManager_updatesAvailable:

.. _signal_UpdateManager_updatesAvailableChanged:

.. index::
   single: updatesAvailable

updatesAvailable
++++++++++++++++

This property holds whether any updates are available in the configured repositories.

:**› Type**: Boolean
:**› Signal**: updatesAvailableChanged()
:**› Attributes**: Readonly


.. _property_UpdateManager_updatesReady:

.. _signal_UpdateManager_updatesReadyChanged:

.. index::
   single: updatesReady

updatesReady
++++++++++++

This property holds whether any updates have been downloaded and are ready to install.

:**› Type**: Boolean
:**› Signal**: updatesReadyChanged()
:**› Attributes**: Readonly

Methods
*******


.. _method_UpdateManager_check:

.. index::
   single: check

check()
+++++++

This method checks the configured repositories for updates by fetching corresponding update file lists. Returns ``true`` if at least one repository could be checked successfully. If :ref:`autoDownload <property_UpdateManager_autoDownload>` is set to ``true`` downloads will be started afterwards automatically. Otherwise call :ref:`download() <method_UpdateManager_download>` manually.

:**› Returns**: Boolean



.. _method_UpdateManager_download:

.. index::
   single: download

download()
++++++++++

This method initiates the download of available updates to the storage specified by :ref:`downloadStorage <property_UpdateManager_downloadStorage>`. Returns ``true`` if the downloads could be started successfully. Once all downloads are finished the :ref:`updatesReady <property_UpdateManager_updatesReady>` property changes to ``true`` and :ref:`pendingUpdates <property_UpdateManager_pendingUpdates>` is updated accordingly. If :ref:`autoInstall <property_UpdateManager_autoInstall>` is set to ``true`` all downloaded updates will be installed afterwards automatically. Otherwise call :ref:`install() <method_UpdateManager_install>` manually.

:**› Returns**: Boolean



.. _method_UpdateManager_install:

.. index::
   single: install

install()
+++++++++

This method initiates the installation of the downloaded updates. Returns ``true`` if at least one update is available for installation. Once all updates have been installed the :ref:`updatesInstalled() <signal_UpdateManager_updatesInstalled>` signal is emitted. If :ref:`autoReboot <property_UpdateManager_autoReboot>` is set to ``true`` the system is rebooted afterwards automatically.

:**› Returns**: Boolean


Signals
*******


.. _signal_UpdateManager_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_UpdateManager_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_UpdateManager_error>` property this signal is also emitted several times if a certain error occurs several times in succession.



.. _signal_UpdateManager_repositoriesDataChanged:

.. index::
   single: repositoriesDataChanged

repositoriesDataChanged(SignedInteger index)
++++++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`repositories <property_UpdateManager_repositories>` list itself emitted the dataChanged() signal.



.. _signal_UpdateManager_targetsDataChanged:

.. index::
   single: targetsDataChanged

targetsDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`targets <property_UpdateManager_targets>` list itself emitted the dataChanged() signal.



.. _signal_UpdateManager_updatesInstalled:

.. index::
   single: updatesInstalled

updatesInstalled()
++++++++++++++++++

This signal is emitted when one or multiple updates have been installed succesfully. This can be used to trigger further actions when :ref:`autoReboot <property_UpdateManager_autoReboot>` is set to ``false`` and the device keeps running after the update.


Enumerations
************


.. _enum_UpdateManager_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in UpdateManager objects. The most recently occurred error is stored in the :ref:`error <property_UpdateManager_error>` property.

.. index::
   single: UpdateManager.NoError
.. index::
   single: UpdateManager.MissingRepositories
.. index::
   single: UpdateManager.InvalidUpdateFile
.. index::
   single: UpdateManager.InstallationError
.. index::
   single: UpdateManager.InvalidDownloadStorage
.. index::
   single: UpdateManager.InsufficientDownloadStorage
.. index::
   single: UpdateManager.NoUpdatesAvailable
.. index::
   single: UpdateManager.NoUpdatesDownloaded
.. index::
   single: UpdateManager.DownloadFailed
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_UpdateManager_NoError:
  * - ``UpdateManager.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_UpdateManager_MissingRepositories:
  * - ``UpdateManager.MissingRepositories``
    - ``1``
    - No repositories specified.

      .. _enumitem_UpdateManager_InvalidUpdateFile:
  * - ``UpdateManager.InvalidUpdateFile``
    - ``2``
    - Update file is invalid or incompatible.

      .. _enumitem_UpdateManager_InstallationError:
  * - ``UpdateManager.InstallationError``
    - ``3``
    - An error occurred while installing an update.

      .. _enumitem_UpdateManager_InvalidDownloadStorage:
  * - ``UpdateManager.InvalidDownloadStorage``
    - ``4``
    - None or invalid download storage set.

      .. _enumitem_UpdateManager_InsufficientDownloadStorage:
  * - ``UpdateManager.InsufficientDownloadStorage``
    - ``5``
    - Insufficient space available on the download storage.

      .. _enumitem_UpdateManager_NoUpdatesAvailable:
  * - ``UpdateManager.NoUpdatesAvailable``
    - ``6``
    - Updates have not been checked or no updates are available for the configured targets.

      .. _enumitem_UpdateManager_NoUpdatesDownloaded:
  * - ``UpdateManager.NoUpdatesDownloaded``
    - ``7``
    - No updates have been downloaded for installation.

      .. _enumitem_UpdateManager_DownloadFailed:
  * - ``UpdateManager.DownloadFailed``
    - ``8``
    - Failed to download one or multiple updates.


.. _example_UpdateManager:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    import InCore.Http 2.0
    
    Application {
    
        id: app
        name: "update-manager-example"
        version: "0.1.0"
    
        UpdateManager {
            id: updateManager
            autoInstall: true
            onCompleted: check()
    
            repositories: [
                LocalRepository { storage: LocalStorage { } },
                UsbDriveRepository { storage.onAvailableChanged: updateManager.check() },
                HttpRepository { url: "http://download.inhub.de/siineos/updates/" }
            ]
    
            UpdateTarget {
                bundlePrefix: "siineos"
                currentVersion: system.osVersion
            }
    
            UpdateTarget {
                bundlePrefix: "example-app"
                currentVersion: app.version
            }
        }
    }
    