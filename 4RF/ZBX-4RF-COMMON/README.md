ZBX-4RF-COMMON
==============

This template uses the 4RF-COMMON-MIB to discover management information from 4RF products.

Items
-----

  * Last Reset Type
  * Local Radio A IP Address
  * Local Radio B IP Address
  * Remote IP Address
  * Remote Radio B IP Address
  * System ID
  * System IP Address
  * System Serial Number
  * System Software Version

Triggers
--------

  * **[WARNING]** => Last Reset Type: Hardware watchdog has just rebooted {HOST.NAME}
  * **[INFORMATION]** => System Serial Number: System serial number changed on {HOST.NAME}
  * **[INFORMATION]** => System Software Version: System software version changed on {HOST.NAME}

Installation
------------

1. Add a value mapping named `fourRFResetType` with the following values:
  * 0 ⇒ none
  * 1 ⇒ softReset
  * 2 ⇒ hardReset
  * 3 ⇒ watchdogReset
2. Add to your host the **{$SNMP_COMMUNITY}** macro with your SNMP community as value.
3. Associate **ZBX-4RF-COMMON** template to the host.

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
