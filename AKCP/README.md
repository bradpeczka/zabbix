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
3. Add to your host the **{$SNMP_COMMUNITY}** macro with your SNMP community as value.
4. Associate **ZBX-AKCP-SP2** template to the host.

To-Do
------------

  * Implement discovery for sensors
  * Refine the alerting logic
  * Implement support for other sensor types

Requirements
------------

This template was tested on Zabbix 2.4.6. The template currently only supports Temperature and Humidity sensors, largely because my test sensor is a unit that's old enough to vote in Australia!

License
-------

This template is distributed under the terms of the BSD New License as published by the Regents of the University of California.

### Copyright

  Copyright (c) Brad Peczka

### Authors
  
  Brad Peczka
  (brad |at| bradpeczka |dot| com)
