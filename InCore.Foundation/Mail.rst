
.. _object_Mail:


:index:`Mail`
-------------

Description
***********

The Mail object can be used to send emails.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`body <property_Mail_body>`
  * :ref:`configuration <property_Mail_configuration>`
  * :ref:`error <property_Mail_error>`
  * :ref:`errorData <property_Mail_errorData>`
  * :ref:`errorString <property_Mail_errorString>`
  * :ref:`from <property_Mail_from>`
  * :ref:`subject <property_Mail_subject>`
  * :ref:`to <property_Mail_to>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`send() <method_Mail_send>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_Mail_errorOccurred>`
  * :ref:`sent() <signal_Mail_sent>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_Mail_Error>`



Properties
**********


.. _property_Mail_body:

.. _signal_Mail_bodyChanged:

.. index::
   single: body

body
++++

This property holds the body of the email. This contains the message.

:**› Type**: String
:**› Signal**: bodyChanged()
:**› Attributes**: Writable


.. _property_Mail_configuration:

.. _signal_Mail_configurationChanged:

.. index::
   single: configuration

configuration
+++++++++++++

This property holds the :ref:`SmtpConfiguration <object_SmtpConfiguration>` used to connect to the server.

:**› Type**: :ref:`SmtpConfiguration <object_SmtpConfiguration>`
:**› Signal**: configurationChanged()
:**› Attributes**: Writable


.. _property_Mail_error:

.. _signal_Mail_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`Mail.NoError <enumitem_Mail_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_Mail_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_Mail_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_Mail_errorData:

.. _signal_Mail_errorDataChanged:

.. index::
   single: errorData

errorData
+++++++++

This property holds all error data of the sender process, when sending has failed.

:**› Type**: String
:**› Signal**: errorDataChanged()
:**› Attributes**: Readonly


.. _property_Mail_errorString:

.. _signal_Mail_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_Mail_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_Mail_from:

.. _signal_Mail_fromChanged:

.. index::
   single: from

from
++++

This property holds the name of the sender.

:**› Type**: :ref:`MailAddress <object_MailAddress>`
:**› Signal**: fromChanged()
:**› Attributes**: Writable


.. _property_Mail_subject:

.. _signal_Mail_subjectChanged:

.. index::
   single: subject

subject
+++++++

This property holds the subject of the email

:**› Type**: String
:**› Signal**: subjectChanged()
:**› Attributes**: Writable


.. _property_Mail_to:

.. _signal_Mail_toChanged:

.. index::
   single: to

to
++

This property holds the name of the recipient.

:**› Type**: :ref:`MailAddress <object_MailAddress>`
:**› Signal**: toChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_Mail_send:

.. index::
   single: send

send()
++++++

This method sends the email with the configured data.

:**› Returns**: Boolean


Signals
*******


.. _signal_Mail_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_Mail_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_Mail_error>` property this signal is also emitted several times if a certain error occurs several times in succession.



.. _signal_Mail_sent:

.. index::
   single: sent

sent()
++++++

This signal is emitted when the operation is done, the email was sent successfully.


Enumerations
************


.. _enum_Mail_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in Mail objects. The most recently occurred error is stored in the :ref:`error <property_Mail_error>` property.

.. index::
   single: Mail.NoError
.. index::
   single: Mail.ConfigurationError
.. index::
   single: Mail.EmptyFromError
.. index::
   single: Mail.EmptyToError
.. index::
   single: Mail.EmptySubjectError
.. index::
   single: Mail.SystemError
.. index::
   single: Mail.SendError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_Mail_NoError:
  * - ``Mail.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_Mail_ConfigurationError:
  * - ``Mail.ConfigurationError``
    - ``1``
    - Invalid or incomplete configuration.

      .. _enumitem_Mail_EmptyFromError:
  * - ``Mail.EmptyFromError``
    - ``2``
    - No sender in property "from" specified.

      .. _enumitem_Mail_EmptyToError:
  * - ``Mail.EmptyToError``
    - ``3``
    - No recipient in property "to" specified.

      .. _enumitem_Mail_EmptySubjectError:
  * - ``Mail.EmptySubjectError``
    - ``4``
    - No subject specified.

      .. _enumitem_Mail_SystemError:
  * - ``Mail.SystemError``
    - ``5``
    - Error starting the SMTP system process.

      .. _enumitem_Mail_SendError:
  * - ``Mail.SendError``
    - ``6``
    - The email could not be sent, likely due to a wrong configuration.


.. _example_Mail:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    import InCore.IO 2.0
    
    Application {
    
        DigitalIO {
            id: input
            direction: DigitalIO.Input
            index: DigitalIO.IO1
            onValueChanged:
                if( value === true ) {
                    mailer.send()    //send mail
                }
        }
    
        Mail {
            id: mailer
            //SmtpConfiguration
            configuration {
                server: "mail.example.org"
                port: 25
                tls: true
                username: "sender"
                password: "c5ypt!cP4ssw0rd"
            }
            //MailAddress
            from {
                name: "Test sender"
                address: "sender@example.com"
            }
            to {
                name: "Test recipient"
                address: "recipient@example.com"
            }
            subject: "digital input on"
    
            body: "Dear Customer\n\n
                    the digital input value had an rising edge."
    
            //error handling
            onErrorDataChanged: console.log( "sending failed with data:", errorData )    //check for sending failure
            onErrorChanged: console.log( errorString )            //other errors
        }
    }
    