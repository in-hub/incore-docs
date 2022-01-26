
.. _object_ApplicationView:


:index:`ApplicationView`
------------------------

Description
***********

The ApplicationView object contains settings and data for representing and displaying an :ref:`Application <object_Application>` in a user-defined frontend. This allows modelling generic and dynamic user interfaces. None of the properties are evaluated or used by any InCore objects so that no restrictions apply for the contents of the individual properties.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`accentColor <property_ApplicationView_accentColor>`
  * :ref:`backgroundColor <property_ApplicationView_backgroundColor>`
  * :ref:`foregroundColor <property_ApplicationView_foregroundColor>`
  * :ref:`logo <property_ApplicationView_logo>`
  * :ref:`name <property_ApplicationView_name>`
  * :ref:`primaryColor <property_ApplicationView_primaryColor>`
  * :ref:`url <property_ApplicationView_url>`
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

  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_ApplicationView_accentColor:

.. _signal_ApplicationView_accentColorChanged:

.. index::
   single: accentColor

accentColor
+++++++++++

This property holds the accent color used in the theme of an application frontend.

:**› Type**: String
:**› Default**: ``rgb(0, 150, 136)``
:**› Signal**: accentColorChanged()
:**› Attributes**: Writable


.. _property_ApplicationView_backgroundColor:

.. _signal_ApplicationView_backgroundColorChanged:

.. index::
   single: backgroundColor

backgroundColor
+++++++++++++++

This property holds the background color used in the theme of an application frontend.

:**› Type**: String
:**› Default**: ``white``
:**› Signal**: backgroundColorChanged()
:**› Attributes**: Writable


.. _property_ApplicationView_foregroundColor:

.. _signal_ApplicationView_foregroundColorChanged:

.. index::
   single: foregroundColor

foregroundColor
+++++++++++++++

This property holds the foreground color used in the theme of an application frontend.

:**› Type**: String
:**› Default**: ``black``
:**› Signal**: foregroundColorChanged()
:**› Attributes**: Writable


.. _property_ApplicationView_logo:

.. _signal_ApplicationView_logoChanged:

.. index::
   single: logo

logo
++++

This property holds a :ref:`Resource <object_Resource>` object containing or describing the application logo image.

:**› Type**: :ref:`Resource <object_Resource>`
:**› Signal**: logoChanged()
:**› Attributes**: Readonly


.. _property_ApplicationView_name:

.. index::
   single: name

name
++++

This property holds the name of the application as defined in the :ref:`Application.name <property_Application_name>` property. It's provided for convenience only.

:**› Type**: String
:**› Attributes**: Readonly


.. _property_ApplicationView_primaryColor:

.. _signal_ApplicationView_primaryColorChanged:

.. index::
   single: primaryColor

primaryColor
++++++++++++

This property holds the primary color used in the theme of an application frontend.

:**› Type**: String
:**› Default**: ``rgb(0, 150, 136)``
:**› Signal**: primaryColorChanged()
:**› Attributes**: Writable


.. _property_ApplicationView_url:

.. index::
   single: url

url
+++

This property holds the URL of the application as defined in the :ref:`Application.url <property_Application_url>` property. It's provided for convenience only.

:**› Type**: String
:**› Attributes**: Readonly


.. _example_ApplicationView:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    
    Application {
    
        // define a view with background and foreground color and a logo provided in the logo.data property
        ApplicationView {
            id: appView
            backgroundColor: "white"
            foregroundColor: "black"
            logo {
                fileName: "logo.png"
            }
        }
    
        // serialize application view as JSON string
        Serializer {
            id: appViewSerializer
            source: appView
            onDataChanged: console.log(data)
        }
    
        // publish serialized application view data via JSON-RPC
        JsonRpcServer {
            JsonRpcService {
                readonly property alias view: appViewSerializer.data
            }
        }
    }
    