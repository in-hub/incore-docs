
.. _object_DateTime:


:index:`DateTime`
-----------------

Description
***********

The DateTime object represents a date including a time to specify a certain absolute point in time. It provides mechanisms for easily formatting a date and/or time into a string, handling timezones and querying precise milliseconds-based timestamps from the system.

:**› Inherits**: :ref:`DataObject <object_DataObject>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`currentMSecsSinceEpoch <property_DateTime_currentMSecsSinceEpoch>`
  * :ref:`currentSecsSinceEpoch <property_DateTime_currentSecsSinceEpoch>`
  * :ref:`dateFormat <property_DateTime_dateFormat>`
  * :ref:`formatString <property_DateTime_formatString>`
  * :ref:`highPrecisionString <property_DateTime_highPrecisionString>`
  * :ref:`string <property_DateTime_string>`
  * :ref:`timeZone <property_DateTime_timeZone>`
  * :ref:`DataObject.data <property_DataObject_data>`
  * :ref:`DataObject.dataType <property_DataObject_dataType>`
  * :ref:`DataObject.description <property_DataObject_description>`
  * :ref:`DataObject.name <property_DataObject_name>`
  * :ref:`DataObject.timestamp <property_DataObject_timestamp>`
  * :ref:`DataObject.uuid <property_DataObject_uuid>`
  * :ref:`DataObject.view <property_DataObject_view>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`availableTimeZones() <method_DateTime_availableTimeZones>`
  * :ref:`DataObject.touch() <method_DataObject_touch>`
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

  * :ref:`DateFormat <enum_DateTime_DateFormat>`
  * :ref:`DataObject.DataType <enum_DataObject_DataType>`



Properties
**********


.. _property_DateTime_currentMSecsSinceEpoch:

.. index::
   single: currentMSecsSinceEpoch

currentMSecsSinceEpoch
++++++++++++++++++++++

This property holds the number of milliseconds since 1970-01-01T00:00:00 Universal Coordinated Time. This number is like the POSIX time_t variable, but expressed in milliseconds instead.

.. note:: For performance reason this property is not updated automatically and has to be read explicitely whenever required. This property therefore can't be used in bindings expressions and is only evaluated once.

:**› Type**: SignedBigInteger
:**› Attributes**: Readonly


.. _property_DateTime_currentSecsSinceEpoch:

.. _signal_DateTime_currentSecsSinceEpochChanged:

.. index::
   single: currentSecsSinceEpoch

currentSecsSinceEpoch
+++++++++++++++++++++

This property holds the number of seconds since 1970-01-01T00:00:00 Universal Coordinated Time.

:**› Type**: SignedBigInteger
:**› Signal**: currentSecsSinceEpochChanged()
:**› Attributes**: Readonly


.. _property_DateTime_dateFormat:

.. _signal_DateTime_dateFormatChanged:

.. index::
   single: dateFormat

dateFormat
++++++++++

This property holds the used dateFormat to format :ref:`string <property_DateTime_string>`, if :ref:`formatString <property_DateTime_formatString>` is left blank.

:**› Type**: :ref:`DateFormat <enum_DateTime_DateFormat>`
:**› Default**: :ref:`DateTime.FormatText <enumitem_DateTime_FormatText>`
:**› Signal**: dateFormatChanged()
:**› Attributes**: Writable


.. _property_DateTime_formatString:

.. _signal_DateTime_formatStringChanged:

.. index::
   single: formatString

formatString
++++++++++++

This property holds the format string which is used to format :ref:`string <property_DateTime_string>` if set.

.. list-table:: Format codes

  * - d		
    - the day as number without a leading zero (1 to 31)
  * - dd		
    - the day as number with a leading zero (01 to 31)
  * - ddd	
    - the abbreviated localized day name (e.g. 'Mon' to 'Sun'). Uses the system locale to localize the name
  * - dddd	
    - the long localized day name (e.g. 'Monday' to 'Sunday'). Uses the system locale to localize the name
  * - M		
    - the month as number without a leading zero (1-12)
  * - MM		
    - the month as number with a leading zero (01-12)
  * - MMM	
    - the abbreviated localized month name (e.g. 'Jan' to 'Dec'). Uses the system locale to localize the name
  * - MMMM	
    - the long localized month name (e.g. 'January' to 'December'). Uses the system locale to localize the name
  * - yy		
    - the year as two digit number (00-99)
  * - yyyy	
    - the year as four digit number
  * - h		
    - the hour without a leading zero (0 to 23 or 1 to 12 if AM/PM display)
  * - hh		
    - the hour with a leading zero (00 to 23 or 01 to 12 if AM/PM display)
  * - H		
    - the hour without a leading zero (0 to 23, even with AM/PM display)
  * - HH		
    - the hour with a leading zero (00 to 23, even with AM/PM display)
  * - m		
    - the minute without a leading zero (0 to 59)
  * - mm		
    - the minute with a leading zero (00 to 59)
  * - s		
    - the whole second without a leading zero (0 to 59)
  * - ss		
    - the whole second with a leading zero where applicable (00 to 59)
  * - z		
    - the fractional part of the second, to go after a decimal point, without trailing zeroes (0 to 999)
  * - zz		
    - the fractional part of the second, to millisecond precision, including trailing zeroes where applicable (000 to 999)
  * - AP or A
    - use AM/PM display. A/AP will be replaced by either "AM" or "PM"
  * - ap or a
    - use am/pm display. a/ap will be replaced by either "am" or "pm"
  * - t		
    - the timezone abbreviation (for example "CEST")


:**› Type**: String
:**› Signal**: formatStringChanged()
:**› Attributes**: Writable


.. _property_DateTime_highPrecisionString:

.. index::
   single: highPrecisionString

highPrecisionString
+++++++++++++++++++

This property holds a formatted string including milliseconds. If a custom :ref:`formatString <property_DateTime_formatString>` is used it has to be ensured that it includes placeholders for milliseconds as these will be omitted otherwise.

.. note:: For performance reason this property is not updated automatically and has to be read explicitely whenever required. This property therefore can't be used in bindings expressions and is only evaluated once.

:**› Type**: String
:**› Attributes**: Readonly


.. _property_DateTime_string:

.. _signal_DateTime_stringChanged:

.. index::
   single: string

string
++++++

This property holds a formatted and constantly updated string representing the current time. If :ref:`formatString <property_DateTime_formatString>` is set it is used for formatting, otherwise :ref:`dateFormat <property_DateTime_dateFormat>` is used.

:**› Type**: String
:**› Signal**: stringChanged()
:**› Attributes**: Readonly


.. _property_DateTime_timeZone:

.. _signal_DateTime_timeZoneChanged:

.. index::
   single: timeZone

timeZone
++++++++

This property holds the timezone which should used. Check :ref:`availableTimeZones() <method_DateTime_availableTimeZones>` for a list of all available time zone ids.

:**› Type**: String
:**› Signal**: timeZoneChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_DateTime_availableTimeZones:

.. index::
   single: availableTimeZones

availableTimeZones()
++++++++++++++++++++

This method returns a list of all available time zones.

:**› Returns**: StringList


Enumerations
************


.. _enum_DateTime_DateFormat:

.. index::
   single: DateFormat

DateFormat
++++++++++

This enumeration describes all supported predefined date formats.

.. index::
   single: DateTime.FormatText
.. index::
   single: DateTime.FormatISO
.. index::
   single: DateTime.FormatLocalizedShort
.. index::
   single: DateTime.FormatLocalizedLong
.. index::
   single: DateTime.FormatRFC2822
.. index::
   single: DateTime.FormatISOWithMs
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_DateTime_FormatText:
  * - ``DateTime.FormatText``
    - ``0``
    - The default format, which includes the day and month name, the day number in the month, and the year in full. The day and month names will be short, localized names. This is basically equivalent to using the date format string, "ddd MMM d yyyy".

      .. _enumitem_DateTime_FormatISO:
  * - ``DateTime.FormatISO``
    - ``1``
    - ISO 8601 extended format: yyyy-MM-ddTHH:mm:ss (e.g. 2019-04-02T10:30:29) or with a time-zone suffix (Z for UTC otherwise an offset as [+|-]HH:mm) if set.

      .. _enumitem_DateTime_FormatLocalizedShort:
  * - ``DateTime.FormatLocalizedShort``
    - ``6``
    - The short version of day and month names, for example "Jan" as a month name.

      .. _enumitem_DateTime_FormatLocalizedLong:
  * - ``DateTime.FormatLocalizedLong``
    - ``7``
    - The short version of day and month names, for example "January" as a month name.

      .. _enumitem_DateTime_FormatRFC2822:
  * - ``DateTime.FormatRFC2822``
    - ``8``
    - RFC 2822, RFC 850 and RFC 1036 format: either [ddd,] dd MMM yyyy hh:mm[:ss] +/-TZ or ddd MMM dd yyyy hh:mm[:ss] +/-TZ.

      .. _enumitem_DateTime_FormatISOWithMs:
  * - ``DateTime.FormatISOWithMs``
    - ``9``
    - ISO 8601 extended format (:ref:`DateTime.FormatISO <enumitem_DateTime_FormatISO>`) including milliseconds.


.. _example_DateTime:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    
    Application {
    
    
        DateTime {
            id: dateTime0
            dateFormat: DateTime.FormatISO
    
            onStringChanged: console.log( "current date time is (human reable and unix)", string, currentSecsSinceEpoch )
        }
    
        DateTime {
            id: dateTime1
            formatString: "MMdd"
    
            onStringChanged: if( string === "0504" ) console.log( "May the fourth be with you!" )
        }
    
        DateTime {
            id: dateTime2
            dateFormat: DateTime.FormatISOWithMs
            // onHighPrecisionStringChanged will not work
        }
    
        Timer {
            interval: 500
            onTriggered: console.log( "high precision date time", dateTime2.highPrecisionString )
        }
    }
    