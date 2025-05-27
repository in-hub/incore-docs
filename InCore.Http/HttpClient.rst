
.. _object_HttpClient:


:index:`HttpClient`
-------------------

Description
***********

The HttpClient object provides methods for sending HTTP request to a HTTP server. All common methods (GET, PUT, POST, DELETE) are supported. Unlike :ref:`HttpRequest <object_HttpRequest>`, this object is a singleton and has no properties. Instead all parameters have to be passed to the corresponding methods explicitly. Responses/errors have to be processed by callbacks supplied as the last parameters.

This object was introduced in InCore 2.9.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 2

  * :ref:`del() <method_HttpClient_del>`
  * :ref:`get() <method_HttpClient_get>`
  * :ref:`post() <method_HttpClient_post>`
  * :ref:`put() <method_HttpClient_put>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********

Methods
*******


.. _method_HttpClient_del:

.. index::
   single: del

del(String url, List headers, JSValue responseCallback, JSValue errorCallback)
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

This method sends a HTTP request with the `DELETE` method to the server. It's mainly used for deleting resources at the given URL.

See `RFC2616 Section 9.7 <https://tools.ietf.org/html/rfc2616#section-9.7>`_ for details.



.. _method_HttpClient_get:

.. index::
   single: get

get(String url, List headers, JSValue responseCallback, JSValue errorCallback)
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

This method sends a HTTP request with the `GET` method to the server. It's mainly used for downloading resources at the given URL.

See `RFC2616 Section 9.3 <https://tools.ietf.org/html/rfc2616#section-9.3>`_ for details.



.. _method_HttpClient_post:

.. index::
   single: post

post(String url, List headers, String data, JSValue responseCallback, JSValue errorCallback)
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

This method sends a HTTP request with the `POST` method to the server. It's mainly used for annotation of existing resources, providing a block of data, such as the result of submitting a form, to a data-handling process or extending a database through an append operation.

See `RFC2616 Section 9.5 <https://tools.ietf.org/html/rfc2616#section-9.5>`_ for details.



.. _method_HttpClient_put:

.. index::
   single: put

put(String url, List headers, String data, JSValue responseCallback, JSValue errorCallback)
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

This method sends a HTTP request with the `PUT` method to the server. It's mainly used for storing resources under the given URL.

See `RFC2616 Section 9.6 <https://tools.ietf.org/html/rfc2616#section-9.6>`_ for details.



.. _example_HttpClient:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.9
    import InCore.Http 2.9
    
    Application {
        onCompleted: {
            HttpClient.get("https://www.inhub.de/", [[HttpHeader.UserAgent, "InCore"], ["Session", "123"]], (response) => {
                               if (response.statusCode === HttpResponse.OK)
                               {
                                   console.log("Received", response.content.data.length, "bytes")
                               }
                               else
                               {
                                   console.log("HTTP status code received:", response.statusCode)
                               }
                           });
    
            HttpClient.get("https://zzz.inhub.de", [], undefined, (error) => {
                               if (error === HttpRequest.HostNotFoundError)
                               {
                                   console.log("Host not found")
                               }
                               else
                               {
                                   console.log("HttpClient error:", error)
                               }
                           });
    
            HttpClient.post("https://httpbin.org/post", [], "InCore.Http POST Example",
                            (response) => console.log("Response for POST:", response.statusCode, response.content.data["data"]));
    
            HttpClient.put("https://httpbin.org/put", [], "InCore.Http PUT Example",
                           (response) => console.log("Response for PUT:", response.statusCode, response.content.data["data"]));
        }
    }
    