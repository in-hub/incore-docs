
.. _object_DockerVolume:


:index:`DockerVolume`
---------------------

Description
***********

The DockerVolume object defines a Docker volume used to provide persistent storage to Docker containers. Most functionalities and modes are supported through the :ref:`DockerObject.driver <property_DockerObject_driver>` and :ref:`DockerObject.options <property_DockerObject_options>` properties. See the `official Docker documentation <https://docs.docker.com/storage/volumes/>`_ for more information on how to use Docker volumes.

:**› Inherits**: :ref:`DockerObject <object_DockerObject>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`destination <property_DockerVolume_destination>`
  * :ref:`readOnly <property_DockerVolume_readOnly>`
  * :ref:`DockerObject.driver <property_DockerObject_driver>`
  * :ref:`DockerObject.error <property_DockerObject_error>`
  * :ref:`DockerObject.errorString <property_DockerObject_errorString>`
  * :ref:`DockerObject.name <property_DockerObject_name>`
  * :ref:`DockerObject.options <property_DockerObject_options>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`DockerObject.create() <method_DockerObject_create>`
  * :ref:`DockerObject.remove() <method_DockerObject_remove>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`DockerObject.errorOccurred() <signal_DockerObject_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`DockerObject.Error <enum_DockerObject_Error>`



Properties
**********


.. _property_DockerVolume_destination:

.. _signal_DockerVolume_destinationChanged:

.. index::
   single: destination

destination
+++++++++++

This property holds the destination path where the volume is mounted in the container.

:**› Type**: String
:**› Signal**: destinationChanged()
:**› Attributes**: Writable


.. _property_DockerVolume_readOnly:

.. _signal_DockerVolume_readOnlyChanged:

.. index::
   single: readOnly

readOnly
++++++++

This property holds whether this volume should be provided read-only for the container. Read-only volumes can be used to provide configuration files and other static data.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: readOnlyChanged()
:**› Attributes**: Writable


.. _example_DockerVolume:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    
    Application {
        System {
            DockerService {
                DockerContainer {
                    name: "docker-postgresql-example"
                    image: "arm32v7/postgres:alpine"
                    volumes: [ DockerVolume { name: "postgresdata"; destination: "/var/lib/postgresql/data" } ]
                }
                DockerContainer {
                    name: "docker-nodered-example"
                    image: "nodered/node-red:latest-minimal"
                    ports: [ "1880:1880" ]
                    volumes: [ DockerVolume { name: "nodereddata"; destination: "/data" } ]
                }
            }
        }
    }
    