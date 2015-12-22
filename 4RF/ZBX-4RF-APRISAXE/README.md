ZBX-4RF-APRISAXE
==============

This template uses the 4RF-APRISAXE-MIB to discover and monitor AprisaXE Microwave systems.

Items
-----

  * Correctable Error Count
  * Errored Seconds
  * Error Free Seconds
  * External Alarm 1 - Description
  * External Alarm 1 - Enabled
  * External Alarm 1 - Mapping
  * External Alarm 1 - Polarity
  * External Alarm 1 - Severity
  * External Alarm 1 - Status
  * External Alarm 2 - Description
  * External Alarm 2 - Enabled
  * External Alarm 2 - Mapping
  * External Alarm 2 - Polarity
  * External Alarm 2 - Severity
  * External Alarm 2 - Status
  * Fan 1 - Status
  * Fan 2 - Status
  * Fans Enabled
  * HSD Parameter Checking
  * HSD Parameter Mismatch
  * Modem Demod Aligment Status
  * Modem Frequency Offset Enable
  * Modem Interleaver Enable
  * Modem Interleaver State
  * Modem Mute Capability
  * Modem Mute State
  * Modem QPSK Coding
  * Modem RefA Clock Status
  * Modem RefB Clock Status
  * Modem SNR
  * Modem Summary Alarm Status
  * Modem Sync Status
  * Modem TDMA Alignment Status
  * Motherboard Serial Number
  * Motherboard Verson
  * Receiver 12V Status
  * Receiver Frequency
  * Receiver RSSI
  * Receiver Serial Number
  * Receiver Status
  * Receiver Synthesiser Status
  * Receiver Temperature
  * RX Packet Count
  * RX Packet Error Count
  * Terminal Alarm Status
  * Terminal Allocated Bandwidth
  * Terminal Bandwidth
  * Terminal Clock Reference
  * Terminal Equipment Type
  * Terminal Loopback Bandwidth
  * Terminal Modulation State
  * Terminal RF Channel Width
  * Terminal RSSI
  * Terminal RX Alarm Status
  * Terminal Startup Status
  * Terminal TX Alarm Status
  * Transmitter +5V Power Status
  * Transmitter -5V Power Status
  * Transmitter 11V Power Status
  * Transmitter 12V Power Status
  * Transmitter 20V Power Status
  * Transmitter 28V Power Status
  * Transmitter Amplifier Balance Status
  * Transmitter Frequency
  * Transmitter PAI
  * Transmitter Power
  * Transmitter Return Loss
  * Transmitter Serial Number
  * Transmitter Status
  * Transmitter Synthesiser Status
  * Transmitter Temperature
  * TX Packet Count
  * Uncorrectable Error Count
  * Discovery: Board Firmware Version
  * Discovery: Board Hardware Version
  * Discovery: Board HSC Number
  * Discovery: Board Serial Number
  * Discovery: Installed Board
  * Discovery: Expected Board

Triggers
--------

  * **[CRITICAL]** => Modem Mute State: Modem Mute [{ITEM.VALUE}] on {HOST.NAME}
  * **[CRITICAL]** => Terminal Alarm Status: Terminal Status changed to CRITICAL
  * **[HIGH]** => Fan 1 - Status: Fan #1 failed on {HOST.NAME}
  * **[HIGH]** => Fan 2 - Status: Fan #2 failed on {HOST.NAME}
  * **[DEGRADED]** => Terminal Alarm Status: Terminal Status changed to MAJOR ALARM
  * **[WARNING]** => Modem SNR: SNR is too low on {HOST.NAME}
  * **[WARNING]** => Terminal RSSI: RSSI is too high on {HOST.NAME}
  * **[INFORMATION]** => Motherboard Serial Number: Motherboard serial number changed on {HOST.NAME}
  * **[INFORMATION]** => Receiver Serial Number: Receiver serial number changed on {HOST.NAME}
  * **[INFORMATION]** => Transmitter Serial Number: Transmitter serial number changed on {HOST.NAME}
  * **[INFORMATION]** => Terminal Alarm Status: Terminal Status changed to MINOR ALARM

Graphs
--------

  * 4RF Health Statistics

Installation
------------

1. Add a value mapping named `aprisaXEAlarmMapping` with the following values:
  * 0 ⇒ none
  * 1 ⇒ localMajor
  * 2 ⇒ localMinor
  * 3 ⇒ remoteMajor
  * 4 ⇒ remoteMinor
  * 5 ⇒ remoteInput1
  * 6 ⇒ remoteInput2
  * 7 ⇒ testMajor
  * 8 ⇒ testMinor
2. Add a value mapping named `aprisaXEAlarmPolarity` with the following values:
  * 0 ⇒ polarityLow
  * 1 ⇒ polarityHigh
3. Add a value mapping named `aprisaXECardType` with the following values:
  * 0 ⇒ none
  * 197 ⇒ singleJETCard
  * 213 ⇒ dualJETCard
  * 224 ⇒ motherboard
  * 227 ⇒ transmitterCard
  * 228 ⇒ receiverCard
  * 229 ⇒ quadJETCard
  * 231 ⇒ quadFourWireCard
  * 232 ⇒ dualFXOCard
  * 233 ⇒ dualFXSCard
  * 234 ⇒ modemCard
  * 235 ⇒ quadV24Card
  * 236 ⇒ hssCard
  * 237 ⇒ pscCard
  * 238 ⇒ picCard
  * 251 ⇒ quadSyncV24Card
4. Add a value mapping named `aprisaXEFanEnable` with the following values:
  * 0 ⇒ fansDisabled
  * 1 ⇒ fansEnabled
5. Add a value mapping named `aprisaXEModemFreqOffsetEnable` with the following values:
  * 0 ⇒ offsetDisabled
  * 1 ⇒ offsetEnabled
6. Add a value mapping named `aprisaXEModemInterleaverState` with the following values:
  * 100 ⇒ interleaverEnabled
  * 101 ⇒ interleaverDisabled
  * 102 ⇒ interleaverDefault
7. Add a value mapping named `aprisaXEModemMuteCapability` with the following values:
  * 0 ⇒ notCapable
  * 1 ⇒ capable
8. Add a value mapping named `aprisaXEModemQPSKCoding` with the following values:
  * 0 ⇒ grayCoded
  * 1 ⇒ nonGrayCoded
9. Add a value mapping named `aprisaXETerminalClockReference` with the following values:
  * 0 ⇒ automatic
  * 1 ⇒ manual
10. Add a value mapping named `aprisaXETerminalEquipmentType` with the following values:
  * 0 ⇒ unknown
  * 1 ⇒ radio
  * 2 ⇒ mux
  * 3 ⇒ protectionSwitch
  * 4 ⇒ protectionRadio
  * 5 ⇒ radioNoMux
11. Add a value mapping named `aprisaXETerminalModulationState` with the following values:
  * 0 ⇒ QPSK
  * 1 ⇒ 16 QAM
  * 2 ⇒ 32 QAM
  * 3 ⇒ 64 QAM
  * 4 ⇒ 128 QAM
  * 5 ⇒ 256 QAM
12. Add a value mapping named `aprisaXETerminalStartupComplete` with the following values:
  * 0 ⇒ notComplete
  * 1 ⇒ startupComplete
13. Add a value mapping named `fourRFAlarmEnabled` with the following values:
  * 0 ⇒ disabled
  * 1 ⇒ enabled
14. Add a value mapping named `fourRFAlarmSeverity` with the following values:
  * 0 ⇒ noSeverity
  * 3 ⇒ minor
  * 4 ⇒ major
15. Add a value mapping named `fourRFAlarmStatus` with the following values:
  * 0 ⇒ noAlarm
  * 1 ⇒ informationAlarm
  * 2 ⇒ warningAlarm
  * 3 ⇒ minorAlarm
  * 4 ⇒ majorAlarm
  * 5 ⇒ criticalAlarm
16. Add a value mapping named `fourRFFanStatus` with the following values:
  * 0 ⇒ notFitted
  * 1 ⇒ fanOK
  * 2 ⇒ fanFailed
17. Add a value mapping named `fourRFOffOn` with the following values:
  * 0 ⇒ off
  * 1 ⇒ on
18. Add to your host the **{$SNMP_COMMUNITY}** macro with your SNMP community as value.
19. Associate **ZBX-4RF-APRISAXE** template to the host.

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
