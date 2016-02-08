ZBX-LIEBERT-CRAC
==============

This template uses the LIEBERT-GP-ENVIRONMENTAL-MIB to discover and monitor Emerson Liebert CRAC units using SNMP.

Items
-----

  * Agent - FW Version
  * Agent - Manufacturer
  * Agent - Model
  * Agent - Part Number
  * Agent - Serial Number
  * Config - Auto Configuration
  * Config - BMS Reset Timer
  * Config - Cabinet Sensor Alarms
  * Config - Chilled Water Control
  * Config - Compressor Lockout
  * Config - Cooling Service Interval
  * Config - Fan Speed Capacity
  * Config - Fan Speed Mode
  * Config - Filter Service Interval
  * Config - Humidifier Lockout
  * Config - Humidifier Service Interval
  * Config - Humidity Control
  * Config - Infrared Flush Rate
  * Config - Local Temperature Unit
  * Config - Reheat & Humidifier Lockout
  * Config - Reheat Lockout
  * Config - Remote Shutdown
  * Config - Restart Delay
  * Config - Sensor #1 Events
  * Config - Sensor Offset
  * Config - Sleep Mode
  * Config - Sleep Mode Deadband Range
  * Config - Standard Sensor Events
  * Config - Supply Temperature Low Limit
  * Config - Supply Temperature Low Setpoint
  * Config - Temperature Control Algorithm
  * Humidity - Control Measurement
  * Humidity - Return Air
  * Humidity - Setpoint
  * Humidity - Tolerance
  * Statistics - Compressor #1 Run Time
  * Statistics - Compressor #2 Run Time
  * Statistics - Compressor #3 Run Time
  * Statistics - Compressor #4 Run Time
  * Statistics - Cooling Mode Run Time
  * Statistics - Dehumidify Mode Run Time
  * Statistics - Fan Run Time
  * Statistics - Free Cooling Run Time
  * Statistics - Heating Mode Run Time
  * Statistics - Hot Gas Run Time	
  * Statistics - Hot Water Run Time
  * Statistics - Humidifier Run Time
  * Statistics - Humidify Mode Run Time
  * Statistics - Reheat #1 Run Time
  * Statistics - Reheat #2 Run Time
  * Statistics - Reheat #3 Run Time
  * Status - Audible Alarm Output
  * Status - Cooling
  * Status - Dehumidifying
  * Status - Econocycle
  * Status - Electric Heater
  * Status - Fan
  * Status - Free Cooling
  * Status - General Alarm Output
  * Status - Heating
  * Status - Hot Water
  * Status - Humidifying
  * Status - Operating Mode
  * Status - Operating Reason
  * Status - System
  * Status - Utilised Cooling Capacity
  * Status - Utilised Dehumidifying Capacity
  * Status - Utilised Fan Capacity
  * Status - Utilised Heating Capacity	
  * Status - Utilised Humidifying Capacity
  * Temperature - Control Measurement
  * Temperature - Digital Scroll Compressor #1
  * Temperature - Digital Scroll Compressor #2
  * Temperature - Return Air
  * Temperature - Setpoint
  * Temperature - Supply Air
  * Temperature - Tolerance
  * Discovery: Managed Device - FW Version
  * Discovery: Managed Device - Manufacturer
  * Discovery: Managed Device - Manufacturing Date
  * Discovery: Managed Device - Model
  * Discovery: Managed Device - Name
  * Discovery: Managed Device - Serial Number
  * Discovery: Managed Device - Service Address #1
  * Discovery: Managed Device - Service Address #2
  * Discovery: Managed Device - Service Address #3
  * Discovery: Managed Device - Service Address #4
  * Discovery: Managed Device - Service Phone Number
  * Discovery: Managed Device - Site
  * Discovery: Managed Device - Tag Number

Triggers
--------

  * **[CRITICAL]** => {HOST.NAME} General Alarm Output is ({ITEM.VALUE1})
  * **[HIGH]** => {HOST.NAME} High Humidity Alarm: ({ITEM.VALUE1})
  * **[HIGH]** => {HOST.NAME} High Temperature Alarm: ({ITEM.VALUE1})
  * **[HIGH]** => {HOST.NAME} Low Humidity Alarm: ({ITEM.VALUE1})
  * **[HIGH]** => {HOST.NAME} Low Temperature Alarm: ({ITEM.VALUE1})
  * **[WARNING]** => {HOST.NAME} Audible Alarm Output is ({ITEM.VALUE1})
  * **[CRITICAL]** => {HOST.NAME} power changed to {ITEM.VALUE1}

Graphs
--------

  * Temperature & Humidity
  
Installation
------------

1. Add a value mapping named `lgpEnvConfigDisabledEnabled` with the following values:
  * 1 ⇒ enabled
  * 2 ⇒ disabled
2. Add a value mapping named `lgpEnvConfigHumidityControl` with the following values:
  * 1 ⇒ relative
  * 2 ⇒ compensated
  * 3 ⇒ predictive
3. Add a value mapping named `lgpEnvConfigLocalTemperatureUnit` with the following values:
  * 1 ⇒ celsius
  * 2 ⇒ farenheit
4. Add a value mapping named `lgpEnvConfigLockout` with the following values:
  * 1 ⇒ lockedOut
  * 2 ⇒ notLockedOut
5. Add a value mapping named `lgpEnvConfigManualAuto` with the following values:
  * 1 ⇒ manual
  * 2 ⇒ auto
6. Add a value mapping named `lgpEnvConfigLockout` with the following values:
  * 1 ⇒ lockedOut
  * 2 ⇒ notLockedOut
7. Add a value mapping named `lgpEnvConfigSleepMode` with the following values:
  * 1 ⇒ enabled
  * 2 ⇒ disabled
  * 3 ⇒ auto
8. Add a value mapping named `lgpEnvConfigTempControlAlgorithm` with the following values:
  * 1 ⇒ pi
  * 2 ⇒ pid
  * 3 ⇒ intelligent
  * 4 ⇒ proportional
9. Add a value mapping named `lgpEnvStateFreeCooling` with the following values:
  * 1 ⇒ on
  * 2 ⇒ off
  * 3 ⇒ start
  * 4 ⇒ unavailable
10. Add a value mapping named `lgpEnvStateOnOffStby` with the following values:
  * 1 ⇒ on
  * 2 ⇒ off
  * 3 ⇒ standby
11. Add a value mapping named `lgpEnvStateOperatingMode` with the following values:
  * 1 ⇒ manual
  * 2 ⇒ auto
12. Add a value mapping named `lgpEnvStateOperatingReason` with the following values:
  * 1 ⇒ none
  * 2 ⇒ localUser
  * 3 ⇒ alarm
  * 4 ⇒ schedule
  * 5 ⇒ remoteUser
  * 6 ⇒ externalDevice
  * 7 ⇒ localDisplay
13. Add to your host the **{$SNMP_COMMUNITY}** macro with your SNMP community as value.
14. Associate **ZBX-LIEBERT-CRAC** template to the host.

Requirements
------------

This template was tested on Zabbix 2.4.6.

License
-------

This template is distributed under the terms of the BSD New License as published by the Regents of the University of California.

### Copyright

  Copyright (c) Brad Peczka

### Authors
  
  Brad Peczka
  (brad |at| bradpeczka |dot| com)
