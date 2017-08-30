ZBX-EATON-XUPS
==============

This template uses the XUPS-MIB to discover and monitor UPS systems.

Items
-----

  * Battery - ABM Status
  * Battery - Capacity
  * Battery - Current
  * Battery - Last Replaced Date
  * Battery - Last Test Status
  * Battery - Runtime
  * Battery - Voltage
  * Bypass - Frequency
  * Bypass - Number of Phases
  * Config - High Output Voltage Limit
  * Config - Input Voltage
  * Config - Install Date
  * Config - Low Output Voltage Limit
  * Config - Output Frequency
  * Config - Output Voltage
  * Config - Output Watts
  * Environment - Ambient Humidity
  * Environment - Ambient Temperature
  * Environment - Ambient Temperature Lower Limit
  * Environment - Ambient Temperature Upper Limit
  * Environment - Remote Humidity
  * Environment - Remote Humidity Lower Limit
  * Environment - Remote Humidity Upper Limit
  * Environment - Remote Temperature
  * Environment - Remote Temperature Lower Limit
  * Environment - Remote Temperature Upper Limit
  * Input - Current Source
  * Input - Dual Input Status
  * Input - Frequency
  * Input - Number of Line Bads
  * Input - Number of Phases
  * Output - Current Source
  * Output - Frequency
  * Output - Load
  * Output - Number of Phases
  * UPS - Last Test Status
  * UPS Agent Version
  * UPS Contact
  * UPS Location
  * UPS Manufacturer
  * UPS Model
  * UPS Name
  * UPS Serial Number
  * UPS Software Version
  * Discovery: Nypass Phase Voltage
  * Discovery: Input Phase Current
  * Discovery: Input Phase Voltage
  * Discovery: Input Phase Watts
  * Discovery: Output Phase Current
  * Discovery: Output Phase Voltage
  * Discovery: Output Phase Watts

Triggers
--------

  * **[CRITICAL]** => {HOST.NAME} Battery Runtime <5mins ({ITEM.VALUE1})
  * **[CRITICAL]** => {HOST.NAME} Output Load >100% ({ITEM.VALUE1})
  * **[HIGH]** => {HOST.NAME} Battery Runtime <15mins ({ITEM.VALUE1})
  * **[HIGH]** => {HOST.NAME} Output Load >90% ({ITEM.VALUE1})
  * **[DEGRADED]** => {HOST.NAME} Battery Test ({ITEM.VALUE1})
  * **[DEGRADED]** => {HOST.NAME} Input Source changed to {ITEM.VALUE1}
  * **[DEGRADED]** => {HOST.NAME} Output Source changed to {ITEM.VALUE1}
  * **[WARNING]** => {HOST.NAME} Battery Level <50% ({ITEM.VALUE1})
  * **[WARNING]** => {HOST.NAME} Output Load >75% ({ITEM.VALUE1})

Graphs
--------

  * Battery - ABM/Test Status
  * Battery - Capacity/Runtime
  * Battery - Current/Voltage
  * Environment - Ambient Temperature/Humidity
  * Frequencies - Bypass/Input/Output
  * Output - Load
  * Discovery: Bypass - Phase Current
  * Discovery: Bypass - Phase Voltage
  * Discovery: Bypass - Phase Watts
  * Discovery: Input - Phase Current
  * Discovery: Input - Phase Voltage
  * Discovery: Input - Phase Watts
  * Discovery: Output - Phase Current
  * Discovery: Output - Phase Voltage
  * Discovery: Output - Phase Watts

Installation
------------

1. Add a value mapping named `xupsBatteryAbmStatus` with the following values:
  * 1 ⇒ batteryCharging
  * 2 ⇒ batteryDischarging
  * 3 ⇒ batteryFloating
  * 4 ⇒ batteryResting
  * 5 ⇒ unknown
2. Add a value mapping named `xupsDualInputStatus` with the following values:
  * 1 ⇒ bothSourcesBad
  * 2 ⇒ primarySourceGood
  * 3 ⇒ secondarySourceGood
  * 4 ⇒ bothSourcesGood
3. Add a value mapping named `xupsInputSource` with the following values:
  * 1 ⇒ other
  * 2 ⇒ none
  * 3 ⇒ primaryUtility
  * 4 ⇒ bypassFeed
  * 5 ⇒ secondaryUtility
  * 6 ⇒ generator
  * 7 ⇒ flywheel
  * 8 ⇒ fuelcell
4. Add a value mapping named `xupsOutputSource` with the following values:
  * 1 ⇒ other
  * 2 ⇒ none
  * 3 ⇒ normal
  * 4 ⇒ bypass
  * 5 ⇒ battery
  * 6 ⇒ booster
  * 7 ⇒ reducer
  * 8 ⇒ parallelCapacity
  * 9 ⇒ parallelRedundant
  * 10 ⇒ highEfficiencyMode
  * 11 ⇒ maintenanceBypass
5. Add a value mapping named `xupsTestBatteryStatus` with the following values:
  * 1 ⇒ unknown
  * 2 ⇒ passed
  * 3 ⇒ failed
  * 4 ⇒ inProgess
  * 5 ⇒ notSupported
  * 6 ⇒ inhibited
  * 7 ⇒ scheduled
6. Add to your host the **{$SNMP_COMMUNITY}** macro with your SNMP community as value.
7. Associate **ZBX-EATON-XUPS** template to the host.

Requirements
------------

This template was tested on Zabbix 2.4.6, and will work with UPSes from a varity of brands including: Eaton, Exide, Powerware and Sola. 

Compatibility has been tested on the following management cards and firmware versions:

* Eaton ConnectUPS-BD Web/SNMP Card, P/N 116750222, Firmware v4.38
* Eaton ConnectUPS-MS Web/SNMP Card, P/N 103006826, Firmware v4.38
* Eaton ConnectUPS-X Web/SNMP Card, P/N 116750221, Firmware v4.38
* Eaton SNMP/Web Minislot Network Card, P/N NETWORK-MS, Firmware 'HF'
* Eaton SNMP/Web Minislot Network Card, P/N NETWORK-MS, Firmware 'JC' 

License
-------

This template is distributed under the terms of the BSD New License as published by the Regents of the University of California.

### Copyright

  Copyright (c) Brad Peczka

### Authors
  
  Brad Peczka
  (brad |at| bradpeczka |dot| com)
