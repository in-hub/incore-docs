
.. _object_HttpHeader:


:index:`HttpHeader`
-------------------

Description
***********

The HttpHeader object represents a single HTTP header which is sent to or received from HTTP servers through :ref:`HttpRequest <object_HttpRequest>` and :ref:`HttpResponse <object_HttpResponse>` objects.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`customHeader <property_HttpHeader_customHeader>`
  * :ref:`data <property_HttpHeader_data>`
  * :ref:`type <property_HttpHeader_type>`
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

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Type <enum_HttpHeader_Type>`



Properties
**********


.. _property_HttpHeader_customHeader:

.. _signal_HttpHeader_customHeaderChanged:

.. index::
   single: customHeader

customHeader
++++++++++++

This property holds the name of a custom HTTP header field which is used when :ref:`type <property_HttpHeader_type>` is set to :ref:`HttpHeader.Custom <enumitem_HttpHeader_Custom>`.

:**› Type**: String
:**› Signal**: customHeaderChanged()
:**› Attributes**: Writable


.. _property_HttpHeader_data:

.. _signal_HttpHeader_dataChanged:

.. index::
   single: data

data
++++

This property holds the data for the HTTP header represented by this object. The data type depends on the :ref:`header type <property_HttpHeader_type>` but usually a string can be used. Use a :ref:`DateTime <object_DateTime>` object for the header types :ref:`HttpHeader.LastModified <enumitem_HttpHeader_LastModified>` and :ref:`HttpHeader.IfModifiedSince <enumitem_HttpHeader_IfModifiedSince>`. This allows dealing with dates easily and let them being converted to properly formatted date strings automatically.

:**› Type**: Variant
:**› Signal**: dataChanged()
:**› Attributes**: Writable


.. _property_HttpHeader_type:

.. _signal_HttpHeader_typeChanged:

.. index::
   single: type

type
++++

This property holds the type of the HTTP header represented by this object.

:**› Type**: :ref:`Type <enum_HttpHeader_Type>`
:**› Default**: :ref:`HttpHeader.Custom <enumitem_HttpHeader_Custom>`
:**› Signal**: typeChanged()
:**› Attributes**: Writable

Enumerations
************


.. _enum_HttpHeader_Type:

.. index::
   single: Type

Type
++++

This enumeration describes the supported HTTP header types as described in `RFC 2616 Section 14 <https://tools.ietf.org/html/rfc2616#section-14>`_.

.. index::
   single: HttpHeader.ContentType
.. index::
   single: HttpHeader.ContentLength
.. index::
   single: HttpHeader.Location
.. index::
   single: HttpHeader.LastModified
.. index::
   single: HttpHeader.ContentDisposition
.. index::
   single: HttpHeader.UserAgent
.. index::
   single: HttpHeader.Server
.. index::
   single: HttpHeader.IfModifiedSince
.. index::
   single: HttpHeader.ETag
.. index::
   single: HttpHeader.IfMatch
.. index::
   single: HttpHeader.IfNoneMatch
.. index::
   single: HttpHeader.Custom
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_HttpHeader_ContentType:
  * - ``HttpHeader.ContentType``
    - ``0``
    - Corresponds to the HTTP Content-Type header and contains a string containing the media (MIME) type and any auxiliary data (for instance, charset).

      .. _enumitem_HttpHeader_ContentLength:
  * - ``HttpHeader.ContentLength``
    - ``1``
    - Corresponds to the HTTP Content-Length header and contains the length in bytes of the data transmitted.

      .. _enumitem_HttpHeader_Location:
  * - ``HttpHeader.Location``
    - ``2``
    - Corresponds to the HTTP Location header and contains a URL representing the actual location of the data, including the destination URL in case of redirections.

      .. _enumitem_HttpHeader_LastModified:
  * - ``HttpHeader.LastModified``
    - ``3``
    - Corresponds to the HTTP Last-Modified header and contains a :ref:`DateTime <object_DateTime>` object representing the last modification date of the contents.

      .. _enumitem_HttpHeader_ContentDisposition:
  * - ``HttpHeader.ContentDisposition``
    - ``6``
    - Corresponds to the HTTP Content-Disposition header and contains a string containing the disposition type (for instance, attachment) and a parameter (for instance, filename).

      .. _enumitem_HttpHeader_UserAgent:
  * - ``HttpHeader.UserAgent``
    - ``7``
    - The User-Agent header sent by HTTP clients.

      .. _enumitem_HttpHeader_Server:
  * - ``HttpHeader.Server``
    - ``8``
    - The Server header received by HTTP clients.

      .. _enumitem_HttpHeader_IfModifiedSince:
  * - ``HttpHeader.IfModifiedSince``
    - ``9``
    - Corresponds to the HTTP If-Modified-Since header and contains a :ref:`DateTime <object_DateTime>` object. It is usually added to a :ref:`HttpRequest <object_HttpRequest>` object. The server shall send a 304 (Not Modified) response if the resource has not changed since this time.

      .. _enumitem_HttpHeader_ETag:
  * - ``HttpHeader.ETag``
    - ``10``
    - Corresponds to the HTTP ETag header and contains a QString representing the last modification state of the contents.

      .. _enumitem_HttpHeader_IfMatch:
  * - ``HttpHeader.IfMatch``
    - ``11``
    - Corresponds to the HTTP If-Match header and contains a StringList. It is usually added to a :ref:`HttpRequest <object_HttpRequest>` object. The server shall send a 412 (Precondition Failed) response if the resource does not match.

      .. _enumitem_HttpHeader_IfNoneMatch:
  * - ``HttpHeader.IfNoneMatch``
    - ``12``
    - Corresponds to the HTTP If-None-Match header and contains a StringList. It is usually added to a :ref:`HttpRequest <object_HttpRequest>` object. The server shall send a 304 (Not Modified) response if the resource does match.

      .. _enumitem_HttpHeader_Custom:
  * - ``HttpHeader.Custom``
    - ``13``
    - Corresponds to a custem HTTP header. The content of the :ref:`customHeader <property_HttpHeader_customHeader>` property is used for the HTTP header name field.


.. _example_HttpHeader:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.Http 2.5
    
    Application {
    
        id: app
    
        MeasurementGroup {
            id: sensorGroup
            Measurement {
                id: temperatureSensor
                unit: "°C"
                data: 20 + Math.random() * 10
            }
            Measurement {
                id: pressureSensor
                unit: "Pa"
                data: 100000 + Math.random() * 10000
                siPrefix: Pressure.Kilo
            }
        }
    
        Serializer {
            id: sensorSerializer
            source: sensorGroup
        }
    
        HttpRequest {
            id: headerTest
            url: "https://httpbin.org/post"
            content: HttpContent {
                type: HttpContent.Json
                data: sensorSerializer.data
            }
    
            HttpHeader {
                type: HttpHeader.UserAgent
                data: "InCore HTTP Client"
            }
    
            HttpHeader {
                customHeader: "InCore-DeviceId"
                data: system.deviceId
            }
    
            response.autoDetectDataTypeFromContentType: false
            onResponseReceived: console.log("Response for POST:", response.statusCode, response.content.data)
        }
    
        onCompleted: {
            headerTest.post();
        }
    }
    