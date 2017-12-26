ZBX-AKCP-SP2
==============

This template uses the HHMSAGENT-MIB to discover and monitor AKCP Environmental Monitoring devices using SNMP.

Items
-----

  * Current Humidity
  * Current Temperature
  * High Humidity Critical Threshold
  * High Humidity Warning Threshold
  * High Temperature Critical Threshold
  * High Temperature Warning Threshold
  * Humidity Rearm
  * Humidity Sensor Description
  * Humidity Sensor Status
  * Humidity Status
  * Low Humidity Critical Threshold
  * Low Humidity Warning Threshold
  * Low Temperature Critical Threshold
  * Low Temperature Warning Threshold
  * Temperature Rearm
  * Temperature Sensor Description
  * Temperature Sensor Status
  * Temperature Status

Triggers
--------

  * **[HIGH]** => {HOST.NAME} High Humidity Alarm: ({ITEM.VALUE})
  * **[HIGH]** => {HOST.NAME} High Temperature Alarm: ({ITEM.VALUE})
  * **[DEGRADED]** => {HOST.NAME} High Humidity Warning: ({ITEM.VALUE})
  * **[DEGRADED]** => {HOST.NAME} High Temperature Warning: ({ITEM.VALUE})
  * **[DEGRADED]** => {HOST.NAME} Low Humidity Alarm: ({ITEM.VALUE})
  * **[DEGRADED]** => {HOST.NAME} Low Temperature Alarm: ({ITEM.VALUE})
  * **[WARNING]** => {HOST.NAME} Humidity Sensor Abnormal: ({ITEM.VALUE})
  * **[WARNING]** => {HOST.NAME} Low Humidity Warning: ({ITEM.VALUE})
  * **[WARNING]** => {HOST.NAME} Low Temperature Warning: ({ITEM.VALUE})
  * **[WARNING]** => {HOST.NAME} Temperature Sensor Abnormal: ({ITEM.VALUE})

Graphs
--------

  * Humidity
  * Temperature

Installation
------------

1. Add a value mapping named `hhmsSensorOnline` with the following values:
  * 1 ⇒ online
  * 2 ⇒ offline
2. Add a value mapping named `hhmsSensorStatus` with the following values:
  * 1 ⇒ noStatus
  * 2 ⇒ normal
  * 3 ⇒ highWarning
  * 4 ⇒ highCritical
  * 5 ⇒ lowWarning
  * 6 ⇒ lowCritical
  * 7 ⇒ sensorError
4. Ensure each sensor to be monitored on the device is configured with its threshold and rearm values, as these are used for the triggers within Zabbix.
5. Add to your host the **{$SNMP_COMMUNITY}** macro with your SNMP community as value.
6. Associate the **ZBX-AKCP-SP2** template to the host.

To-Do
------------

  * Implement discovery for sensors. Currently this template assumes that the device will have a Temperature sensor connected on Port 1, and a Humidity sensor connected on Port 2.
  * Refine the alerting logic
  * Implement support for other sensor types

Requirements
------------

This template was tested on Zabbix 2.4.6. The template currently only supports Temperature and Humidity sensors, largely because my test sensor is a unit that's old enough to vote in Australia!

AKCP appears to OEM sensors for a number of other companies - my test unit is a 'Netic', but I have also seen them being sold under the 'Jacarta' and 'Didactum' brands, amongst others. In most cases the unit itself is still badged as a 'SensorProbe' or 'SensorProbe2'.

License
-------

This template is distributed under the terms of the BSD New License as published by the Regents of the University of California.

### Copyright

  Copyright (c) Brad Peczka

### Authors
  
  Brad Peczka
  (brad |at| bradpeczka |dot| com)
