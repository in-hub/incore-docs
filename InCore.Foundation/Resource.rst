
.. _object_Resource:


:index:`Resource`
-----------------

Description
***********

The Resource object provides the content of a file as a string. This can be used to easily process the content of text files or provide base64-encoded image data.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`data <property_Resource_data>`
  * :ref:`encoding <property_Resource_encoding>`
  * :ref:`error <property_Resource_error>`
  * :ref:`errorString <property_Resource_errorString>`
  * :ref:`fileName <property_Resource_fileName>`
  * :ref:`storage <property_Resource_storage>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_Resource_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Encoding <enum_Resource_Encoding>`
  * :ref:`Error <enum_Resource_Error>`



Properties
**********


.. _property_Resource_data:

.. _signal_Resource_dataChanged:

.. index::
   single: data

data
++++

This property holds the contents of the file resource. Its encoding is based on the :ref:`encoding <property_Resource_encoding>` property.

:**› Type**: String
:**› Signal**: dataChanged()
:**› Attributes**: Readonly


.. _property_Resource_encoding:

.. _signal_Resource_encodingChanged:

.. index::
   single: encoding

encoding
++++++++

This property holds the encoding type specifying how to encode the data read from the file before updating the :ref:`data <property_Resource_data>` property.

:**› Type**: :ref:`Encoding <enum_Resource_Encoding>`
:**› Default**: :ref:`Resource.Raw <enumitem_Resource_Raw>`
:**› Signal**: encodingChanged()
:**› Attributes**: Writable


.. _property_Resource_error:

.. _signal_Resource_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`Resource.NoError <enumitem_Resource_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_Resource_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_Resource_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_Resource_errorString:

.. _signal_Resource_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_Resource_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_Resource_fileName:

.. _signal_Resource_fileNameChanged:

.. index::
   single: fileName

fileName
++++++++

This property holds the name of the resource file to read. It is relative to :ref:`storage <property_Resource_storage>` and its :ref:`path <property_Storage_path>` on the storage.

:**› Type**: String
:**› Signal**: fileNameChanged()
:**› Attributes**: Writable


.. _property_Resource_storage:

.. _signal_Resource_storageChanged:

.. index::
   single: storage

storage
+++++++

This property holds a reference to the storage which the resource file is stored on.

:**› Type**: :ref:`Storage <object_Storage>`
:**› Signal**: storageChanged()
:**› Attributes**: Writable

Signals
*******


.. _signal_Resource_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_Resource_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_Resource_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_Resource_Encoding:

.. index::
   single: Encoding

Encoding
++++++++

This enumeration describes the supported encoding types for the :ref:`data <property_Resource_data>` property.

.. index::
   single: Resource.Raw
.. index::
   single: Resource.Base64
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_Resource_Raw:
  * - ``Resource.Raw``
    - ``0``
    - Provide the file contents as a UTF-8 encoded string.

      .. _enumitem_Resource_Base64:
  * - ``Resource.Base64``
    - ``1``
    - Provide the file contents as a base64 encoded string.


.. _enum_Resource_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in Resource objects. The most recently occurred error is stored in the :ref:`error <property_Resource_error>` property.

.. index::
   single: Resource.NoError
.. index::
   single: Resource.FileNotFoundError
.. index::
   single: Resource.FileOpenError
.. index::
   single: Resource.FileTooBigError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_Resource_NoError:
  * - ``Resource.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_Resource_FileNotFoundError:
  * - ``Resource.FileNotFoundError``
    - ``1``
    - Resource file not found.

      .. _enumitem_Resource_FileOpenError:
  * - ``Resource.FileOpenError``
    - ``2``
    - File can't be opened for reading.

      .. _enumitem_Resource_FileTooBigError:
  * - ``Resource.FileTooBigError``
    - ``3``
    - File size exceeds internal limits.

