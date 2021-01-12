
.. _object_HttpResponse:


:index:`HttpResponse`
---------------------

Description
***********

The HttpResponse object represents a HTTP response received from a HTTP server. It usually is associated with the corresponding :ref:`HttpRequest <object_HttpRequest>` object in the :ref:`HttpRequest.response <property_HttpRequest_response>` property. After a :ref:`HttpResponse <object_HttpResponse>` has been received, it's :ref:`statusCode <property_HttpResponse_statusCode>` should be checked to ensure the desired result. If succesful the :ref:`content <property_HttpResponse_content>` property holds the received data.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`autoDetectDataTypeFromContentType <property_HttpResponse_autoDetectDataTypeFromContentType>`
  * :ref:`connectionEncrypted <property_HttpResponse_connectionEncrypted>`
  * :ref:`content <property_HttpResponse_content>`
  * :ref:`headers <property_HttpResponse_headers>`
  * :ref:`originalContentLength <property_HttpResponse_originalContentLength>`
  * :ref:`pipeliningWasUsed <property_HttpResponse_pipeliningWasUsed>`
  * :ref:`reasonPhrase <property_HttpResponse_reasonPhrase>`
  * :ref:`redirectionTarget <property_HttpResponse_redirectionTarget>`
  * :ref:`statusCode <property_HttpResponse_statusCode>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`wait() <method_HttpResponse_wait>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`headersDataChanged() <signal_HttpResponse_headersDataChanged>`
  * :ref:`received() <signal_HttpResponse_received>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`StatusCode <enum_HttpResponse_StatusCode>`



Properties
**********


.. _property_HttpResponse_autoDetectDataTypeFromContentType:

.. _signal_HttpResponse_autoDetectDataTypeFromContentTypeChanged:

.. index::
   single: autoDetectDataTypeFromContentType

autoDetectDataTypeFromContentType
+++++++++++++++++++++++++++++++++

This property holds whether to automatically detect the data type from the received content type header if any. If disabled, the received data is treated as if it had the configured type.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: autoDetectDataTypeFromContentTypeChanged()
:**› Attributes**: Writable


.. _property_HttpResponse_connectionEncrypted:

.. _signal_HttpResponse_connectionEncryptedChanged:

.. index::
   single: connectionEncrypted

connectionEncrypted
+++++++++++++++++++

This property holds Indicates whether the data was obtained through an encrypted (secure) connection.

:**› Type**: Boolean
:**› Signal**: connectionEncryptedChanged()
:**› Attributes**: Readonly


.. _property_HttpResponse_content:

.. _signal_HttpResponse_contentChanged:

.. index::
   single: content

content
+++++++

This property holds the content received from the server.

:**› Type**: :ref:`HttpContent <object_HttpContent>`
:**› Signal**: contentChanged()
:**› Attributes**: Writable


.. _property_HttpResponse_headers:

.. _signal_HttpResponse_headersChanged:

.. index::
   single: headers

headers
+++++++

This property holds a list of header objects representing the HTTP headers received from the server.

:**› Type**: :ref:`List <object_List>`\<:ref:`HttpHeader <object_HttpHeader>`>
:**› Signal**: headersChanged()
:**› Attributes**: Readonly


.. _property_HttpResponse_originalContentLength:

.. _signal_HttpResponse_originalContentLengthChanged:

.. index::
   single: originalContentLength

originalContentLength
+++++++++++++++++++++

This property holds the original content-length attribute before being invalidated and removed from the header when the data is compressed and the request was marked to be decompressed automatically.

:**› Type**: SignedBigInteger
:**› Signal**: originalContentLengthChanged()
:**› Attributes**: Readonly


.. _property_HttpResponse_pipeliningWasUsed:

.. _signal_HttpResponse_pipeliningWasUsedChanged:

.. index::
   single: pipeliningWasUsed

pipeliningWasUsed
+++++++++++++++++

This property holds whether the HTTP pipelining was used for receiving this response.

:**› Type**: Boolean
:**› Signal**: pipeliningWasUsedChanged()
:**› Attributes**: Readonly


.. _property_HttpResponse_reasonPhrase:

.. _signal_HttpResponse_reasonPhraseChanged:

.. index::
   single: reasonPhrase

reasonPhrase
++++++++++++

This property holds the HTTP reason phrase as received from the HTTP server (like "Ok", "Found", "Not Found", "Access Denied", etc.) This is the human-readable representation of the status code (see :ref:`statusCode <property_HttpResponse_statusCode>`).

:**› Type**: String
:**› Signal**: reasonPhraseChanged()
:**› Attributes**: Readonly


.. _property_HttpResponse_redirectionTarget:

.. _signal_HttpResponse_redirectionTargetChanged:

.. index::
   single: redirectionTarget

redirectionTarget
+++++++++++++++++

This property holds that the server is redirecting the request to a different URL. The API does not by default follow redirections: the application can determine if the requested redirection should be allowed, according to its security policies, or it can set :ref:`HttpRequest.followRedirects <property_HttpRequest_followRedirects>` to ``true`` (in which case the redirection will be followed and this attribute will be empty in the response). The returned URL might be relative.

:**› Type**: String
:**› Signal**: redirectionTargetChanged()
:**› Attributes**: Readonly


.. _property_HttpResponse_statusCode:

.. _signal_HttpResponse_statusCodeChanged:

.. index::
   single: statusCode

statusCode
++++++++++

This property holds the HTTP status code received from the HTTP server such as 200, 404 etc. See the :ref:`StatusCode <enum_HttpResponse_StatusCode>` enumeration for details.

:**› Type**: :ref:`StatusCode <enum_HttpResponse_StatusCode>`
:**› Signal**: statusCodeChanged()
:**› Attributes**: Readonly

Methods
*******


.. _method_HttpResponse_wait:

.. index::
   single: wait

wait(SignedInteger msecs)
+++++++++++++++++++++++++

This method blocks until the HTTP response has been received. This method will timeout after `msecs` milliseconds. In most cases the asynchronuous :ref:`received() <signal_HttpResponse_received>` signal should be used instead of this synchronuous method.

:**› Returns**: Boolean


Signals
*******


.. _signal_HttpResponse_headersDataChanged:

.. index::
   single: headersDataChanged

headersDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`headers <property_HttpResponse_headers>` list itself emitted the dataChanged() signal.



.. _signal_HttpResponse_received:

.. index::
   single: received

received()
++++++++++

This signal is emitted when a response is received for the corresponding request and all properties have been updated with the received data.


Enumerations
************


.. _enum_HttpResponse_StatusCode:

.. index::
   single: StatusCode

StatusCode
++++++++++

This enumeration describes all available Hypertext Transfer Protocol (HTTP) response status codes. Status codes are issued by a server in response to a client's request made to the server.

.. index::
   single: HttpResponse.InvalidStatus
.. index::
   single: HttpResponse.Continue
.. index::
   single: HttpResponse.SwitchingProtocols
.. index::
   single: HttpResponse.Processing
.. index::
   single: HttpResponse.OK
.. index::
   single: HttpResponse.Created
.. index::
   single: HttpResponse.Accepted
.. index::
   single: HttpResponse.NonAuthoritativeInformation
.. index::
   single: HttpResponse.NoContent
.. index::
   single: HttpResponse.ResetContent
.. index::
   single: HttpResponse.PartialContent
.. index::
   single: HttpResponse.MultiStatus
.. index::
   single: HttpResponse.AlreadyReported
.. index::
   single: HttpResponse.IMUsed
.. index::
   single: HttpResponse.MultipleChoices
.. index::
   single: HttpResponse.MovedPermanently
.. index::
   single: HttpResponse.Found
.. index::
   single: HttpResponse.SeeOther
.. index::
   single: HttpResponse.NotModified
.. index::
   single: HttpResponse.UseProxy
.. index::
   single: HttpResponse.TemporaryRedirect
.. index::
   single: HttpResponse.PermanentRedirect
.. index::
   single: HttpResponse.BadRequest
.. index::
   single: HttpResponse.Unauthorized
.. index::
   single: HttpResponse.PaymentRequired
.. index::
   single: HttpResponse.Forbidden
.. index::
   single: HttpResponse.NotFound
.. index::
   single: HttpResponse.MethodNotAllowed
.. index::
   single: HttpResponse.NotAcceptable
.. index::
   single: HttpResponse.ProxyAuthenticationRequired
.. index::
   single: HttpResponse.RequestTimeout
.. index::
   single: HttpResponse.Conflict
.. index::
   single: HttpResponse.Gone
.. index::
   single: HttpResponse.LengthRequired
.. index::
   single: HttpResponse.PreconditionFailed
.. index::
   single: HttpResponse.RequestEntityTooLarge
.. index::
   single: HttpResponse.URITooLong
.. index::
   single: HttpResponse.UnsupportedMediaType
.. index::
   single: HttpResponse.RequestedRangeNotSatisfiable
.. index::
   single: HttpResponse.ExpectationFailed
.. index::
   single: HttpResponse.PolicyNotFulfilled
.. index::
   single: HttpResponse.MisdirectedRequest
.. index::
   single: HttpResponse.UnprocessableEntity
.. index::
   single: HttpResponse.Locked
.. index::
   single: HttpResponse.FailedDependency
.. index::
   single: HttpResponse.UpgradeRequired
.. index::
   single: HttpResponse.PreconditionRequired
.. index::
   single: HttpResponse.TooManyRequests
.. index::
   single: HttpResponse.RequestHeaderFieldsTooLarge
.. index::
   single: HttpResponse.UnavailableForLegalReasons
.. index::
   single: HttpResponse.InternalServerError
.. index::
   single: HttpResponse.NotImplemented
.. index::
   single: HttpResponse.BadGateway
.. index::
   single: HttpResponse.ServiceUnavailable
.. index::
   single: HttpResponse.GatewayTimeout
.. index::
   single: HttpResponse.HttpVersionNotSupported
.. index::
   single: HttpResponse.VariantAlsoNegotiates
.. index::
   single: HttpResponse.InsufficientStorage
.. index::
   single: HttpResponse.LoopDetected
.. index::
   single: HttpResponse.NotExtended
.. index::
   single: HttpResponse.NetworkAuthenticationRequired
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_HttpResponse_InvalidStatus:
  * - ``HttpResponse.InvalidStatus``
    - ``-1``
    - Invalid status code, only internal use.

      .. _enumitem_HttpResponse_Continue:
  * - ``HttpResponse.Continue``
    - ``100``
    - See `details on status code 100 <https://tools.ietf.org/html/rfc2616#section-10.1.1>`_ .

      .. _enumitem_HttpResponse_SwitchingProtocols:
  * - ``HttpResponse.SwitchingProtocols``
    - ``101``
    - See `details on status code 101 <https://tools.ietf.org/html/rfc2616#section-10.1.2>`_ .

      .. _enumitem_HttpResponse_Processing:
  * - ``HttpResponse.Processing``
    - ``102``
    - See `details on status code 102 <https://tools.ietf.org/html/rfc2518#section-10.1>`_ .

      .. _enumitem_HttpResponse_OK:
  * - ``HttpResponse.OK``
    - ``200``
    - See `details on status code 200 <https://tools.ietf.org/html/rfc2616#section-10.2.1>`_ .

      .. _enumitem_HttpResponse_Created:
  * - ``HttpResponse.Created``
    - ``201``
    - See `details on status code 201 <https://tools.ietf.org/html/rfc2616#section-10.2.2>`_ .

      .. _enumitem_HttpResponse_Accepted:
  * - ``HttpResponse.Accepted``
    - ``202``
    - See `details on status code 202 <https://tools.ietf.org/html/rfc2616#section-10.2.3>`_ .

      .. _enumitem_HttpResponse_NonAuthoritativeInformation:
  * - ``HttpResponse.NonAuthoritativeInformation``
    - ``203``
    - See `details on status code 203 <https://tools.ietf.org/html/rfc2616#section-10.2.4>`_ .

      .. _enumitem_HttpResponse_NoContent:
  * - ``HttpResponse.NoContent``
    - ``204``
    - See `details on status code 204 <https://tools.ietf.org/html/rfc2616#section-10.2.5>`_ .

      .. _enumitem_HttpResponse_ResetContent:
  * - ``HttpResponse.ResetContent``
    - ``205``
    - See `details on status code 205 <https://tools.ietf.org/html/rfc2616#section-10.2.6>`_ .

      .. _enumitem_HttpResponse_PartialContent:
  * - ``HttpResponse.PartialContent``
    - ``206``
    - See `details on status code 206 <https://tools.ietf.org/html/rfc2616#section-10.2.7>`_ .

      .. _enumitem_HttpResponse_MultiStatus:
  * - ``HttpResponse.MultiStatus``
    - ``207``
    - See `details on status code 207 <https://tools.ietf.org/html/rfc2518#section-10.2>`_ .

      .. _enumitem_HttpResponse_AlreadyReported:
  * - ``HttpResponse.AlreadyReported``
    - ``208``
    - See `details on status code 208 <https://tools.ietf.org/html/rfc5842#section-7.1>`_ .

      .. _enumitem_HttpResponse_IMUsed:
  * - ``HttpResponse.IMUsed``
    - ``226``
    - See `details on status code 226 <https://tools.ietf.org/html/rfc3229#section-10.4.1>`_ .

      .. _enumitem_HttpResponse_MultipleChoices:
  * - ``HttpResponse.MultipleChoices``
    - ``300``
    - See `details on status code 300 <https://tools.ietf.org/html/rfc2616#section-10.3.1>`_ .

      .. _enumitem_HttpResponse_MovedPermanently:
  * - ``HttpResponse.MovedPermanently``
    - ``301``
    - See `details on status code 301 <https://tools.ietf.org/html/rfc2616#section-10.3.2>`_ .

      .. _enumitem_HttpResponse_Found:
  * - ``HttpResponse.Found``
    - ``302``
    - See `details on status code 302 <https://tools.ietf.org/html/rfc2616#section-10.3.2>`_ .

      .. _enumitem_HttpResponse_SeeOther:
  * - ``HttpResponse.SeeOther``
    - ``303``
    - See `details on status code 303 <https://tools.ietf.org/html/rfc2616#section-10.3.4>`_ .

      .. _enumitem_HttpResponse_NotModified:
  * - ``HttpResponse.NotModified``
    - ``304``
    - See `details on status code 304 <https://tools.ietf.org/html/rfc2616#section-10.3.5>`_ .

      .. _enumitem_HttpResponse_UseProxy:
  * - ``HttpResponse.UseProxy``
    - ``305``
    - See `details on status code 305 <https://tools.ietf.org/html/rfc2616#section-10.3.6>`_ .

      .. _enumitem_HttpResponse_TemporaryRedirect:
  * - ``HttpResponse.TemporaryRedirect``
    - ``307``
    - See `details on status code 307 <https://tools.ietf.org/html/rfc2616#section-10.3.8>`_ .

      .. _enumitem_HttpResponse_PermanentRedirect:
  * - ``HttpResponse.PermanentRedirect``
    - ``308``
    - See `details on status code 308 <https://tools.ietf.org/html/rfc7538>`_ .

      .. _enumitem_HttpResponse_BadRequest:
  * - ``HttpResponse.BadRequest``
    - ``400``
    - See `details on status code 400 <https://tools.ietf.org/html/rfc2616#section-10.4.1>`_ .

      .. _enumitem_HttpResponse_Unauthorized:
  * - ``HttpResponse.Unauthorized``
    - ``401``
    - See `details on status code 401 <https://tools.ietf.org/html/rfc2616#section-10.4.2>`_ .

      .. _enumitem_HttpResponse_PaymentRequired:
  * - ``HttpResponse.PaymentRequired``
    - ``402``
    - See `details on status code 402 <https://tools.ietf.org/html/rfc2616#section-10.4.3>`_ .

      .. _enumitem_HttpResponse_Forbidden:
  * - ``HttpResponse.Forbidden``
    - ``403``
    - See `details on status code 403 <https://tools.ietf.org/html/rfc2616#section-10.4.4>`_ .

      .. _enumitem_HttpResponse_NotFound:
  * - ``HttpResponse.NotFound``
    - ``404``
    - See `details on status code 404 <https://tools.ietf.org/html/rfc2616#section-10.4.5>`_ .

      .. _enumitem_HttpResponse_MethodNotAllowed:
  * - ``HttpResponse.MethodNotAllowed``
    - ``405``
    - See `details on status code 405 <https://tools.ietf.org/html/rfc2616#section-10.4.6>`_ .

      .. _enumitem_HttpResponse_NotAcceptable:
  * - ``HttpResponse.NotAcceptable``
    - ``406``
    - See `details on status code 406 <https://tools.ietf.org/html/rfc2616#section-10.4.7>`_ .

      .. _enumitem_HttpResponse_ProxyAuthenticationRequired:
  * - ``HttpResponse.ProxyAuthenticationRequired``
    - ``407``
    - See `details on status code 407 <https://tools.ietf.org/html/rfc2616#section-10.4.8>`_ .

      .. _enumitem_HttpResponse_RequestTimeout:
  * - ``HttpResponse.RequestTimeout``
    - ``408``
    - See `details on status code 408 <https://tools.ietf.org/html/rfc2616#section-10.4.9>`_ .

      .. _enumitem_HttpResponse_Conflict:
  * - ``HttpResponse.Conflict``
    - ``409``
    - See `details on status code 409 <https://tools.ietf.org/html/rfc2616#section-10.4.10>`_ .

      .. _enumitem_HttpResponse_Gone:
  * - ``HttpResponse.Gone``
    - ``410``
    - See `details on status code 410 <https://tools.ietf.org/html/rfc2616#section-10.4.11>`_ .

      .. _enumitem_HttpResponse_LengthRequired:
  * - ``HttpResponse.LengthRequired``
    - ``411``
    - See `details on status code 411 <https://tools.ietf.org/html/rfc2616#section-10.4.12>`_ .

      .. _enumitem_HttpResponse_PreconditionFailed:
  * - ``HttpResponse.PreconditionFailed``
    - ``412``
    - See `details on status code 412 <https://tools.ietf.org/html/rfc2616#section-10.4.13>`_ .

      .. _enumitem_HttpResponse_RequestEntityTooLarge:
  * - ``HttpResponse.RequestEntityTooLarge``
    - ``413``
    - See `details on status code 413 <https://tools.ietf.org/html/rfc2616#section-10.4.14>`_ .

      .. _enumitem_HttpResponse_URITooLong:
  * - ``HttpResponse.URITooLong``
    - ``414``
    - See `details on status code 414 <https://tools.ietf.org/html/rfc2616#section-10.4.15>`_ .

      .. _enumitem_HttpResponse_UnsupportedMediaType:
  * - ``HttpResponse.UnsupportedMediaType``
    - ``415``
    - See `details on status code 415 <https://tools.ietf.org/html/rfc2616#section-10.4.16>`_ .

      .. _enumitem_HttpResponse_RequestedRangeNotSatisfiable:
  * - ``HttpResponse.RequestedRangeNotSatisfiable``
    - ``416``
    - See `details on status code 416 <https://tools.ietf.org/html/rfc2616#section-10.4.17>`_ .

      .. _enumitem_HttpResponse_ExpectationFailed:
  * - ``HttpResponse.ExpectationFailed``
    - ``417``
    - See `details on status code 417 <https://tools.ietf.org/html/rfc2616#section-10.4.18>`_ .

      .. _enumitem_HttpResponse_PolicyNotFulfilled:
  * - ``HttpResponse.PolicyNotFulfilled``
    - ``420``
    - See `details on status code 420 <https://www.w3.org/TR/WD-http-pep-971121.html#_Toc404743960>`_ .

      .. _enumitem_HttpResponse_MisdirectedRequest:
  * - ``HttpResponse.MisdirectedRequest``
    - ``421``
    - See `details on status code 421 <https://tools.ietf.org/html/rfc7540#section-9.1.2>`_ .

      .. _enumitem_HttpResponse_UnprocessableEntity:
  * - ``HttpResponse.UnprocessableEntity``
    - ``422``
    - See `details on status code 422 <https://tools.ietf.org/html/rfc2518#section-10.3>`_ .

      .. _enumitem_HttpResponse_Locked:
  * - ``HttpResponse.Locked``
    - ``423``
    - See `details on status code 423 <https://tools.ietf.org/html/rfc2518#section-10.4>`_ .

      .. _enumitem_HttpResponse_FailedDependency:
  * - ``HttpResponse.FailedDependency``
    - ``424``
    - See `details on status code 424 <https://tools.ietf.org/html/rfc2518#section-10.5>`_ .

      .. _enumitem_HttpResponse_UpgradeRequired:
  * - ``HttpResponse.UpgradeRequired``
    - ``426``
    - See `details on status code 426 <https://tools.ietf.org/html/rfc2817>`_ .

      .. _enumitem_HttpResponse_PreconditionRequired:
  * - ``HttpResponse.PreconditionRequired``
    - ``428``
    - See `details on status code 428 <https://tools.ietf.org/html/rfc6585#section-3>`_ .

      .. _enumitem_HttpResponse_TooManyRequests:
  * - ``HttpResponse.TooManyRequests``
    - ``429``
    - See `details on status code 429 <https://tools.ietf.org/html/rfc6585#section-4>`_ .

      .. _enumitem_HttpResponse_RequestHeaderFieldsTooLarge:
  * - ``HttpResponse.RequestHeaderFieldsTooLarge``
    - ``431``
    - See `details on status code 431 <https://tools.ietf.org/html/rfc6585#section-5>`_ .

      .. _enumitem_HttpResponse_UnavailableForLegalReasons:
  * - ``HttpResponse.UnavailableForLegalReasons``
    - ``451``
    - See `details on status code 451 <https://tools.ietf.org/html/draft-tbray-http-legally-restricted-status-00#section-3>`_ .

      .. _enumitem_HttpResponse_InternalServerError:
  * - ``HttpResponse.InternalServerError``
    - ``500``
    - See `details on status code 500 <https://tools.ietf.org/html/rfc2616#section-10.5.1>`_ .

      .. _enumitem_HttpResponse_NotImplemented:
  * - ``HttpResponse.NotImplemented``
    - ``501``
    - See `details on status code 501 <https://tools.ietf.org/html/rfc2616#section-10.5.2>`_ .

      .. _enumitem_HttpResponse_BadGateway:
  * - ``HttpResponse.BadGateway``
    - ``502``
    - See `details on status code 502 <https://tools.ietf.org/html/rfc2616#section-10.5.3>`_ .

      .. _enumitem_HttpResponse_ServiceUnavailable:
  * - ``HttpResponse.ServiceUnavailable``
    - ``503``
    - See `details on status code 503 <https://tools.ietf.org/html/rfc2616#section-10.5.4>`_ .

      .. _enumitem_HttpResponse_GatewayTimeout:
  * - ``HttpResponse.GatewayTimeout``
    - ``504``
    - See `details on status code 504 <https://tools.ietf.org/html/rfc2616#section-10.5.5>`_ .

      .. _enumitem_HttpResponse_HttpVersionNotSupported:
  * - ``HttpResponse.HttpVersionNotSupported``
    - ``505``
    - See `details on status code 505 <https://tools.ietf.org/html/rfc2616#section-10.5.6>`_ .

      .. _enumitem_HttpResponse_VariantAlsoNegotiates:
  * - ``HttpResponse.VariantAlsoNegotiates``
    - ``506``
    - See `details on status code 506 <https://tools.ietf.org/html/rfc2295#section-8.1>`_ .

      .. _enumitem_HttpResponse_InsufficientStorage:
  * - ``HttpResponse.InsufficientStorage``
    - ``507``
    - See `details on status code 507 <https://tools.ietf.org/html/rfc4918#section-11.5>`_ .

      .. _enumitem_HttpResponse_LoopDetected:
  * - ``HttpResponse.LoopDetected``
    - ``508``
    - See `details on status code 508 <https://tools.ietf.org/html/rfc5842#section-7.2>`_ .

      .. _enumitem_HttpResponse_NotExtended:
  * - ``HttpResponse.NotExtended``
    - ``510``
    - See `details on status code 510 <https://tools.ietf.org/html/rfc2774#section-7>`_ .

      .. _enumitem_HttpResponse_NetworkAuthenticationRequired:
  * - ``HttpResponse.NetworkAuthenticationRequired``
    - ``511``
    - See `details on status code 511 <https://tools.ietf.org/html/rfc6585#section-6>`_ .

Example
*******
See :ref:`HttpRequest example <example_HttpRequest>` on how to use HttpResponse.
