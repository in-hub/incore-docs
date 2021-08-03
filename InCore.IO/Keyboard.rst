
.. _object_Keyboard:


:index:`Keyboard`
-----------------

Description
***********

The Keyboard object represents a keyboard input device attached to the local system. Keyboards can be any kind of input devices with one or multiple keys. This also includes devices simulating key presses such as HID-based barcode scanners connected via USB. This object allows receiving :ref:`key press events <signal_Keyboard_keyPressed>` and :ref:`key release events <signal_Keyboard_keyReleased>` as well as any :ref:`entered text <signal_Keyboard_textEntered>` from the input device.

This object was introduced in InCore 2.3.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`enabled <property_Keyboard_enabled>`
  * :ref:`inputDeviceFile <property_Keyboard_inputDeviceFile>`
  * :ref:`name <property_Keyboard_name>`
  * :ref:`physicalLocation <property_Keyboard_physicalLocation>`
  * :ref:`productIdentifier <property_Keyboard_productIdentifier>`
  * :ref:`usbLocation <property_Keyboard_usbLocation>`
  * :ref:`vendorIdentifier <property_Keyboard_vendorIdentifier>`
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

  * :ref:`keyPressed() <signal_Keyboard_keyPressed>`
  * :ref:`keyReleased() <signal_Keyboard_keyReleased>`
  * :ref:`textEntered() <signal_Keyboard_textEntered>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Modifiers <enum_Keyboard_Modifiers>`



Properties
**********


.. _property_Keyboard_enabled:

.. _signal_Keyboard_enabledChanged:

.. index::
   single: enabled

enabled
+++++++

This property holds whether the device is enabled, i.e. key events are processed and the corresponding signals are emitted.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: enabledChanged()
:**› Attributes**: Writable


.. _property_Keyboard_inputDeviceFile:

.. _signal_Keyboard_inputDeviceFileChanged:

.. index::
   single: inputDeviceFile

inputDeviceFile
+++++++++++++++

This property holds the input device file of the keyboard represented by this object.

:**› Type**: String
:**› Signal**: inputDeviceFileChanged()
:**› Attributes**: Readonly


.. _property_Keyboard_name:

.. _signal_Keyboard_nameChanged:

.. index::
   single: name

name
++++

This property holds the name of the keyboard device, if available.

:**› Type**: String
:**› Signal**: nameChanged()
:**› Attributes**: Readonly


.. _property_Keyboard_physicalLocation:

.. _signal_Keyboard_physicalLocationChanged:

.. index::
   single: physicalLocation

physicalLocation
++++++++++++++++

This property holds the physical location of the keyboard device, if available.

:**› Type**: String
:**› Signal**: physicalLocationChanged()
:**› Attributes**: Readonly


.. _property_Keyboard_productIdentifier:

.. _signal_Keyboard_productIdentifierChanged:

.. index::
   single: productIdentifier

productIdentifier
+++++++++++++++++

This property holds the product identifier of the keyboard device, if available.

:**› Type**: SignedInteger
:**› Signal**: productIdentifierChanged()
:**› Attributes**: Readonly


.. _property_Keyboard_usbLocation:

.. _signal_Keyboard_usbLocationChanged:

.. index::
   single: usbLocation

usbLocation
+++++++++++

This property holds the location of the keyboard device on the USB bus, if available.

:**› Type**: String
:**› Signal**: usbLocationChanged()
:**› Attributes**: Readonly


.. _property_Keyboard_vendorIdentifier:

.. _signal_Keyboard_vendorIdentifierChanged:

.. index::
   single: vendorIdentifier

vendorIdentifier
++++++++++++++++

This property holds the vendor identifier of the keyboard device, if available.

:**› Type**: SignedInteger
:**› Signal**: vendorIdentifierChanged()
:**› Attributes**: Readonly

Signals
*******


.. _signal_Keyboard_keyPressed:

.. index::
   single: keyPressed

keyPressed(SignedInteger key, :ref:`Keyboard.Modifiers <enum_Keyboard_Modifiers>` modifiers, Boolean autoRepeat)
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever a key is pressed or auto-repeated while pressed. The ``key`` argument contains the corresponding key code. Any active modifiers (such as :kbd:`Shift` or :kbd:`Ctrl`) are indicated through the ``modifiers`` argument. If the key event was caused by auto-repeat, the ``autoRepeat`` argument is ``true``. If automatically repeated key 



.. _signal_Keyboard_keyReleased:

.. index::
   single: keyReleased

keyReleased(SignedInteger key, :ref:`Keyboard.Modifiers <enum_Keyboard_Modifiers>` modifiers)
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever a key is released. The ``key`` argument contains the corresponding key code. Any active modifiers (such as :kbd:`Shift` or :kbd:`Ctrl`) are indicated through the ``modifiers`` argument.



.. _signal_Keyboard_textEntered:

.. index::
   single: textEntered

textEntered(String text)
++++++++++++++++++++++++

This signal is emitted whenever a text is entered, i.e. a character or numeric key is pressed.


Enumerations
************


.. _enum_Keyboard_Modifiers:

.. index::
   single: Modifiers

Modifiers
+++++++++

This enumeration describes the modifier keys which can be pressed while other keys are pressed.

.. index::
   single: Keyboard.NoModifier
.. index::
   single: Keyboard.ShiftModifier
.. index::
   single: Keyboard.ControlModifier
.. index::
   single: Keyboard.AltModifier
.. index::
   single: Keyboard.MetaModifier
.. index::
   single: Keyboard.KeypadModifier
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_Keyboard_NoModifier:
  * - ``Keyboard.NoModifier``
    - ``0``
    - No modifier key is pressed.

      .. _enumitem_Keyboard_ShiftModifier:
  * - ``Keyboard.ShiftModifier``
    - ``33554432``
    - A :kbd:`Shift` key on the keyboard is pressed.

      .. _enumitem_Keyboard_ControlModifier:
  * - ``Keyboard.ControlModifier``
    - ``67108864``
    - A :kbd:`Ctrl` key on the keyboard is pressed.

      .. _enumitem_Keyboard_AltModifier:
  * - ``Keyboard.AltModifier``
    - ``134217728``
    - A :kbd:`Alt` key on the keyboard is pressed.

      .. _enumitem_Keyboard_MetaModifier:
  * - ``Keyboard.MetaModifier``
    - ``268435456``
    - A :kbd:`Meta` key on the keyboard is pressed.

      .. _enumitem_Keyboard_KeypadModifier:
  * - ``Keyboard.KeypadModifier``
    - ``536870912``
    - A keypad button is pressed.

Example
*******
See :ref:`KeyboardManager example <example_KeyboardManager>` on how to use Keyboard.
