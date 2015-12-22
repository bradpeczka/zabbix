ZBX-UBNT-AIRMAX
==============

This template uses the UBNT-AIRMAX-MIB to discover and monitor Ubiquiti Networks AirMAX radios.

Items
-----

  * Discovery: airMAX Capacity
  * Discovery: airMAX Status
  * Discovery: airMAX NoACK Status
  * Discovery: airMAX Priority
  * Discovery: airMAX Quality
  * Discovery: airSelect Hop Interval
  * Discovery: airSelect Status
  * Discovery: Radio Antenna Type
  * Discovery: Radio Configured Power
  * Discovery: Radio Country Code
  * Discovery: Radio Chainmask
  * Discovery: Radio DFS Status
  * Discovery: Radio Distance
  * Discovery: Radio Operating Frequency
  * Discovery: Radio Mode
  * Discovery: Chain Data RSSI
  * Discovery: Chain Extension RSSI
  * Discovery: Chain Management RSSI
  * Discovery: Wireless CCQ
  * Discovery: Wireless Channel Width
  * Discovery: Wireless Connected Clients
  * Discovery: Wireless MAC Address
  * Discovery: Wireless Noise Floor
  * Discovery: Wireless Repeater Status
  * Discovery: Wireless RSSI
  * Discovery: Wireless RX Rate
  * Discovery: Wireless Security Mode
  * Discovery: Wireless Signal Strength
  * Discovery: Wireless SSID Broadcast
  * Discovery: Wireless TX Rate
  * Discovery: Wireless WDS Status

Installation
------------

1. Add a value mapping named `ubntAirMaxPriority` with the following values:
  * 0 ⇒ high
  * 1 ⇒ medium
  * 2 ⇒ low
  * 3 ⇒ none
2. Add a value mapping named `ubntEnabledDisabled` with the following values:
  * 1 ⇒ enabled
  * 2 ⇒ disabled
3. Add a value mapping named `ubntRadioChainmask` with the following values:
  * 1 ⇒ chain0Active
  * 2 ⇒ chain1Active
  * 3 ⇒ bothChainsActive
4. Add a value mapping named `ubntRadioMode` with the following values:
  * 1 ⇒ station
  * 2 ⇒ ap
  * 3 ⇒ apRepeater
  * 4 ⇒ apWDS
5. Add to your host the **{$SNMP_COMMUNITY}** macro with your SNMP community as value.
6. Associate **ZBX-UBNT-AIRMAX** template to the host.

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
