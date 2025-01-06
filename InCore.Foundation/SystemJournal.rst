
.. _object_SystemJournal:


:index:`SystemJournal`
----------------------

Description
***********

The SystemJournal object provides access to the system's journal, i.e. system-wide log messages

This object was introduced in InCore 2.8.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`bootMessages <property_SystemJournal_bootMessages>`
  * :ref:`messagesLimit <property_SystemJournal_messagesLimit>`
  * :ref:`recentMessages <property_SystemJournal_recentMessages>`
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

  * :ref:`messageAppended() <signal_SystemJournal_messageAppended>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_SystemJournal_bootMessages:

.. _signal_SystemJournal_bootMessagesChanged:

.. index::
   single: bootMessages

bootMessages
++++++++++++

This property holds all entries of the system journal written during system boot.

:**› Type**: String
:**› Signal**: bootMessagesChanged()
:**› Attributes**: Readonly


.. _property_SystemJournal_messagesLimit:

.. _signal_SystemJournal_messagesLimitChanged:

.. index::
   single: messagesLimit

messagesLimit
+++++++++++++

This property holds the number of log messages to store in the :ref:`recentMessages <property_SystemJournal_recentMessages>` property.

:**› Type**: SignedInteger
:**› Default**: ``1000``
:**› Signal**: messagesLimitChanged()
:**› Attributes**: Writable


.. _property_SystemJournal_recentMessages:

.. _signal_SystemJournal_recentMessagesChanged:

.. index::
   single: recentMessages

recentMessages
++++++++++++++

This property holds the most recent journal messages. The number of messages is controlled by the :ref:`messagesLimit <property_SystemJournal_messagesLimit>` property.

:**› Type**: String
:**› Signal**: recentMessagesChanged()
:**› Attributes**: Readonly

Signals
*******


.. _signal_SystemJournal_messageAppended:

.. index::
   single: messageAppended

messageAppended(String message)
+++++++++++++++++++++++++++++++




