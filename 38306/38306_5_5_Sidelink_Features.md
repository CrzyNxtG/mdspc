## 5.5 Sidelink Features

+-----------------------------------------------------------------------+
| Definitions for feature                                               |
+-----------------------------------------------------------------------+
| **CW autonomous update for SL transmission without HARQ feedback**    |
|                                                                       |
| It is optional for UE to support autonomous update of the CW~p~ to    |
| the next higher allowed value when the same CW~p~ ≠ CW~max,p~ value   |
| is consecutively used for X times for generation of N~init~ for       |
| PSCCH/PSSCH transmission without HARQ feedback for a band where       |
| shared spectrum channel access must be used.                          |
|                                                                       |
| A UE supporting this feature shall also indicate the support of       |
| *sl-DynamicChannelAccess-r18*.                                        |
+-----------------------------------------------------------------------+
| **Rank 2 PSSCH transmission**                                         |
|                                                                       |
| It is optional for UE to support rank 2 PSSCH transmission. This      |
| field is only applicable if the UE supports *csi-ReportSidelink-r16*  |
| with *csi-RS-PortsSidelink* = p2.                                     |
+-----------------------------------------------------------------------+
| **Receiving NR sidelink of S-SSB**                                    |
|                                                                       |
| It is optional for UE to receive S-SSB in NR sidelink and support     |
| synchronisation to a reference UE.                                    |
+-----------------------------------------------------------------------+
| **Receiving PSCCH/PSSCH from 2^nd^ starting symbol in a slot**        |
|                                                                       |
| It is optional for UE to support receiving PSCCH/PSSCH from 2^nd^     |
| starting symbol in a slot in addition to the first starting symbol    |
| for a band where shared spectrum channel access is used.              |
|                                                                       |
| A UE supporting this feature shall also indicate support of           |
| *sl-Reception-r16*.                                                   |
+-----------------------------------------------------------------------+
| **Receiving S-SSB on additional S-SSB occasion(s)**                   |
|                                                                       |
| It is optional for UE to support receiving S-SSB on additional S-SSB  |
| occasion(s).                                                          |
|                                                                       |
| A UE supporting this feature shall also indicate support of           |
| *channelBWs-DL-SCS-960kHz-FR2-2-r17* and                              |
| *channelBWs-UL-SCS-960kHz-FR2-2-r17*.                                 |
+-----------------------------------------------------------------------+
| **Resource allocation for multi-consecutive slots transmission**      |
|                                                                       |
| It is optional for UE to support resource (re-)selection for          |
| PSCCH/PSSCH transmission on multiple consecutive slots.               |
|                                                                       |
| A UE supporting this feature shall also indicate support of at least  |
| one of *sl-TransmissionMode2-r16* and                                 |
| *sl-TransmissionMode2-PartialSensing-r17*.                            |
+-----------------------------------------------------------------------+
| **S-SSB transmissions in multiple contiguous RB sets**                |
|                                                                       |
| It is optional for UE to support S-SSB transmissions in multiple      |
| contiguous RB sets.                                                   |
|                                                                       |
| A UE supporting this feature shall at least indicate support of       |
| *sl-DynamicMultiChannelAccess-r18* or support transmitting            |
| PSFCH/S-SSB on a subset of the intended number of RB sets based on    |
| the outcome of channel access on individual RB sets.                  |
+-----------------------------------------------------------------------+
| **S-SSB transmissions in multiple non-contiguous RB sets**            |
|                                                                       |
| It is optional for UE to support S-SSB transmissions in multiple      |
| non-contiguous RB sets.                                               |
|                                                                       |
| A UE supporting this feature shall also support S-SSB transmissions   |
| in multiple contiguous RB sets.                                       |
+-----------------------------------------------------------------------+
| **Short-term time-scale TDM for in-device coexistence**               |
|                                                                       |
| It is optional for UE to support prioritization between LTE sidelink  |
| transmission/reception and NR sidelink transmission/reception.        |
|                                                                       |
| This feature is only applicable if the UE supports at least one of    |
| *sl-Reception-r16*, *sl-TransmissionMode1-r16* and                    |
| *sl-TransmissionMode2-r16*, and if the UE supports V2X sidelink       |
| communication in the band combination.                                |
+-----------------------------------------------------------------------+
| **SL multi-channel access allowing PSFCH/S-SSB transmission**         |
|                                                                       |
| It is optional for UE to support Type A and Type B multi-channel      |
| access procedures for PSFCH/S-SSB transmissions transmissions on a    |
| subset of intended number of RB sets based on the outcome of channel  |
| access on individual RB sets in a slot.                               |
|                                                                       |
| A UE supporting this feature shall also indicate support of           |
| *sl-DynamicMultiChannelAccess-r18*.                                   |
+-----------------------------------------------------------------------+
| **Transmitting PSCCH/PSSCH from 2^nd^ starting symbol in a slot**     |
|                                                                       |
| It is optional for UE to support transmitting PSCCH/PSSCH from 2^nd^  |
| starting symbol in a slot in addition to the first starting symbol    |
| for a band where shared spectrum channel access is used.              |
|                                                                       |
| A UE supporting this feature shall also indicate support of           |
| *sl-DynamicChannelAccess-r18*, at least one of                        |
| *sl-CrossCarrierScheduling-*r16, *sl-TransmissionMode2-r16*,          |
| *sl-TransmissionMode2-RandomResourceSelection-r17*, and               |
| *sl-TransmissionMode2-PartialSensing-r17*.                            |
+-----------------------------------------------------------------------+
| **Transmitting SSB repetitions within one RB set**                    |
|                                                                       |
| It is optional for UE to support transmitting S-PSS/S-SSS/PSBCH       |
| multiple times by repetition in frequency domain within one RB set.   |
|                                                                       |
| The UE supports NR sidelink in shared spectrum where PSD and/or OCB   |
| requirements are defined by regulation must support this feature.     |
|                                                                       |
| A UE supporting this feature shall also indicate support of           |
| *channelBWs-DL-SCS-960kHz-FR2-2-r17* and                              |
| *channelBWs-UL-SCS-960kHz-FR2-2-r17*.                                 |
+-----------------------------------------------------------------------+
| **Transmitting S-SSB on additional S-SSB occasion(s)**                |
|                                                                       |
| It is optional for UE to support transmitting S-SSB on additional     |
| S-SSB occasion(s) per band.                                           |
|                                                                       |
| A UE supporting this feature shall also indicate support of           |
| *channelBWs-DL-SCS-960kHz-FR2-2-r17* and                              |
| *channelBWs-UL-SCS-960kHz-FR2-2-r17*.                                 |
+=======================================================================+