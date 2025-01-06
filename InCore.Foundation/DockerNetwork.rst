
.. _object_DockerNetwork:


:index:`DockerNetwork`
----------------------

Description
***********

The DockerNetwork object defines a Docker network used to connect Docker networks to each other. Most functionalities and modes (such as bridge, host and overlay networks) are supported through the :ref:`DockerObject.driver <property_DockerObject_driver>` and :ref:`DockerObject.options <property_DockerObject_options>` properties. See the `official Docker documentation <https://docs.docker.com/network/>`_ for more information on how to use Docker networks.

:**› Inherits**: :ref:`DockerObject <object_DockerObject>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`gateways <property_DockerNetwork_gateways>`
  * :ref:`internal <property_DockerNetwork_internal>`
  * :ref:`ipRange <property_DockerNetwork_ipRange>`
  * :ref:`subnets <property_DockerNetwork_subnets>`
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
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
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


.. _property_DockerNetwork_gateways:

.. _signal_DockerNetwork_gatewaysChanged:

.. index::
   single: gateways

gateways
++++++++

This property holds the gateways which to assign the Docker network.

This property was introduced in InCore 2.8.

:**› Type**: StringList
:**› Signal**: gatewaysChanged()
:**› Attributes**: Writable


.. _property_DockerNetwork_internal:

.. _signal_DockerNetwork_internalChanged:

.. index::
   single: internal

internal
++++++++

This property holds whether this network should be configured as an internal network used for connecting containers only. Internal networks can't be accessed by the outside world.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: internalChanged()
:**› Attributes**: Writable


.. _property_DockerNetwork_ipRange:

.. _signal_DockerNetwork_ipRangeChanged:

.. index::
   single: ipRange

ipRange
+++++++

This property holds the IP range which to allocate for the Docker network.

This property was introduced in InCore 2.8.

:**› Type**: String
:**› Signal**: ipRangeChanged()
:**› Attributes**: Writable


.. _property_DockerNetwork_subnets:

.. _signal_DockerNetwork_subnetsChanged:

.. index::
   single: subnets

subnets
+++++++

This property holds the subnets which to assign the Docker network.

This property was introduced in InCore 2.8.

:**› Type**: StringList
:**› Signal**: subnetsChanged()
:**› Attributes**: Writable


.. _example_DockerNetwork:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    
    Application {
    
        property var internalNetwork : DockerNetwork { id: internalNetwork; name: "example_internal"; internal: true; }
    
        DockerService {
            DockerContainer {
                name: "example-frontend"
                image: "example/frontend:latest"
                hostname: "frontend"
                ports: [ "80:80" ]
                networks: [ internalNetwork ]
            }
            DockerContainer {
                name: "example-backend"
                image: "example/backend:latest"
                hostname: "backend"
                networks: [ internalNetwork ]
            }
        }
    }
    