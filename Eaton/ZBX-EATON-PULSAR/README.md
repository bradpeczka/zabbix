ZBX-EATON-PULSAR
==============

This template uses the MG-SNMP-UPS-MIB to discover and monitor UPS systems.

Items
-----

  * Battery - Capacity
  * Battery - Current
  * Battery - Last Calibration Date
  * Battery - Last Test Result
  * Battery - Restart Capacity
  * Battery - Runtime
  * Battery - Temperature
  * Battery - Test Schedule
  * Battery - Time until Fully Charged
  * Battery - Time until Restart Charged
  * Battery - Voltage
  * Battery Status - Fault
  * Battery Status - Low Battery
  * Battery Status - Low Condition
  * Battery Status - Needs to be replaced
  * Battery Status - No Battery
  * Battery Status - Not Charging
  * Battery Status - Not High Charge
  * Battery Status - Not Recharged
  * Battery Status - Unavailable
  * Config - Alarm on Battery Test Failure
  * Config - Alarm on Bypass
  * Config - Alarm on Overload
  * Config - Audible Alarm Delay
  * Config - Audible Alarm Enabled
  * Config - Auto Restart Enabled
  * Config - Battery Installed
  * Config - Bypass Type
  * Config - High Voltage Transfer Point
  * Config - Low Battery Level
  * Config - Low Battery Time
  * Config - Low Voltage Transfer Point
  * Config - Nominal Battery Voltage
  * Config - Nominal Output Current
  * Config - Nominal Output Frequency
  * Config - Nominal Output Voltage
  * Config - VA Rating
  * Environment - Ambient Humidity
  * Environment - Ambient Temperature
  * Input - Number of Phases
  * Input Status - Bad Voltage/Frequency
  * Input Status - Line Fail Cause
  * Output - Number of Phases
  * Output Status - Bypass Unavailable
  * Output Status - Inverter Off
  * Output Status - No Bypass Installed
  * Output Status - On Battery
  * Output Status - On Boost
  * Output Status - On Buck
  * Output Status - Overload
  * Output Status - Over Temperature
  * Output Status - Utility Off
  * UPS Contact
  * UPS FW Revision
  * UPS HW Revision
  * UPS Install Date
  * UPS Location
  * UPS Manufacturer
  * UPS Name
  * UPS Serial Number
  * Discovery: Environment Sensor Comms Failure
  * Discovery: Environment Sensor Humidity
  * Discovery: Environment Sensor Temperature
  * Discovery: Input Phase Current
  * Discovery: Input Phase Frequency
  * Discovery: Input Phase Maximum Voltage (1 minute)
  * Discovery: Input Phase Minimum Voltage (1 minute)
  * Discovery: Input Phase Voltage
  * Discovery: Output Phase Current
  * Discovery: Output Phase Frequency
  * Discovery: Output Phase Load
  * Discovery: Output Phase Voltage


Triggers
--------

  * **[CRITICAL]** => Battery Runtime <5min ({ITEM.VALUE1})
  * **[CRITICAL]** => Input - Cause of Input Line Fail {ITEM.VALUE1}
  * **[HIGH]** => Battery FAULT ({ITEM.VALUE1})
  * **[HIGH]** => Battery Low ({ITEM.VALUE1})
  * **[HIGH]** => Battery Needs to be replaced ({ITEM.VALUE1})
  * **[HIGH]** => Battery Runtime <15min ({ITEM.VALUE1})
  * **[HIGH]** => Battery - NO battery ({ITEM.VALUE1})
  * **[HIGH]** => Battery - Non High Charge ({ITEM.VALUE1})
  * **[HIGH]** => Battery - Not charging ({ITEM.VALUE1})
  * **[HIGH]** => Battery - Not Recharged ({ITEM.VALUE1})
  * **[HIGH]** => Battery - Status Unavailable ({ITEM.VALUE1})
  * **[HIGH]** => Input - Bad Voltage/Frequency {ITEM.VALUE1}
  * **[DEGRADED]** => Output - Bypass Unavailable ({ITEM.VALUE1})
  * **[DEGRADED]** => Output - Inverter Off ({ITEM.VALUE1})
  * **[DEGRADED]** => Output - No Bypass Installed ({ITEM.VALUE1})
  * **[DEGRADED]** => Output - On Boost ({ITEM.VALUE1})
  * **[DEGRADED]** => Output - On Battery ({ITEM.VALUE1})
  * **[DEGRADED]** => Output - On Bypass ({ITEM.VALUE1})
  * **[DEGRADED]** => Output - On Fader (on buck) ({ITEM.VALUE1})
  * **[DEGRADED]** => Output - Over Load ({ITEM.VALUE1})
  * **[DEGRADED]** => Output - Over Temperature ({ITEM.VALUE1})
  * **[DEGRADED]** => Output - Utility Off({ITEM.VALUE1})
  * **[WARNING]** => Battery Level <50% ({ITEM.VALUE1})
  * **[CRITICAL]** => Discovery: Input - Phase {#SNMPINDEX} Voltage not in limits 177-250 V ({ITEM.VALUE1})

Graphs
--------

  * Battery - Capacity/Runtime
  * Battery - Current/Voltage
  * Battery - Ambient Temperature/Humidity
  * Discovery: Environment - Sensor Humidity
  * Discovery: Environment - Sensor Temperature
  * Discovery: Input - Phase Current
  * Discovery: Input - Phase Frequency
  * Discovery: Input - Phase Voltage
  * Discovery: Output - Phase Current
  * Discovery: Output - Phase Frequency
  * Discovery: Output - Phase Load
  * Discovery: Output - Phase Voltage

Installation
------------

1. Add a value mapping named `upsmgConfigAutoRestart` with the following values:
  * 1 ⇒ always
  * 2 ⇒ never
  * 3 ⇒ onMains
2. Add a value mapping named `upsmgConfigByPassType` with the following values:
  * 1 ⇒ none
  * 2 ⇒ relay
  * 3 ⇒ static
3. Add a value mapping named `upsmgInputLineFailCause` with the following values:
  * 1 ⇒ none
  * 2 ⇒ outOfVoltageTolerance
  * 3 ⇒ outOfFrequencyTolerance
  * 4 ⇒ utilityOff
4. Add a value mapping named `upsmgStatusYesNo` with the following values:
  * 1 ⇒ yes
  * 2 ⇒ no
5. Add a value mapping named `upsmgTestBatterySchedule` with the following values:
  * 1 ⇒ unknown
  * 2 ⇒ weekly
  * 3 ⇒ monthly
  * 4 ⇒ atTurnOn
  * 5 ⇒ none
  * 6 ⇒ daily
6. Add a value mapping named `upsmgTestDiagResult` with the following values:
  * 1 ⇒ success
  * 2 ⇒ failed
  * 3 ⇒ none
7. Add to your host the **{$SNMP_COMMUNITY}** macro with your SNMP community as value.
8. Associate **ZBX-EATON-PULSAR** template to the host.

Requirements
------------

This template was tested on Zabbix 2.4.6, and will work with UPSes from a varity of brands including: Dell, Eaton, MGE, Merlin Gerin, and Powerware. 

Compatibility has been tested on the following management cards and firmware versions:
* Eaton SNMP/Web Minislot Network Card, P/N NETWORK-MS, Firmware 'HF'
* MGE Network Management Card Transverse, P/N 66074, Firmware 'KC'

License
-------

This template is distributed under the terms of the BSD New License as published by the Regents of the University of California.

### Copyright

  Copyright (c) Brad Peczka

### Authors
  
  Brad Peczka
  (brad |at| bradpeczka |dot| com)
