
.. _object_DockerContainer:


:index:`DockerContainer`
------------------------

Description
***********

The DockerContainer object represents a Docker container configuration and provides methods for starting/stopping and running/executing commands in the container. Its parent object has to be a :ref:`DockerService <object_DockerService>` which implements the required mechanisms for the container operations and initially starts all enabled containers.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`arguments <property_DockerContainer_arguments>`
  * :ref:`capAdd <property_DockerContainer_capAdd>`
  * :ref:`capDrop <property_DockerContainer_capDrop>`
  * :ref:`cleanUpAtExit <property_DockerContainer_cleanUpAtExit>`
  * :ref:`cleanUpAtStart <property_DockerContainer_cleanUpAtStart>`
  * :ref:`enabled <property_DockerContainer_enabled>`
  * :ref:`entryPoint <property_DockerContainer_entryPoint>`
  * :ref:`environment <property_DockerContainer_environment>`
  * :ref:`error <property_DockerContainer_error>`
  * :ref:`errorString <property_DockerContainer_errorString>`
  * :ref:`hostname <property_DockerContainer_hostname>`
  * :ref:`image <property_DockerContainer_image>`
  * :ref:`loggingDriver <property_DockerContainer_loggingDriver>`
  * :ref:`mounts <property_DockerContainer_mounts>`
  * :ref:`name <property_DockerContainer_name>`
  * :ref:`networkMode <property_DockerContainer_networkMode>`
  * :ref:`networks <property_DockerContainer_networks>`
  * :ref:`ports <property_DockerContainer_ports>`
  * :ref:`restartPolicy <property_DockerContainer_restartPolicy>`
  * :ref:`running <property_DockerContainer_running>`
  * :ref:`seccompProfile <property_DockerContainer_seccompProfile>`
  * :ref:`volumes <property_DockerContainer_volumes>`
  * :ref:`workingDirectory <property_DockerContainer_workingDirectory>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 2

  * :ref:`execute() <method_DockerContainer_execute>`
  * :ref:`pull() <method_DockerContainer_pull>`
  * :ref:`run() <method_DockerContainer_run>`
  * :ref:`start() <method_DockerContainer_start>`
  * :ref:`stop() <method_DockerContainer_stop>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_DockerContainer_errorOccurred>`
  * :ref:`mountsDataChanged() <signal_DockerContainer_mountsDataChanged>`
  * :ref:`networksDataChanged() <signal_DockerContainer_networksDataChanged>`
  * :ref:`volumesDataChanged() <signal_DockerContainer_volumesDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_DockerContainer_Error>`
  * :ref:`LoggingDriver <enum_DockerContainer_LoggingDriver>`
  * :ref:`NetworkMode <enum_DockerContainer_NetworkMode>`
  * :ref:`RestartPolicy <enum_DockerContainer_RestartPolicy>`



Properties
**********


.. _property_DockerContainer_arguments:

.. _signal_DockerContainer_argumentsChanged:

.. index::
   single: arguments

arguments
+++++++++

This property holds a list of arguments which to pass to the executable specified by :ref:`entryPoint <property_DockerContainer_entryPoint>`.

This property was introduced in InCore 2.6.

:**› Type**: StringList
:**› Signal**: argumentsChanged()
:**› Attributes**: Writable


.. _property_DockerContainer_capAdd:

.. _signal_DockerContainer_capAddChanged:

.. index::
   single: capAdd

capAdd
++++++

This property holds security-related capabilities which to add to the container, e.g. ``NET_ADMIN``.

This property was introduced in InCore 2.8.

:**› Type**: StringList
:**› Signal**: capAddChanged()
:**› Attributes**: Writable


.. _property_DockerContainer_capDrop:

.. _signal_DockerContainer_capDropChanged:

.. index::
   single: capDrop

capDrop
+++++++

This property holds security-related capabilities which to drop from the container, e.g. ``NET_ADMIN``.

This property was introduced in InCore 2.8.

:**› Type**: StringList
:**› Signal**: capDropChanged()
:**› Attributes**: Writable


.. _property_DockerContainer_cleanUpAtExit:

.. _signal_DockerContainer_cleanUpAtExitChanged:

.. index::
   single: cleanUpAtExit

cleanUpAtExit
+++++++++++++

This property holds whether to automatically remove the container after it has exited and :ref:`restartPolicy <property_DockerContainer_restartPolicy>` is set to :ref:`DockerContainer.NoRestart <enumitem_DockerContainer_NoRestart>`.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: cleanUpAtExitChanged()
:**› Attributes**: Writable


.. _property_DockerContainer_cleanUpAtStart:

.. _signal_DockerContainer_cleanUpAtStartChanged:

.. index::
   single: cleanUpAtStart

cleanUpAtStart
++++++++++++++

This property holds whether to automatically remove a potentially existing instance of the container identified by :ref:`name <property_DockerContainer_name>` before starting. If an instance with the same name exists, the container can't be started otherwise.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: cleanUpAtStartChanged()
:**› Attributes**: Writable


.. _property_DockerContainer_enabled:

.. _signal_DockerContainer_enabledChanged:

.. index::
   single: enabled

enabled
+++++++

This property holds whether the container is enabled, i.e. can be started. When enabled the container is started by :ref:`DockerService <object_DockerService>` automatically on start.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: enabledChanged()
:**› Attributes**: Writable


.. _property_DockerContainer_entryPoint:

.. _signal_DockerContainer_entryPointChanged:

.. index::
   single: entryPoint

entryPoint
++++++++++

This property holds an alternative entrypoint, i.e. command to execute for running the container. See the `official Docker documentation on ENTRYPOINT <https://docs.docker.com/engine/reference/run/#entrypoint-default-command-to-execute-at-runtime>`_ for details.

:**› Type**: String
:**› Signal**: entryPointChanged()
:**› Attributes**: Writable


.. _property_DockerContainer_environment:

.. _signal_DockerContainer_environmentChanged:

.. index::
   single: environment

environment
+++++++++++

This property holds a list of environment variables and their values for the container. See the `official Docker documentation on environment variables <https://docs.docker.com/engine/reference/run/#env-environment-variables>`_ for details.

:**› Type**: StringList
:**› Signal**: environmentChanged()
:**› Attributes**: Writable


.. _property_DockerContainer_error:

.. _signal_DockerContainer_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`DockerContainer.NoError <enumitem_DockerContainer_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_DockerContainer_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_DockerContainer_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_DockerContainer_errorString:

.. _signal_DockerContainer_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_DockerContainer_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_DockerContainer_hostname:

.. _signal_DockerContainer_hostnameChanged:

.. index::
   single: hostname

hostname
++++++++

This property holds the hostname to assign the Docker container. This allows other containers in the same network to connect to services in this container by hostname instead of IP address. See the `official Docker documentation on containers and hostnames <https://docs.docker.com/config/containers/container-networking/#ip-address-and-hostname>`_ for details.

:**› Type**: String
:**› Signal**: hostnameChanged()
:**› Attributes**: Writable


.. _property_DockerContainer_image:

.. _signal_DockerContainer_imageChanged:

.. index::
   single: image

image
+++++

This property holds the name of the image and an optional version tag to run in the container. See the `official Docker documentation on images <https://docs.docker.com/engine/reference/run/#imagetag>`_ for details.

:**› Type**: String
:**› Signal**: imageChanged()
:**› Attributes**: Writable


.. _property_DockerContainer_loggingDriver:

.. _signal_DockerContainer_loggingDriverChanged:

.. index::
   single: loggingDriver

loggingDriver
+++++++++++++

This property holds which logging driver to use for forwarding/storing log messages from the container. See the :ref:`DockerContainer.LoggingDriver <enum_DockerContainer_LoggingDriver>` enumeration for details.

This property was introduced in InCore 2.9.

:**› Type**: :ref:`LoggingDriver <enum_DockerContainer_LoggingDriver>`
:**› Default**: :ref:`DockerContainer.NoLogging <enumitem_DockerContainer_NoLogging>`
:**› Signal**: loggingDriverChanged()
:**› Attributes**: Writable


.. _property_DockerContainer_mounts:

.. _signal_DockerContainer_mountsChanged:

.. index::
   single: mounts

mounts
++++++

This property holds a list of Docker mounts (i.e. local directories) which to provide in the container. See the :ref:`DockerMount <object_DockerMount>` documentation for details.

:**› Type**: :ref:`List <object_List>`\<:ref:`DockerMount <object_DockerMount>`>
:**› Signal**: mountsChanged()
:**› Attributes**: Readonly


.. _property_DockerContainer_name:

.. _signal_DockerContainer_nameChanged:

.. index::
   single: name

name
++++

This property holds the name of the container. See the `official Docker documentation on container names <https://docs.docker.com/engine/reference/run/#name---name>`_ for details.

:**› Type**: String
:**› Signal**: nameChanged()
:**› Attributes**: Writable


.. _property_DockerContainer_networkMode:

.. _signal_DockerContainer_networkModeChanged:

.. index::
   single: networkMode

networkMode
+++++++++++

This property holds the network mode for the container. See :ref:`DockerContainer.NetworkMode <enum_DockerContainer_NetworkMode>` and the `official Docker documentation on networking <https://docs.docker.com/network/>`_ for details.

This property was introduced in InCore 2.0.

:**› Type**: :ref:`NetworkMode <enum_DockerContainer_NetworkMode>`
:**› Default**: :ref:`DockerContainer.Bridge <enumitem_DockerContainer_Bridge>`
:**› Signal**: networkModeChanged()
:**› Attributes**: Writable


.. _property_DockerContainer_networks:

.. _signal_DockerContainer_networksChanged:

.. index::
   single: networks

networks
++++++++

This property holds a list of Docker networks which to connect the container to if :ref:`networkMode <property_DockerContainer_networkMode>` is set to :ref:`DockerContainer.Bridge <enumitem_DockerContainer_Bridge>`. See the :ref:`DockerNetwork <object_DockerNetwork>` documentation for details.

:**› Type**: :ref:`List <object_List>`\<:ref:`DockerNetwork <object_DockerNetwork>`>
:**› Signal**: networksChanged()
:**› Attributes**: Readonly


.. _property_DockerContainer_ports:

.. _signal_DockerContainer_portsChanged:

.. index::
   single: ports

ports
+++++

This property holds a list of ports to forward from the container to the host interface. See the `official Docker documentation on incoming ports <https://docs.docker.com/engine/reference/run/#expose-incoming-ports>`_ for details.

:**› Type**: StringList
:**› Signal**: portsChanged()
:**› Attributes**: Writable


.. _property_DockerContainer_restartPolicy:

.. _signal_DockerContainer_restartPolicyChanged:

.. index::
   single: restartPolicy

restartPolicy
+++++++++++++

This property holds a setting which specifies how and when a container should be restarted on exit. See the :ref:`DockerContainer.RestartPolicy <enum_DockerContainer_RestartPolicy>` enumeration for details.

:**› Type**: :ref:`RestartPolicy <enum_DockerContainer_RestartPolicy>`
:**› Default**: :ref:`DockerContainer.RestartOnFailure <enumitem_DockerContainer_RestartOnFailure>`
:**› Signal**: restartPolicyChanged()
:**› Attributes**: Writable


.. _property_DockerContainer_running:

.. _signal_DockerContainer_runningChanged:

.. index::
   single: running

running
+++++++

This property holds whether the container is currently running. This property is updated by :ref:`start() <method_DockerContainer_start>` and :ref:`stop() <method_DockerContainer_stop>`.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: runningChanged()
:**› Attributes**: Readonly


.. _property_DockerContainer_seccompProfile:

.. _signal_DockerContainer_seccompProfileChanged:

.. index::
   single: seccompProfile

seccompProfile
++++++++++++++

This property holds the path to a custom seccomp profile file. This allows to customize the system calls which the container is allowed to use. See the `official Docker documentation on seccomp security profiles <https://docs.docker.com/engine/security/seccomp/>`_ for details.

This property was introduced in InCore 2.1.

:**› Type**: String
:**› Signal**: seccompProfileChanged()
:**› Attributes**: Writable


.. _property_DockerContainer_volumes:

.. _signal_DockerContainer_volumesChanged:

.. index::
   single: volumes

volumes
+++++++

This property holds a list of Docker volumes which to provide in the container. See the :ref:`DockerVolume <object_DockerVolume>` documentation for details.

:**› Type**: :ref:`List <object_List>`\<:ref:`DockerVolume <object_DockerVolume>`>
:**› Signal**: volumesChanged()
:**› Attributes**: Readonly


.. _property_DockerContainer_workingDirectory:

.. _signal_DockerContainer_workingDirectoryChanged:

.. index::
   single: workingDirectory

workingDirectory
++++++++++++++++

This property holds an alternative working directory, i.e. the directory in which to execute commands via :ref:`DockerContainer.run() <method_DockerContainer_run>` or :ref:`DockerContainer.execute() <method_DockerContainer_execute>`. See the `official Docker documentation on WORKDIR <https://docs.docker.com/engine/reference/run/#workdir>`_ for details.

This property was introduced in InCore 2.2.

:**› Type**: String
:**› Signal**: workingDirectoryChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_DockerContainer_execute:

.. index::
   single: execute

execute(String command, StringList arguments)
+++++++++++++++++++++++++++++++++++++++++++++

This method executes the given command in the container. The container has to be started before.

:**› Returns**: Boolean



.. _method_DockerContainer_pull:

.. index::
   single: pull

pull()
++++++

This method pulls the specified :ref:`image <property_DockerContainer_image>` from the corresponding Docker registry. This can be used for updating existing images.

This method was introduced in InCore 2.6.

:**› Returns**: Boolean



.. _method_DockerContainer_run:

.. index::
   single: run

run(String command, StringList arguments)
+++++++++++++++++++++++++++++++++++++++++

This method starts the container and runs the given command.

:**› Returns**: Boolean



.. _method_DockerContainer_start:

.. index::
   single: start

start()
+++++++

This method starts the container if it is :ref:`enabled <property_DockerContainer_enabled>` and not :ref:`running <property_DockerContainer_running>`. It returns `true` if the container could be started successfully.

:**› Returns**: Boolean



.. _method_DockerContainer_stop:

.. index::
   single: stop

stop()
++++++

This method stops and removes the container if it is :ref:`running <property_DockerContainer_running>`. It returns `true` if the container has been stopped stopped and removed successfully.

:**› Returns**: Boolean


Signals
*******


.. _signal_DockerContainer_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_DockerContainer_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_DockerContainer_error>` property this signal is also emitted several times if a certain error occurs several times in succession.



.. _signal_DockerContainer_mountsDataChanged:

.. index::
   single: mountsDataChanged

mountsDataChanged(SignedInteger index)
++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`mounts <property_DockerContainer_mounts>` list itself emitted the dataChanged() signal.



.. _signal_DockerContainer_networksDataChanged:

.. index::
   single: networksDataChanged

networksDataChanged(SignedInteger index)
++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`networks <property_DockerContainer_networks>` list itself emitted the dataChanged() signal.



.. _signal_DockerContainer_volumesDataChanged:

.. index::
   single: volumesDataChanged

volumesDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`volumes <property_DockerContainer_volumes>` list itself emitted the dataChanged() signal.


Enumerations
************


.. _enum_DockerContainer_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in DockerContainer objects. The most recently occurred error is stored in the :ref:`error <property_DockerContainer_error>` property.

.. index::
   single: DockerContainer.NoError
.. index::
   single: DockerContainer.ServiceNotFound
.. index::
   single: DockerContainer.ServiceNotRunning
.. index::
   single: DockerContainer.ContainerNotRunning
.. index::
   single: DockerContainer.ContainerStartFailed
.. index::
   single: DockerContainer.ContainerAlreadyStarted
.. index::
   single: DockerContainer.MountWithoutStorage
.. index::
   single: DockerContainer.MountSourcePathCreationFailed
.. index::
   single: DockerContainer.InvalidMountSourcePath
.. index::
   single: DockerContainer.InvalidVolumeConfiguration
.. index::
   single: DockerContainer.InvalidNetworkConfiguration
.. index::
   single: DockerContainer.InvalidName
.. index::
   single: DockerContainer.InvalidImage
.. index::
   single: DockerContainer.NetworkConnectionError
.. index::
   single: DockerContainer.PullFailed
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_DockerContainer_NoError:
  * - ``DockerContainer.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_DockerContainer_ServiceNotFound:
  * - ``DockerContainer.ServiceNotFound``
    - ``1``
    - Service not found (parent is not a DockerService).

      .. _enumitem_DockerContainer_ServiceNotRunning:
  * - ``DockerContainer.ServiceNotRunning``
    - ``2``
    - DockerService not enabled or not running.

      .. _enumitem_DockerContainer_ContainerNotRunning:
  * - ``DockerContainer.ContainerNotRunning``
    - ``3``
    - Container is not running.

      .. _enumitem_DockerContainer_ContainerStartFailed:
  * - ``DockerContainer.ContainerStartFailed``
    - ``4``
    - Container could not be started e.g. due to invalid parameters or unavailable resources.

      .. _enumitem_DockerContainer_ContainerAlreadyStarted:
  * - ``DockerContainer.ContainerAlreadyStarted``
    - ``5``
    - Container already started.

      .. _enumitem_DockerContainer_MountWithoutStorage:
  * - ``DockerContainer.MountWithoutStorage``
    - ``6``
    - Mount has no storage and no source path defined.

      .. _enumitem_DockerContainer_MountSourcePathCreationFailed:
  * - ``DockerContainer.MountSourcePathCreationFailed``
    - ``7``
    - Mount source path could not be created locally or on specified storage.

      .. _enumitem_DockerContainer_InvalidMountSourcePath:
  * - ``DockerContainer.InvalidMountSourcePath``
    - ``8``
    - Mount source path is not available and was not configured to be created automatically.

      .. _enumitem_DockerContainer_InvalidVolumeConfiguration:
  * - ``DockerContainer.InvalidVolumeConfiguration``
    - ``9``
    - Empty or invalid volume configuration (name or destination missing).

      .. _enumitem_DockerContainer_InvalidNetworkConfiguration:
  * - ``DockerContainer.InvalidNetworkConfiguration``
    - ``10``
    - Empty or invalid network configuration (name missing).

      .. _enumitem_DockerContainer_InvalidName:
  * - ``DockerContainer.InvalidName``
    - ``11``
    - Empty or invalid name.

      .. _enumitem_DockerContainer_InvalidImage:
  * - ``DockerContainer.InvalidImage``
    - ``12``
    - Empty or invalid image.

      .. _enumitem_DockerContainer_NetworkConnectionError:
  * - ``DockerContainer.NetworkConnectionError``
    - ``13``
    - Failed to connect container to specified network(s).

      .. _enumitem_DockerContainer_PullFailed:
  * - ``DockerContainer.PullFailed``
    - ``14``
    - Failed to pull the specified image. Either the Docker registry is not reachable or the image does not exist.


.. _enum_DockerContainer_LoggingDriver:

.. index::
   single: LoggingDriver

LoggingDriver
+++++++++++++

This enumeration describes the supported logging drivers for Docker containers. See the `official Docker documentation on logging drivers policies <https://docs.docker.com/engine/logging/configure/>`_ for details.

This enumeration was introduced in InCore 2.9.

.. index::
   single: DockerContainer.NoLogging
.. index::
   single: DockerContainer.LocalLogging
.. index::
   single: DockerContainer.JournaldLogging
.. index::
   single: DockerContainer.JsonFileLogging
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_DockerContainer_NoLogging:
  * - ``DockerContainer.NoLogging``
    - ``0``
    - Do not process any log messages of the container.

      .. _enumitem_DockerContainer_LocalLogging:
  * - ``DockerContainer.LocalLogging``
    - ``1``
    - Write log messages to the `local storage <https://docs.docker.com/engine/logging/drivers/local/>`_.

      .. _enumitem_DockerContainer_JournaldLogging:
  * - ``DockerContainer.JournaldLogging``
    - ``2``
    - Write log messages to the `systemd journal <https://docs.docker.com/engine/logging/drivers/journald/>`_.

      .. _enumitem_DockerContainer_JsonFileLogging:
  * - ``DockerContainer.JsonFileLogging``
    - ``3``
    - Write log messages to a `container-specific JSON file <https://docs.docker.com/engine/logging/drivers/json-file/>`_.


.. _enum_DockerContainer_NetworkMode:

.. index::
   single: NetworkMode

NetworkMode
+++++++++++

This enumeration describes the supported network modes for Docker containers. See the `official Docker documentation on networking <https://docs.docker.com/network/>`_ for details.

This enumeration was introduced in InCore 2.0.

.. index::
   single: DockerContainer.Bridge
.. index::
   single: DockerContainer.Host
.. index::
   single: DockerContainer.Overlay
.. index::
   single: DockerContainer.MacVLAN
.. index::
   single: DockerContainer.NoNetworking
.. index::
   single: DockerContainer.CustomNetworksOnly
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_DockerContainer_Bridge:
  * - ``DockerContainer.Bridge``
    - ``0``
    - Use the `bridge network driver <https://docs.docker.com/network/bridge/>`_ for the container.

      .. _enumitem_DockerContainer_Host:
  * - ``DockerContainer.Host``
    - ``1``
    - Use the `host network driver <https://docs.docker.com/network/host/>`_ for the container.

      .. _enumitem_DockerContainer_Overlay:
  * - ``DockerContainer.Overlay``
    - ``2``
    - Use the `overlay network driver <https://docs.docker.com/network/overlay/>`_ for the container.

      .. _enumitem_DockerContainer_MacVLAN:
  * - ``DockerContainer.MacVLAN``
    - ``3``
    - Use the `macvlan network driver <https://docs.docker.com/network/macvlan/>`_ for the container.

      .. _enumitem_DockerContainer_NoNetworking:
  * - ``DockerContainer.NoNetworking``
    - ``4``
    - Use the `none network driver <https://docs.docker.com/network/none/>`_, i.e. disable networking for the container.

      .. _enumitem_DockerContainer_CustomNetworksOnly:
  * - ``DockerContainer.CustomNetworksOnly``
    - ``5``
    - 


.. _enum_DockerContainer_RestartPolicy:

.. index::
   single: RestartPolicy

RestartPolicy
+++++++++++++

This enumeration describes the supported restart policies for Docker containers. See the `official Docker documentation on restart policies <https://docs.docker.com/engine/reference/run/#restart-policies---restart>`_ for details.

.. index::
   single: DockerContainer.NoRestart
.. index::
   single: DockerContainer.RestartOnFailure
.. index::
   single: DockerContainer.RestartUnlessStopped
.. index::
   single: DockerContainer.RestartAlways
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_DockerContainer_NoRestart:
  * - ``DockerContainer.NoRestart``
    - ``0``
    - Do not automatically restart the container when it exits.

      .. _enumitem_DockerContainer_RestartOnFailure:
  * - ``DockerContainer.RestartOnFailure``
    - ``1``
    - Restart only if the container exits with a non-zero exit status.

      .. _enumitem_DockerContainer_RestartUnlessStopped:
  * - ``DockerContainer.RestartUnlessStopped``
    - ``2``
    - Always restart the container regardless of the exit status, including on daemon startup, except if the container was put into a stopped state before the Docker daemon was stopped.

      .. _enumitem_DockerContainer_RestartAlways:
  * - ``DockerContainer.RestartAlways``
    - ``3``
    - Always restart the container regardless of the exit status. With this policy the Docker daemon will try to restart the container indefinitely. The container will also always start on daemon startup, regardless of the current state of the container.


.. _example_DockerContainer:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    
    Application {
        DockerService {
            DockerContainer {
                name: "nodered-example"
                image: "nodered/node-red:latest-minimal"
                ports: [ "1880:1880" ]
                environment: [ "FLOWS=myflows.json", "NODE_OPTIONS=--max_old_space_size=128" ]
                restartPolicy: DockerContainer.RestartAlways
            }
        }
    }
    