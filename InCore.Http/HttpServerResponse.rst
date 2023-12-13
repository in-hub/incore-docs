
.. _object_HttpServerResponse:


:index:`HttpServerResponse`
---------------------------

Description
***********

The HttpServerResponse object represents a HTTP response sent from a :ref:`HttpServer <object_HttpServer>` object back to the client.


Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`content <property_HttpServerResponse_content>`
  * :ref:`headers <property_HttpServerResponse_headers>`
  * :ref:`mimeType <property_HttpServerResponse_mimeType>`
  * :ref:`statusCode <property_HttpServerResponse_statusCode>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`StatusCode <enum_HttpServerResponse_StatusCode>`



Properties
**********


.. _property_HttpServerResponse_content:

.. _signal_HttpServerResponse_contentChanged:

.. index::
   single: content

content
+++++++

This property holds the content which to serve in the response.

:**› Type**: :ref:`HttpContent <object_HttpContent>`
:**› Signal**: contentChanged()
:**› Attributes**: Writable


.. _property_HttpServerResponse_headers:

.. _signal_HttpServerResponse_headersChanged:

.. index::
   single: headers

headers
+++++++

This property holds the headers which to send with the response.

:**› Type**: Map
:**› Signal**: headersChanged()
:**› Attributes**: Writable


.. _property_HttpServerResponse_mimeType:

.. _signal_HttpServerResponse_mimeTypeChanged:

.. index::
   single: mimeType

mimeType
++++++++

This property holds the MIME type of the response data.

:**› Type**: String
:**› Signal**: mimeTypeChanged()
:**› Attributes**: Writable


.. _property_HttpServerResponse_statusCode:

.. _signal_HttpServerResponse_statusCodeChanged:

.. index::
   single: statusCode

statusCode
++++++++++

This property holds the HTTP status code of the response such as 200, 404 etc. See the :ref:`StatusCode <enum_HttpServerResponse_StatusCode>` enumeration for details.

:**› Type**: :ref:`StatusCode <enum_HttpServerResponse_StatusCode>`
:**› Default**: :ref:`HttpServerResponse.OK <enumitem_HttpServerResponse_OK>`
:**› Signal**: statusCodeChanged()
:**› Attributes**: Writable

Enumerations
************


.. _enum_HttpServerResponse_StatusCode:

.. index::
   single: StatusCode

StatusCode
++++++++++

This enumeration describes all available Hypertext Transfer Protocol (HTTP) response status codes. Status codes are issued by a server in response to a client's request made to the server.

.. index::
   single: HttpServerResponse.Continue
.. index::
   single: HttpServerResponse.SwitchingProtocols
.. index::
   single: HttpServerResponse.Processing
.. index::
   single: HttpServerResponse.OK
.. index::
   single: HttpServerResponse.Created
.. index::
   single: HttpServerResponse.Accepted
.. index::
   single: HttpServerResponse.NonAuthoritativeInformation
.. index::
   single: HttpServerResponse.NoContent
.. index::
   single: HttpServerResponse.ResetContent
.. index::
   single: HttpServerResponse.PartialContent
.. index::
   single: HttpServerResponse.MultiStatus
.. index::
   single: HttpServerResponse.AlreadyReported
.. index::
   single: HttpServerResponse.IMUsed
.. index::
   single: HttpServerResponse.MultipleChoices
.. index::
   single: HttpServerResponse.MovedPermanently
.. index::
   single: HttpServerResponse.Found
.. index::
   single: HttpServerResponse.SeeOther
.. index::
   single: HttpServerResponse.NotModified
.. index::
   single: HttpServerResponse.UseProxy
.. index::
   single: HttpServerResponse.TemporaryRedirect
.. index::
   single: HttpServerResponse.PermanentRedirect
.. index::
   single: HttpServerResponse.BadRequest
.. index::
   single: HttpServerResponse.Unauthorized
.. index::
   single: HttpServerResponse.PaymentRequired
.. index::
   single: HttpServerResponse.Forbidden
.. index::
   single: HttpServerResponse.NotFound
.. index::
   single: HttpServerResponse.MethodNotAllowed
.. index::
   single: HttpServerResponse.NotAcceptable
.. index::
   single: HttpServerResponse.ProxyAuthenticationRequired
.. index::
   single: HttpServerResponse.RequestTimeout
.. index::
   single: HttpServerResponse.Conflict
.. index::
   single: HttpServerResponse.Gone
.. index::
   single: HttpServerResponse.LengthRequired
.. index::
   single: HttpServerResponse.PreconditionFailed
.. index::
   single: HttpServerResponse.RequestEntityTooLarge
.. index::
   single: HttpServerResponse.URITooLong
.. index::
   single: HttpServerResponse.UnsupportedMediaType
.. index::
   single: HttpServerResponse.RequestedRangeNotSatisfiable
.. index::
   single: HttpServerResponse.ExpectationFailed
.. index::
   single: HttpServerResponse.PolicyNotFulfilled
.. index::
   single: HttpServerResponse.MisdirectedRequest
.. index::
   single: HttpServerResponse.UnprocessableEntity
.. index::
   single: HttpServerResponse.Locked
.. index::
   single: HttpServerResponse.FailedDependency
.. index::
   single: HttpServerResponse.UpgradeRequired
.. index::
   single: HttpServerResponse.PreconditionRequired
.. index::
   single: HttpServerResponse.TooManyRequests
.. index::
   single: HttpServerResponse.RequestHeaderFieldsTooLarge
.. index::
   single: HttpServerResponse.UnavailableForLegalReasons
.. index::
   single: HttpServerResponse.InternalServerError
.. index::
   single: HttpServerResponse.NotImplemented
.. index::
   single: HttpServerResponse.BadGateway
.. index::
   single: HttpServerResponse.ServiceUnavailable
.. index::
   single: HttpServerResponse.GatewayTimeout
.. index::
   single: HttpServerResponse.HttpVersionNotSupported
.. index::
   single: HttpServerResponse.VariantAlsoNegotiates
.. index::
   single: HttpServerResponse.InsufficientStorage
.. index::
   single: HttpServerResponse.LoopDetected
.. index::
   single: HttpServerResponse.NotExtended
.. index::
   single: HttpServerResponse.NetworkAuthenticationRequired
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_HttpServerResponse_Continue:
  * - ``HttpServerResponse.Continue``
    - ``100``
    - See `details on status code 100 <https://tools.ietf.org/html/rfc2616#section-10.1.1>`_ .

      .. _enumitem_HttpServerResponse_SwitchingProtocols:
  * - ``HttpServerResponse.SwitchingProtocols``
    - ``101``
    - See `details on status code 101 <https://tools.ietf.org/html/rfc2616#section-10.1.2>`_ .

      .. _enumitem_HttpServerResponse_Processing:
  * - ``HttpServerResponse.Processing``
    - ``102``
    - See `details on status code 102 <https://tools.ietf.org/html/rfc2518#section-10.1>`_ .

      .. _enumitem_HttpServerResponse_OK:
  * - ``HttpServerResponse.OK``
    - ``200``
    - See `details on status code 200 <https://tools.ietf.org/html/rfc2616#section-10.2.1>`_ .

      .. _enumitem_HttpServerResponse_Created:
  * - ``HttpServerResponse.Created``
    - ``201``
    - See `details on status code 201 <https://tools.ietf.org/html/rfc2616#section-10.2.2>`_ .

      .. _enumitem_HttpServerResponse_Accepted:
  * - ``HttpServerResponse.Accepted``
    - ``202``
    - See `details on status code 202 <https://tools.ietf.org/html/rfc2616#section-10.2.3>`_ .

      .. _enumitem_HttpServerResponse_NonAuthoritativeInformation:
  * - ``HttpServerResponse.NonAuthoritativeInformation``
    - ``203``
    - See `details on status code 203 <https://tools.ietf.org/html/rfc2616#section-10.2.4>`_ .

      .. _enumitem_HttpServerResponse_NoContent:
  * - ``HttpServerResponse.NoContent``
    - ``204``
    - See `details on status code 204 <https://tools.ietf.org/html/rfc2616#section-10.2.5>`_ .

      .. _enumitem_HttpServerResponse_ResetContent:
  * - ``HttpServerResponse.ResetContent``
    - ``205``
    - See `details on status code 205 <https://tools.ietf.org/html/rfc2616#section-10.2.6>`_ .

      .. _enumitem_HttpServerResponse_PartialContent:
  * - ``HttpServerResponse.PartialContent``
    - ``206``
    - See `details on status code 206 <https://tools.ietf.org/html/rfc2616#section-10.2.7>`_ .

      .. _enumitem_HttpServerResponse_MultiStatus:
  * - ``HttpServerResponse.MultiStatus``
    - ``207``
    - See `details on status code 207 <https://tools.ietf.org/html/rfc2518#section-10.2>`_ .

      .. _enumitem_HttpServerResponse_AlreadyReported:
  * - ``HttpServerResponse.AlreadyReported``
    - ``208``
    - See `details on status code 208 <https://tools.ietf.org/html/rfc5842#section-7.1>`_ .

      .. _enumitem_HttpServerResponse_IMUsed:
  * - ``HttpServerResponse.IMUsed``
    - ``226``
    - See `details on status code 226 <https://tools.ietf.org/html/rfc3229#section-10.4.1>`_ .

      .. _enumitem_HttpServerResponse_MultipleChoices:
  * - ``HttpServerResponse.MultipleChoices``
    - ``300``
    - See `details on status code 300 <https://tools.ietf.org/html/rfc2616#section-10.3.1>`_ .

      .. _enumitem_HttpServerResponse_MovedPermanently:
  * - ``HttpServerResponse.MovedPermanently``
    - ``301``
    - See `details on status code 301 <https://tools.ietf.org/html/rfc2616#section-10.3.2>`_ .

      .. _enumitem_HttpServerResponse_Found:
  * - ``HttpServerResponse.Found``
    - ``302``
    - See `details on status code 302 <https://tools.ietf.org/html/rfc2616#section-10.3.2>`_ .

      .. _enumitem_HttpServerResponse_SeeOther:
  * - ``HttpServerResponse.SeeOther``
    - ``303``
    - See `details on status code 303 <https://tools.ietf.org/html/rfc2616#section-10.3.4>`_ .

      .. _enumitem_HttpServerResponse_NotModified:
  * - ``HttpServerResponse.NotModified``
    - ``304``
    - See `details on status code 304 <https://tools.ietf.org/html/rfc2616#section-10.3.5>`_ .

      .. _enumitem_HttpServerResponse_UseProxy:
  * - ``HttpServerResponse.UseProxy``
    - ``305``
    - See `details on status code 305 <https://tools.ietf.org/html/rfc2616#section-10.3.6>`_ .

      .. _enumitem_HttpServerResponse_TemporaryRedirect:
  * - ``HttpServerResponse.TemporaryRedirect``
    - ``307``
    - See `details on status code 307 <https://tools.ietf.org/html/rfc2616#section-10.3.8>`_ .

      .. _enumitem_HttpServerResponse_PermanentRedirect:
  * - ``HttpServerResponse.PermanentRedirect``
    - ``308``
    - See `details on status code 308 <https://tools.ietf.org/html/rfc7538>`_ .

      .. _enumitem_HttpServerResponse_BadRequest:
  * - ``HttpServerResponse.BadRequest``
    - ``400``
    - See `details on status code 400 <https://tools.ietf.org/html/rfc2616#section-10.4.1>`_ .

      .. _enumitem_HttpServerResponse_Unauthorized:
  * - ``HttpServerResponse.Unauthorized``
    - ``401``
    - See `details on status code 401 <https://tools.ietf.org/html/rfc2616#section-10.4.2>`_ .

      .. _enumitem_HttpServerResponse_PaymentRequired:
  * - ``HttpServerResponse.PaymentRequired``
    - ``402``
    - See `details on status code 402 <https://tools.ietf.org/html/rfc2616#section-10.4.3>`_ .

      .. _enumitem_HttpServerResponse_Forbidden:
  * - ``HttpServerResponse.Forbidden``
    - ``403``
    - See `details on status code 403 <https://tools.ietf.org/html/rfc2616#section-10.4.4>`_ .

      .. _enumitem_HttpServerResponse_NotFound:
  * - ``HttpServerResponse.NotFound``
    - ``404``
    - See `details on status code 404 <https://tools.ietf.org/html/rfc2616#section-10.4.5>`_ .

      .. _enumitem_HttpServerResponse_MethodNotAllowed:
  * - ``HttpServerResponse.MethodNotAllowed``
    - ``405``
    - See `details on status code 405 <https://tools.ietf.org/html/rfc2616#section-10.4.6>`_ .

      .. _enumitem_HttpServerResponse_NotAcceptable:
  * - ``HttpServerResponse.NotAcceptable``
    - ``406``
    - See `details on status code 406 <https://tools.ietf.org/html/rfc2616#section-10.4.7>`_ .

      .. _enumitem_HttpServerResponse_ProxyAuthenticationRequired:
  * - ``HttpServerResponse.ProxyAuthenticationRequired``
    - ``407``
    - See `details on status code 407 <https://tools.ietf.org/html/rfc2616#section-10.4.8>`_ .

      .. _enumitem_HttpServerResponse_RequestTimeout:
  * - ``HttpServerResponse.RequestTimeout``
    - ``408``
    - See `details on status code 408 <https://tools.ietf.org/html/rfc2616#section-10.4.9>`_ .

      .. _enumitem_HttpServerResponse_Conflict:
  * - ``HttpServerResponse.Conflict``
    - ``409``
    - See `details on status code 409 <https://tools.ietf.org/html/rfc2616#section-10.4.10>`_ .

      .. _enumitem_HttpServerResponse_Gone:
  * - ``HttpServerResponse.Gone``
    - ``410``
    - See `details on status code 410 <https://tools.ietf.org/html/rfc2616#section-10.4.11>`_ .

      .. _enumitem_HttpServerResponse_LengthRequired:
  * - ``HttpServerResponse.LengthRequired``
    - ``411``
    - See `details on status code 411 <https://tools.ietf.org/html/rfc2616#section-10.4.12>`_ .

      .. _enumitem_HttpServerResponse_PreconditionFailed:
  * - ``HttpServerResponse.PreconditionFailed``
    - ``412``
    - See `details on status code 412 <https://tools.ietf.org/html/rfc2616#section-10.4.13>`_ .

      .. _enumitem_HttpServerResponse_RequestEntityTooLarge:
  * - ``HttpServerResponse.RequestEntityTooLarge``
    - ``413``
    - See `details on status code 413 <https://tools.ietf.org/html/rfc2616#section-10.4.14>`_ .

      .. _enumitem_HttpServerResponse_URITooLong:
  * - ``HttpServerResponse.URITooLong``
    - ``414``
    - See `details on status code 414 <https://tools.ietf.org/html/rfc2616#section-10.4.15>`_ .

      .. _enumitem_HttpServerResponse_UnsupportedMediaType:
  * - ``HttpServerResponse.UnsupportedMediaType``
    - ``415``
    - See `details on status code 415 <https://tools.ietf.org/html/rfc2616#section-10.4.16>`_ .

      .. _enumitem_HttpServerResponse_RequestedRangeNotSatisfiable:
  * - ``HttpServerResponse.RequestedRangeNotSatisfiable``
    - ``416``
    - See `details on status code 416 <https://tools.ietf.org/html/rfc2616#section-10.4.17>`_ .

      .. _enumitem_HttpServerResponse_ExpectationFailed:
  * - ``HttpServerResponse.ExpectationFailed``
    - ``417``
    - See `details on status code 417 <https://tools.ietf.org/html/rfc2616#section-10.4.18>`_ .

      .. _enumitem_HttpServerResponse_PolicyNotFulfilled:
  * - ``HttpServerResponse.PolicyNotFulfilled``
    - ``420``
    - See `details on status code 420 <https://www.w3.org/TR/WD-http-pep-971121.html#_Toc404743960>`_ .

      .. _enumitem_HttpServerResponse_MisdirectedRequest:
  * - ``HttpServerResponse.MisdirectedRequest``
    - ``421``
    - See `details on status code 421 <https://tools.ietf.org/html/rfc7540#section-9.1.2>`_ .

      .. _enumitem_HttpServerResponse_UnprocessableEntity:
  * - ``HttpServerResponse.UnprocessableEntity``
    - ``422``
    - See `details on status code 422 <https://tools.ietf.org/html/rfc2518#section-10.3>`_ .

      .. _enumitem_HttpServerResponse_Locked:
  * - ``HttpServerResponse.Locked``
    - ``423``
    - See `details on status code 423 <https://tools.ietf.org/html/rfc2518#section-10.4>`_ .

      .. _enumitem_HttpServerResponse_FailedDependency:
  * - ``HttpServerResponse.FailedDependency``
    - ``424``
    - See `details on status code 424 <https://tools.ietf.org/html/rfc2518#section-10.5>`_ .

      .. _enumitem_HttpServerResponse_UpgradeRequired:
  * - ``HttpServerResponse.UpgradeRequired``
    - ``426``
    - See `details on status code 426 <https://tools.ietf.org/html/rfc2817>`_ .

      .. _enumitem_HttpServerResponse_PreconditionRequired:
  * - ``HttpServerResponse.PreconditionRequired``
    - ``428``
    - See `details on status code 428 <https://tools.ietf.org/html/rfc6585#section-3>`_ .

      .. _enumitem_HttpServerResponse_TooManyRequests:
  * - ``HttpServerResponse.TooManyRequests``
    - ``429``
    - See `details on status code 429 <https://tools.ietf.org/html/rfc6585#section-4>`_ .

      .. _enumitem_HttpServerResponse_RequestHeaderFieldsTooLarge:
  * - ``HttpServerResponse.RequestHeaderFieldsTooLarge``
    - ``431``
    - See `details on status code 431 <https://tools.ietf.org/html/rfc6585#section-5>`_ .

      .. _enumitem_HttpServerResponse_UnavailableForLegalReasons:
  * - ``HttpServerResponse.UnavailableForLegalReasons``
    - ``451``
    - See `details on status code 451 <https://tools.ietf.org/html/draft-tbray-http-legally-restricted-status-00#section-3>`_ .

      .. _enumitem_HttpServerResponse_InternalServerError:
  * - ``HttpServerResponse.InternalServerError``
    - ``500``
    - See `details on status code 500 <https://tools.ietf.org/html/rfc2616#section-10.5.1>`_ .

      .. _enumitem_HttpServerResponse_NotImplemented:
  * - ``HttpServerResponse.NotImplemented``
    - ``501``
    - See `details on status code 501 <https://tools.ietf.org/html/rfc2616#section-10.5.2>`_ .

      .. _enumitem_HttpServerResponse_BadGateway:
  * - ``HttpServerResponse.BadGateway``
    - ``502``
    - See `details on status code 502 <https://tools.ietf.org/html/rfc2616#section-10.5.3>`_ .

      .. _enumitem_HttpServerResponse_ServiceUnavailable:
  * - ``HttpServerResponse.ServiceUnavailable``
    - ``503``
    - See `details on status code 503 <https://tools.ietf.org/html/rfc2616#section-10.5.4>`_ .

      .. _enumitem_HttpServerResponse_GatewayTimeout:
  * - ``HttpServerResponse.GatewayTimeout``
    - ``504``
    - See `details on status code 504 <https://tools.ietf.org/html/rfc2616#section-10.5.5>`_ .

      .. _enumitem_HttpServerResponse_HttpVersionNotSupported:
  * - ``HttpServerResponse.HttpVersionNotSupported``
    - ``505``
    - See `details on status code 505 <https://tools.ietf.org/html/rfc2616#section-10.5.6>`_ .

      .. _enumitem_HttpServerResponse_VariantAlsoNegotiates:
  * - ``HttpServerResponse.VariantAlsoNegotiates``
    - ``506``
    - See `details on status code 506 <https://tools.ietf.org/html/rfc2295#section-8.1>`_ .

      .. _enumitem_HttpServerResponse_InsufficientStorage:
  * - ``HttpServerResponse.InsufficientStorage``
    - ``507``
    - See `details on status code 507 <https://tools.ietf.org/html/rfc4918#section-11.5>`_ .

      .. _enumitem_HttpServerResponse_LoopDetected:
  * - ``HttpServerResponse.LoopDetected``
    - ``508``
    - See `details on status code 508 <https://tools.ietf.org/html/rfc5842#section-7.2>`_ .

      .. _enumitem_HttpServerResponse_NotExtended:
  * - ``HttpServerResponse.NotExtended``
    - ``510``
    - See `details on status code 510 <https://tools.ietf.org/html/rfc2774#section-7>`_ .

      .. _enumitem_HttpServerResponse_NetworkAuthenticationRequired:
  * - ``HttpServerResponse.NetworkAuthenticationRequired``
    - ``511``
    - See `details on status code 511 <https://tools.ietf.org/html/rfc6585#section-6>`_ .

