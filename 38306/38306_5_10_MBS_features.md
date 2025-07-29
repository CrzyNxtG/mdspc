## 5.10 MBS features

+-----------------------------------------------------------------------+
| Definitions for feature                                               |
+-----------------------------------------------------------------------+
| **Broadcast reception**                                               |
|                                                                       |
| It is optional for UE to support broadcast reception as specified in  |
| TS 38.331 \[9\]. A UE that supports the feature shall also support:   |
|                                                                       |
| > \- Group-common PDCCH/PDSCH for broadcast with CRC scrambled by     |
| > MCCH-RNTI;                                                          |
| >                                                                     |
| > \- Group-common PDCCH/PDSCH for broadcast with CRC scrambled by     |
| > G-RNTI(s) for MTCH;                                                 |
| >                                                                     |
| > \- CFR configuration for broadcast;                                 |
| >                                                                     |
| > \- CORESET and common search space for broadcast;                   |
| >                                                                     |
| > \- DCI format 4_0 with CRC scrambled with G-RNTI/MCCH-RNTI for      |
| > broadcast;                                                          |
| >                                                                     |
| > \- Inter-slot TDM between unicast PDSCH and MCCH group-common PDSCH |
| > or MTCH group-common PDSCH, or between MCCH group-common PDSCH and  |
| > MTCH group-common PDSCH, or among unicast PDSCH and MCCH            |
| > group-common PDSCH and MTCH group-common PDSCH in different slots;  |
| >                                                                     |
| > \- MCCH change notification indication via DCI;                     |
| >                                                                     |
| > \- RRC configured slot-level repetition up to 8 for MTCH;           |
| >                                                                     |
| > \- One G-RNTI per UE is supported for broadcast reception;          |
| >                                                                     |
| > \- Support of FDMed MCCH and PBCH;                                  |
| >                                                                     |
| > \- Support of up to 64QAM for FR1/FR2;                              |
|                                                                       |
| \- 4 broadcast MRBs as the minimum number;                            |
|                                                                       |
| \- PDCP 12 bits SN;                                                   |
|                                                                       |
| \- ROHC with profiles 0x0000, 0x0001 and 0x0002;                      |
|                                                                       |
| \- 4 ROHC context sessions;                                           |
|                                                                       |
| \- RLC UM with 6 bits SN;                                             |
|                                                                       |
| \- RLC UM with 12 bits SN;                                            |
|                                                                       |
| \- DRX with long DRX cycle for MBS broadcast as specified in TS       |
| 38.321 \[8\].                                                         |
|                                                                       |
| An (e)RedCap UE supporting Broadcast reception also supports CFR and  |
| MCCH configuration for (e)RedCap UE.                                  |
+=======================================================================+

5.11 Idle/inactive measurement for voice fallback features

+-----------------------------------------------------------------------+
| Definitions for feature                                               |
+-----------------------------------------------------------------------+
| **Idle/Inactive measurement for voice fallback**                      |
|                                                                       |
| It is optional for UE to support the idle/inactive measurement for    |
| EPS fallback in RRC_IDLE/RRC_INACTIVE as specified in TS 38.331       |
| \[9\].                                                                |
+=======================================================================+

5.12 NCR features

+-----------------------------------------------------------------------+
| Definitions for feature                                               |
+-----------------------------------------------------------------------+
| **Basic NCR support**                                                 |
|                                                                       |
| It is optional for UE to support the NCR-MT feature as specified in   |
| TS 38.213 \[11\]. An NCR node for which the NCR-MT includes           |
| *ncr-NodeIndication* in *RRCSetupComplete* as specified in TS 38.331  |
| \[9\] must support these feature components:                          |
|                                                                       |
| > \- Support of fixed beam for C-link/backhaul link                   |
| >                                                                     |
| > \- Support of TDMed UL transmission of C-link and backhaul link     |
| >                                                                     |
| > \- Support of ON-OFF operation for NCR-Fwd based on access link     |
| > beam indication                                                     |
| >                                                                     |
| > \- Support of TDD UL/DL determination for backhaul/access link      |
| > based on TDD UL/DL configuration of C-link                          |
| >                                                                     |
| > \- Support of Tx/Rx timing determination for backhaul/access link   |
| > based on Tx/Rx timing of C-link                                     |
| >                                                                     |
| > \- Support of beam correspondence of the DL/UL of the access link   |
| > at NCR-Fwd                                                          |
| >                                                                     |
| > \- Support periodic beam indication for access link                 |
| >                                                                     |
| > \- Priority flag for periodic indication                            |
| >                                                                     |
| > \- Support of simultaneous and TDMed DL reception of C-link and     |
| > backhaul link                                                       |
+=======================================================================+