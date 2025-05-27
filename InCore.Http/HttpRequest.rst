
.. _object_HttpRequest:


:index:`HttpRequest`
--------------------

Description
***********

The HttpRequest object represents a HTTP request which can be sent to a server at a given URL (:ref:`url <property_HttpRequest_url>`). All common methods (GET, PUT, POST, DELETE) are supported. The HTTP headers can be defined through the :ref:`headers <property_HttpRequest_headers>` property. When transferring data to the server the :ref:`HttpContent <object_HttpContent>` object in the :ref:`content <property_HttpRequest_content>` property needs to be prepared accordingly. The received response (headers, status code and data) is accessible through the :ref:`response <property_HttpRequest_response>` property.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`allowPipelining <property_HttpRequest_allowPipelining>`
  * :ref:`authentication <property_HttpRequest_authentication>`
  * :ref:`content <property_HttpRequest_content>`
  * :ref:`error <property_HttpRequest_error>`
  * :ref:`errorString <property_HttpRequest_errorString>`
  * :ref:`followRedirects <property_HttpRequest_followRedirects>`
  * :ref:`headers <property_HttpRequest_headers>`
  * :ref:`response <property_HttpRequest_response>`
  * :ref:`url <property_HttpRequest_url>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 2

  * :ref:`del() <method_HttpRequest_del>`
  * :ref:`get() <method_HttpRequest_get>`
  * :ref:`post() <method_HttpRequest_post>`
  * :ref:`put() <method_HttpRequest_put>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_HttpRequest_errorOccurred>`
  * :ref:`headersDataChanged() <signal_HttpRequest_headersDataChanged>`
  * :ref:`responseReceived() <signal_HttpRequest_responseReceived>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_HttpRequest_Error>`



Properties
**********


.. _property_HttpRequest_allowPipelining:

.. _signal_HttpRequest_allowPipeliningChanged:

.. index::
   single: allowPipelining

allowPipelining
+++++++++++++++

This property holds whether the HTTP client is allowed to use HTTP pipelining with this request.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: allowPipeliningChanged()
:**› Attributes**: Writable


.. _property_HttpRequest_authentication:

.. _signal_HttpRequest_authenticationChanged:

.. index::
   single: authentication

authentication
++++++++++++++

This property holds the :ref:`HttpAuthentication <object_HttpAuthentication>` object which provides user credentials.

This property was introduced in InCore 2.7.

:**› Type**: :ref:`HttpAuthentication <object_HttpAuthentication>`
:**› Signal**: authenticationChanged()
:**› Attributes**: Readonly


.. _property_HttpRequest_content:

.. _signal_HttpRequest_contentChanged:

.. index::
   single: content

content
+++++++

This property holds the content which to send to the server (PUT/POST requests only). If :ref:`headers <property_HttpRequest_headers>` does not contain a :ref:`HttpHeader <object_HttpHeader>` object with :ref:`HttpHeader.type <property_HttpHeader_type>` = :ref:`HttpHeader.ContentType <enumitem_HttpHeader_ContentType>` the request will be sent with an additional content type header with an automatically determined value depending on :ref:`HttpContent.type <property_HttpContent_type>`.

:**› Type**: :ref:`HttpContent <object_HttpContent>`
:**› Signal**: contentChanged()
:**› Attributes**: Writable


.. _property_HttpRequest_error:

.. _signal_HttpRequest_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`HttpRequest.NoError <enumitem_HttpRequest_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_HttpRequest_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_HttpRequest_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_HttpRequest_errorString:

.. _signal_HttpRequest_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_HttpRequest_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_HttpRequest_followRedirects:

.. _signal_HttpRequest_followRedirectsChanged:

.. index::
   single: followRedirects

followRedirects
+++++++++++++++

This property holds whether the HTTP client should automatically follow a HTTP redirect response or not. Currently redirects that are insecure, that is redirecting from "https" to "http" protocol, are not allowed.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: followRedirectsChanged()
:**› Attributes**: Writable


.. _property_HttpRequest_headers:

.. _signal_HttpRequest_headersChanged:

.. index::
   single: headers

headers
+++++++

This property holds a list of header objects to use when sending a HTTP request.

:**› Type**: :ref:`List <object_List>`\<:ref:`HttpHeader <object_HttpHeader>`>
:**› Signal**: headersChanged()
:**› Attributes**: Readonly


.. _property_HttpRequest_response:

.. _signal_HttpRequest_responseChanged:

.. index::
   single: response

response
++++++++

This property holds the last received response for a request sent through this object.

:**› Type**: :ref:`HttpResponse <object_HttpResponse>`
:**› Signal**: responseChanged()
:**› Attributes**: Readonly


.. _property_HttpRequest_url:

.. _signal_HttpRequest_urlChanged:

.. index::
   single: url

url
+++

This property holds the URL which to send a request for.

:**› Type**: String
:**› Signal**: urlChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_HttpRequest_del:

.. index::
   single: del

del(JSValue callback, JSValue errorCallback)
++++++++++++++++++++++++++++++++++++++++++++

This method sends a HTTP request with the `DELETE` method to the server. It's mainly used for deleting resources at the given URL.

See `RFC2616 Section 9.7 <https://tools.ietf.org/html/rfc2616#section-9.7>`_ for details.



.. _method_HttpRequest_get:

.. index::
   single: get

get(JSValue responseCallback, JSValue errorCallback)
++++++++++++++++++++++++++++++++++++++++++++++++++++

This method sends a HTTP request with the `GET` method to the server. It's mainly used for downloading resources at the given URL.

See `RFC2616 Section 9.3 <https://tools.ietf.org/html/rfc2616#section-9.3>`_ for details.



.. _method_HttpRequest_post:

.. index::
   single: post

post(JSValue callback, JSValue errorCallback)
+++++++++++++++++++++++++++++++++++++++++++++

This method sends a HTTP request with the `POST` method to the server. It's mainly used for annotation of existing resources, providing a block of data, such as the result of submitting a form, to a data-handling process or extending a database through an append operation.

See `RFC2616 Section 9.5 <https://tools.ietf.org/html/rfc2616#section-9.5>`_ for details.



.. _method_HttpRequest_put:

.. index::
   single: put

put(JSValue callback, JSValue errorCallback)
++++++++++++++++++++++++++++++++++++++++++++

This method sends a HTTP request with the `PUT` method to the server. It's mainly used for storing resources under the given URL.

See `RFC2616 Section 9.6 <https://tools.ietf.org/html/rfc2616#section-9.6>`_ for details.


Signals
*******


.. _signal_HttpRequest_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_HttpRequest_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_HttpRequest_error>` property this signal is also emitted several times if a certain error occurs several times in succession.



.. _signal_HttpRequest_headersDataChanged:

.. index::
   single: headersDataChanged

headersDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`headers <property_HttpRequest_headers>` list itself emitted the dataChanged() signal.



.. _signal_HttpRequest_responseReceived:

.. index::
   single: responseReceived

responseReceived()
++++++++++++++++++

This signal is emitted when a response is received for a request represented by this object. It's identical to the :ref:`HttpResponse.received() <signal_HttpResponse_received>` signal but provided for convenience.


Enumerations
************


.. _enum_HttpRequest_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in HttpRequest objects. The most recently occurred error is stored in the :ref:`error <property_HttpRequest_error>` property.

.. index::
   single: HttpRequest.NoError
.. index::
   single: HttpRequest.ConnectionRefusedError
.. index::
   single: HttpRequest.RemoteHostClosedError
.. index::
   single: HttpRequest.HostNotFoundError
.. index::
   single: HttpRequest.TimeoutError
.. index::
   single: HttpRequest.OperationCanceledError
.. index::
   single: HttpRequest.SslHandshakeFailedError
.. index::
   single: HttpRequest.TemporaryNetworkFailureError
.. index::
   single: HttpRequest.NetworkSessionFailedError
.. index::
   single: HttpRequest.BackgroundRequestNotAllowedError
.. index::
   single: HttpRequest.TooManyRedirectsError
.. index::
   single: HttpRequest.InsecureRedirectError
.. index::
   single: HttpRequest.UnknownNetworkError
.. index::
   single: HttpRequest.ProxyConnectionRefusedError
.. index::
   single: HttpRequest.ProxyConnectionClosedError
.. index::
   single: HttpRequest.ProxyNotFoundError
.. index::
   single: HttpRequest.ProxyTimeoutError
.. index::
   single: HttpRequest.ProxyAuthenticationRequiredError
.. index::
   single: HttpRequest.UnknownProxyError
.. index::
   single: HttpRequest.ContentAccessDenied
.. index::
   single: HttpRequest.ContentOperationNotPermittedError
.. index::
   single: HttpRequest.ContentNotFoundError
.. index::
   single: HttpRequest.AuthenticationRequiredError
.. index::
   single: HttpRequest.ContentReSendError
.. index::
   single: HttpRequest.ContentConflictError
.. index::
   single: HttpRequest.ContentGoneError
.. index::
   single: HttpRequest.UnknownContentError
.. index::
   single: HttpRequest.ProtocolUnknownError
.. index::
   single: HttpRequest.ProtocolInvalidOperationError
.. index::
   single: HttpRequest.ProtocolFailure
.. index::
   single: HttpRequest.InternalServerError
.. index::
   single: HttpRequest.OperationNotImplementedError
.. index::
   single: HttpRequest.ServiceUnavailableError
.. index::
   single: HttpRequest.UnknownServerError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_HttpRequest_NoError:
  * - ``HttpRequest.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_HttpRequest_ConnectionRefusedError:
  * - ``HttpRequest.ConnectionRefusedError``
    - ``1``
    - The remote server refused the connection (the server is not accepting requests).

      .. _enumitem_HttpRequest_RemoteHostClosedError:
  * - ``HttpRequest.RemoteHostClosedError``
    - ``2``
    - The remote server closed the connection prematurely, before the entire response was received and processed.

      .. _enumitem_HttpRequest_HostNotFoundError:
  * - ``HttpRequest.HostNotFoundError``
    - ``3``
    - The remote host name was not found (invalid hostname).

      .. _enumitem_HttpRequest_TimeoutError:
  * - ``HttpRequest.TimeoutError``
    - ``4``
    - The connection to the remote server timed out.

      .. _enumitem_HttpRequest_OperationCanceledError:
  * - ``HttpRequest.OperationCanceledError``
    - ``5``
    - The operation was canceled before it was finished.

      .. _enumitem_HttpRequest_SslHandshakeFailedError:
  * - ``HttpRequest.SslHandshakeFailedError``
    - ``6``
    - The SSL/TLS handshake failed and the encrypted channel could not be established.

      .. _enumitem_HttpRequest_TemporaryNetworkFailureError:
  * - ``HttpRequest.TemporaryNetworkFailureError``
    - ``7``
    - The connection was broken due to disconnection from the network, however the system has initiated roaming to another access point. The request should be resubmitted and will be processed as soon as the connection is re-established.

      .. _enumitem_HttpRequest_NetworkSessionFailedError:
  * - ``HttpRequest.NetworkSessionFailedError``
    - ``8``
    - The connection was broken due to disconnection from the network or failure to start the network.

      .. _enumitem_HttpRequest_BackgroundRequestNotAllowedError:
  * - ``HttpRequest.BackgroundRequestNotAllowedError``
    - ``9``
    - The background request is not currently allowed due to platform policy.

      .. _enumitem_HttpRequest_TooManyRedirectsError:
  * - ``HttpRequest.TooManyRedirectsError``
    - ``10``
    - While following redirects, the maximum limit was reached. The limit is by default set to 50.

      .. _enumitem_HttpRequest_InsecureRedirectError:
  * - ``HttpRequest.InsecureRedirectError``
    - ``11``
    - while following redirects, the HTTP client detected a redirect from a encrypted protocol (https) to an unencrypted.

      .. _enumitem_HttpRequest_UnknownNetworkError:
  * - ``HttpRequest.UnknownNetworkError``
    - ``99``
    - An unknown network-related error was detected.

      .. _enumitem_HttpRequest_ProxyConnectionRefusedError:
  * - ``HttpRequest.ProxyConnectionRefusedError``
    - ``101``
    - The connection to the proxy server was refused (the proxy server is not accepting requests).

      .. _enumitem_HttpRequest_ProxyConnectionClosedError:
  * - ``HttpRequest.ProxyConnectionClosedError``
    - ``102``
    - The proxy server closed the connection prematurely, before the entire response was received and processed.

      .. _enumitem_HttpRequest_ProxyNotFoundError:
  * - ``HttpRequest.ProxyNotFoundError``
    - ``103``
    - The proxy host name was not found (invalid proxy hostname).

      .. _enumitem_HttpRequest_ProxyTimeoutError:
  * - ``HttpRequest.ProxyTimeoutError``
    - ``104``
    - The connection to the proxy timed out or the proxy did not reply in time to the request sent.

      .. _enumitem_HttpRequest_ProxyAuthenticationRequiredError:
  * - ``HttpRequest.ProxyAuthenticationRequiredError``
    - ``105``
    - The proxy requires authentication in order to honour the request but did not accept any credentials offered (if any).

      .. _enumitem_HttpRequest_UnknownProxyError:
  * - ``HttpRequest.UnknownProxyError``
    - ``199``
    - An unknown proxy-related error was detected.

      .. _enumitem_HttpRequest_ContentAccessDenied:
  * - ``HttpRequest.ContentAccessDenied``
    - ``201``
    - The access to the remote content was denied (similar to HTTP error 403).

      .. _enumitem_HttpRequest_ContentOperationNotPermittedError:
  * - ``HttpRequest.ContentOperationNotPermittedError``
    - ``202``
    - The operation requested on the remote content is not permitted.

      .. _enumitem_HttpRequest_ContentNotFoundError:
  * - ``HttpRequest.ContentNotFoundError``
    - ``203``
    - The remote content was not found at the server (similar to HTTP error 404).

      .. _enumitem_HttpRequest_AuthenticationRequiredError:
  * - ``HttpRequest.AuthenticationRequiredError``
    - ``204``
    - The remote server requires authentication to serve the content but the credentials provided were not accepted (if any).

      .. _enumitem_HttpRequest_ContentReSendError:
  * - ``HttpRequest.ContentReSendError``
    - ``205``
    - The request needed to be sent again, but this failed for example because the upload data could not be read a second time.

      .. _enumitem_HttpRequest_ContentConflictError:
  * - ``HttpRequest.ContentConflictError``
    - ``206``
    - The request could not be completed due to a conflict with the current state of the resource.

      .. _enumitem_HttpRequest_ContentGoneError:
  * - ``HttpRequest.ContentGoneError``
    - ``207``
    - The requested resource is no longer available at the server.

      .. _enumitem_HttpRequest_UnknownContentError:
  * - ``HttpRequest.UnknownContentError``
    - ``299``
    - An unknown error related to the remote content was detected.

      .. _enumitem_HttpRequest_ProtocolUnknownError:
  * - ``HttpRequest.ProtocolUnknownError``
    - ``301``
    - The HTTP client cannot honor the request because the protocol is not known.

      .. _enumitem_HttpRequest_ProtocolInvalidOperationError:
  * - ``HttpRequest.ProtocolInvalidOperationError``
    - ``302``
    - The requested operation is invalid for this protocol.

      .. _enumitem_HttpRequest_ProtocolFailure:
  * - ``HttpRequest.ProtocolFailure``
    - ``399``
    - A breakdown in protocol was detected (parsing error, invalid or unexpected responses, etc.).

      .. _enumitem_HttpRequest_InternalServerError:
  * - ``HttpRequest.InternalServerError``
    - ``401``
    - The server encountered an unexpected condition which prevented it from fulfilling the request.

      .. _enumitem_HttpRequest_OperationNotImplementedError:
  * - ``HttpRequest.OperationNotImplementedError``
    - ``402``
    - The server does not support the functionality required to fulfill the request.

      .. _enumitem_HttpRequest_ServiceUnavailableError:
  * - ``HttpRequest.ServiceUnavailableError``
    - ``403``
    - The server is unable to handle the request at this time.

      .. _enumitem_HttpRequest_UnknownServerError:
  * - ``HttpRequest.UnknownServerError``
    - ``499``
    - An unknown error related to the server response was detected.


.. _example_HttpRequest:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.9
    import InCore.Http 2.9
    
    Application {
    
        HttpRequest {
            id: simpleRequest
            url: "https://www.inhub.de/"
        }
    
        HttpRequest {
            id: postTest
            url: "https://httpbin.org/post"
            content: HttpContent {
                type: HttpContent.PlainText
                data: "InCore.Http POST Example"
            }
            onResponseReceived: console.log("Response for POST:", response.statusCode, response.content.data["data"])
        }
    
        HttpRequest {
            id: putTest
            url: "https://httpbin.org/put"
            content: HttpContent {
                type: HttpContent.PlainText
                data: "InCore.Http PUT Example"
            }
            response.autoDetectDataTypeFromContentType: false
            onResponseReceived: console.log("Response for PUT:", response.statusCode, response.content.data)
        }
    
        onCompleted: {
            simpleRequest.get((response) => console.log("Response for GET:", response.statusCode, response.content.data))
            postTest.post()
            putTest.put()
        }
    }
    