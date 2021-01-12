
.. _object_Sms:


:index:`Sms`
------------

Description
***********

The Sms object represents an `SMS message <https://en.wikipedia.org/wiki/SMS>`_. A message text (:ref:`text <property_Sms_text>`) can be sent to a recipient (:ref:`recipientNumber <property_Sms_recipientNumber>`) usinga :ref:`MobileNetworkInterface <object_MobileNetworkInterface>` specified through the :ref:`transport <property_Sms_transport>` property.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`error <property_Sms_error>`
  * :ref:`errorData <property_Sms_errorData>`
  * :ref:`errorString <property_Sms_errorString>`
  * :ref:`recipientNumber <property_Sms_recipientNumber>`
  * :ref:`text <property_Sms_text>`
  * :ref:`transport <property_Sms_transport>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`send() <method_Sms_send>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_Sms_errorOccurred>`
  * :ref:`sent() <signal_Sms_sent>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_Sms_Error>`



Properties
**********


.. _property_Sms_error:

.. _signal_Sms_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`Sms.NoError <enumitem_Sms_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_Sms_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_Sms_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_Sms_errorData:

.. _signal_Sms_errorDataChanged:

.. index::
   single: errorData

errorData
+++++++++

This property holds additional information on errors occurred while sending SMS messages.

:**› Type**: String
:**› Signal**: errorDataChanged()
:**› Attributes**: Readonly


.. _property_Sms_errorString:

.. _signal_Sms_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_Sms_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_Sms_recipientNumber:

.. _signal_Sms_recipientNumberChanged:

.. index::
   single: recipientNumber

recipientNumber
+++++++++++++++

This property holds the phone number of the SMS recipient.

:**› Type**: String
:**› Signal**: recipientNumberChanged()
:**› Attributes**: Writable


.. _property_Sms_text:

.. _signal_Sms_textChanged:

.. index::
   single: text

text
++++

This property holds the text of the SMS to send. If it contains non-ASCII characters the Unicode (UCS-2) encoding is used which requires 2 bytes per character. This may be relevant if the number of SMS that can be sent in a time period is limited.

:**› Type**: String
:**› Signal**: textChanged()
:**› Attributes**: Writable


.. _property_Sms_transport:

.. _signal_Sms_transportChanged:

.. index::
   single: transport

transport
+++++++++

This property holds the mobile network interface which to use for sending the SMS messages.

:**› Type**: :ref:`MobileNetworkInterface <object_MobileNetworkInterface>`
:**› Signal**: transportChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_Sms_send:

.. index::
   single: send

send()
++++++

This method sends the SMS using the given :ref:`transport <property_Sms_transport>`. It returns ``true`` if the send operation has been initiated successfully. Actual errors occuring while sending the SMS are signaled through the :ref:`error <property_Sms_error>` property. Additional information may be available in the :ref:`errorData <property_Sms_errorData>` property.

:**› Returns**: Boolean


Signals
*******


.. _signal_Sms_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_Sms_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_Sms_error>` property this signal is also emitted several times if a certain error occurs several times in succession.



.. _signal_Sms_sent:

.. index::
   single: sent

sent()
++++++

This signal is emitted when an SMS has been sent successfully. It's not emitted if an error occurred while sending.


Enumerations
************


.. _enum_Sms_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in Sms objects. The most recently occurred error is stored in the :ref:`error <property_Sms_error>` property.

.. index::
   single: Sms.NoError
.. index::
   single: Sms.TransportError
.. index::
   single: Sms.EmptyRecipientNumber
.. index::
   single: Sms.EmptyTextError
.. index::
   single: Sms.SendError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_Sms_NoError:
  * - ``Sms.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_Sms_TransportError:
  * - ``Sms.TransportError``
    - ``1``
    - SMS transport not set or invalid.

      .. _enumitem_Sms_EmptyRecipientNumber:
  * - ``Sms.EmptyRecipientNumber``
    - ``2``
    - SMS recipient number is empty.

      .. _enumitem_Sms_EmptyTextError:
  * - ``Sms.EmptyTextError``
    - ``3``
    - SMS text is empty.

      .. _enumitem_Sms_SendError:
  * - ``Sms.SendError``
    - ``4``
    - The SMS could not be send, likely due to a network error or an invalid recipient.


.. _example_Sms:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    
    Application {
    
        Sms {
            id: sms
            text: ("Hello world! This is SMS number %1.").arg(smsCounter.value)
            transport: mobileNetworkInterface
            recipientNumber: "+49123456789"
            onErrorOccurred: console.log( "Could not send SMS:", errorString, errorData)
        }
    
        Counter {
            id: smsCounter
            interval: 30000
            onValueChanged: sms.send();
        }
    
        NetworkConfiguration {
            MobileNetworkInterface {
                id: mobileNetworkInterface
                // configure connection parameters
                apn: "internet.myprovider.de"
                username: "inhub"
                password: "MyS3cr3tP4ssw0rd"
            }
        }
    }
    