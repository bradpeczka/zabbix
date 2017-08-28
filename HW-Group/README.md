ZBX-HWG-DAMOCLES
==============

This template uses the DAMOCLES-MIB to discover and monitor HW-Group Damociles DI/DO devices using SNMP.

Items
-----

  * Discovery: Input Alarm State
  * Discovery: Input Name
  * Discovery: Input Number of State Changes
  * Discovery: Input Status
  * Discovery: Output Status
  * Discovery: Output Name
  * Discovery: Output Mode
  * Discovery: Output Type
  * Discovery: Output Default State
  * Discovery: Sensor Status
  * Discovery: Sensor Name
  * Discovery: Sensor Value

Triggers
--------

  * **[HIGH]** => {HOST.NAME} {#SNMPVALUE} Alarm
  * **[INFORMATONAL]** => {#SNMPVALUE} output status was changed on {HOST.NAME}
  * **[INFORMATIONAL]** => {#SNMPVALUE} input status was changed on {HOST.NAME}

Installation
------------

1. Add a value mapping named `damoclesInputAlarmState` with the following values:
  * 0 ⇒ normal
  * 1 ⇒ alarm
2. Add a value mapping named `damoclesOnOff` with the following values:
  * 0 ⇒ off
  * 1 ⇒ on
  * 2 ⇒ offIfAnyAlarm
  * 3 ⇒ onIfAnyAlarm
3. Add a value mapping named `damoclesOutputMode` with the following values:
  * 0 ⇒ manual
  * 1 ⇒ autoAlarm
  * 2 ⇒ autoTriggerEq
  * 3 ⇒ autoTriggerHi
  * 4 ⇒ autoTriggerLo
  * 5 ⇒ autoGroupOn
4. Add a value mapping named `damoclesOutputType` with the following values:
  * 0 ⇒ onOff
  * 1 ⇒ rts
  * 2 ⇒ dtr
5. Add to your host the **{$SNMP_COMMUNITY}** macro with your SNMP community as value.
6. Associate **ZBX-HWG-DAMOCLES** template to the host.

Requirements
------------

This template was tested on Zabbix 2.4.6. The Sensor Discovery rule has not been tested, due to my test device not having this functionality, but *should* work out of the box.

License
-------

This template is distributed under the terms of the BSD New License as published by the Regents of the University of California.

### Copyright

  Copyright (c) Brad Peczka

### Authors
  
  Brad Peczka
  (brad |at| bradpeczka |dot| com)
