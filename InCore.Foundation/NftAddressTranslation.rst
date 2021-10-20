
.. _object_NftAddressTranslation:


:index:`NftAddressTranslation`
------------------------------

Description
***********



This object was introduced in InCore 2.1.

:**› Inherits**: :ref:`NftFlow <object_NftFlow>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`error <property_NftAddressTranslation_error>`
  * :ref:`errorString <property_NftAddressTranslation_errorString>`
  * :ref:`masquerade <property_NftAddressTranslation_masquerade>`
  * :ref:`natDestinationAddress <property_NftAddressTranslation_natDestinationAddress>`
  * :ref:`natSourceAddress <property_NftAddressTranslation_natSourceAddress>`
  * :ref:`NftFlow.destinationAddress <property_NftFlow_destinationAddress>`
  * :ref:`NftFlow.destinationPorts <property_NftFlow_destinationPorts>`
  * :ref:`NftFlow.inputInterface <property_NftFlow_inputInterface>`
  * :ref:`NftFlow.outputInterface <property_NftFlow_outputInterface>`
  * :ref:`NftFlow.protocol <property_NftFlow_protocol>`
  * :ref:`NftFlow.sourceAddress <property_NftFlow_sourceAddress>`
  * :ref:`NftFlow.sourcePorts <property_NftFlow_sourcePorts>`
  * :ref:`NftTable.chains <property_NftTable_chains>`
  * :ref:`NftTable.enabled <property_NftTable_enabled>`
  * :ref:`NftTable.family <property_NftTable_family>`
  * :ref:`NftTable.name <property_NftTable_name>`
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

  * :ref:`errorOccurred() <signal_NftAddressTranslation_errorOccurred>`
  * :ref:`NftTable.chainsDataChanged() <signal_NftTable_chainsDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_NftAddressTranslation_Error>`
  * :ref:`NftTable.Family <enum_NftTable_Family>`



Properties
**********


.. _property_NftAddressTranslation_error:

.. _signal_NftAddressTranslation_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`NftAddressTranslation.NoError <enumitem_NftAddressTranslation_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_NftAddressTranslation_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_NftAddressTranslation_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_NftAddressTranslation_errorString:

.. _signal_NftAddressTranslation_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_NftAddressTranslation_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_NftAddressTranslation_masquerade:

.. _signal_NftAddressTranslation_masqueradeChanged:

.. index::
   single: masquerade

masquerade
++++++++++

This property holds whether to masquerade connections. If enabled, the :ref:`NftFlow.outputInterface <property_NftFlow_outputInterface>` property has to be set.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: masqueradeChanged()
:**› Attributes**: Writable


.. _property_NftAddressTranslation_natDestinationAddress:

.. _signal_NftAddressTranslation_natDestinationAddressChanged:

.. index::
   single: natDestinationAddress

natDestinationAddress
+++++++++++++++++++++

This property holds the address to use for rewriting the destination address of packets.

:**› Type**: String
:**› Signal**: natDestinationAddressChanged()
:**› Attributes**: Writable


.. _property_NftAddressTranslation_natSourceAddress:

.. _signal_NftAddressTranslation_natSourceAddressChanged:

.. index::
   single: natSourceAddress

natSourceAddress
++++++++++++++++

This property holds the address to use for rewriting the source address of packets.

:**› Type**: String
:**› Signal**: natSourceAddressChanged()
:**› Attributes**: Writable

Signals
*******


.. _signal_NftAddressTranslation_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_NftAddressTranslation_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_NftAddressTranslation_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_NftAddressTranslation_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in NftAddressTranslation objects. The most recently occurred error is stored in the :ref:`error <property_NftAddressTranslation_error>` property.

.. index::
   single: NftAddressTranslation.NoError
.. index::
   single: NftAddressTranslation.MasqueradingWithoutOutputInterface
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_NftAddressTranslation_NoError:
  * - ``NftAddressTranslation.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_NftAddressTranslation_MasqueradingWithoutOutputInterface:
  * - ``NftAddressTranslation.MasqueradingWithoutOutputInterface``
    - ``1``
    - Masquerading enabled but output interface not set.


.. _example_NftAddressTranslation:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    
    NftFirewall {
        NftAddressTranslation {
            inputInterface: "usb0"
            destinationAddress: "192.168.123.1"
            natSourceAddress: "192.168.19.1"
            natDestinationAddress: "192.168.19.2"
        }
    
        onRulesetChanged: console.log(ruleset)
    }
    