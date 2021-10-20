
.. _object_DockerMount:


:index:`DockerMount`
--------------------

Description
***********

The DockerMount object defines a Docker mount used to mount directories from the host system into Docker containers. Most functionalities and modes are supported through the :ref:`DockerObject.driver <property_DockerObject_driver>` and :ref:`DockerObject.options <property_DockerObject_options>` properties. See the official Docker documentation on `bind mounts <https://docs.docker.com/storage/bind-mounts/>`_ and `tmpfs mounts <https://docs.docker.com/storage/tmpfs/>`_ for more information on how to use Docker mounts.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`autoCreate <property_DockerMount_autoCreate>`
  * :ref:`destination <property_DockerMount_destination>`
  * :ref:`readOnly <property_DockerMount_readOnly>`
  * :ref:`source <property_DockerMount_source>`
  * :ref:`storage <property_DockerMount_storage>`
  * :ref:`storageSubDirectory <property_DockerMount_storageSubDirectory>`
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

  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_DockerMount_autoCreate:

.. _signal_DockerMount_autoCreateChanged:

.. index::
   single: autoCreate

autoCreate
++++++++++

This property holds whether the source directory should be created automatically if it does not exist.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: autoCreateChanged()
:**› Attributes**: Writable


.. _property_DockerMount_destination:

.. _signal_DockerMount_destinationChanged:

.. index::
   single: destination

destination
+++++++++++

This property holds an absolute path to use as mount point inside the container. All contents if the :ref:`source <property_DockerMount_source>` directory will be available in this directory in the container.

:**› Type**: String
:**› Signal**: destinationChanged()
:**› Attributes**: Writable


.. _property_DockerMount_readOnly:

.. _signal_DockerMount_readOnlyChanged:

.. index::
   single: readOnly

readOnly
++++++++

This property holds whether to mount the source directory read-only into the container. This can be used as an additional security measure if the container does not need to write to the mount anyway.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: readOnlyChanged()
:**› Attributes**: Writable


.. _property_DockerMount_source:

.. _signal_DockerMount_sourceChanged:

.. index::
   single: source

source
++++++

This property holds an absolute path to the source directory which to mount into the container. If :ref:`storage <property_DockerMount_storage>` is set, :ref:`storageSubDirectory <property_DockerMount_storageSubDirectory>` has to be used instead.

:**› Type**: String
:**› Signal**: sourceChanged()
:**› Attributes**: Writable


.. _property_DockerMount_storage:

.. _signal_DockerMount_storageChanged:

.. index::
   single: storage

storage
+++++++

This property holds the storage of which a :ref:`sub directory <property_DockerMount_storageSubDirectory>` shall be mounted into the container.

:**› Type**: :ref:`Storage <object_Storage>`
:**› Signal**: storageChanged()
:**› Attributes**: Writable


.. _property_DockerMount_storageSubDirectory:

.. _signal_DockerMount_storageSubDirectoryChanged:

.. index::
   single: storageSubDirectory

storageSubDirectory
+++++++++++++++++++

This property holds a relative path specifying a sub directory on the configured :ref:`storage <property_DockerMount_storage>` which to mount into the container.

:**› Type**: String
:**› Signal**: storageSubDirectoryChanged()
:**› Attributes**: Writable


.. _example_DockerMount:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    
    Application {
        System {
            DockerService {
                DockerContainer {
                    name: "docker-mount-example"
                    image: "arm32v7/nginx:latest"
                    mounts: [
                        DockerMount {
                            source: "/storage/nginx/conf.d"
                            destination: "/etc/nginx/conf.d"
                            readOnly: true
                        }
                    ]
                }
            }
        }
    }
    