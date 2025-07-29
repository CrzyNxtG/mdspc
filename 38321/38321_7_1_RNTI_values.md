## 7.1 RNTI values

RNTI values are presented in Table 7.1-1.

Table 7.1-1: RNTI values.

  -----------------------------------------------------------------------
  Value (hexa-decimal)   RNTI
  ---------------------- ------------------------------------------------
  0000                   N/A

  0001--FFF2             RA-RNTI, MSGB-RNTI, Temporary C-RNTI, C-RNTI,
                         CI-RNTI, MCS-C-RNTI, CS-RNTI, TPC-PUCCH-RNTI,
                         TPC-PUSCH-RNTI, TPC-SRS-RNTI, INT-RNTI,
                         SFI-RNTI, SP-CSI-RNTI, PS-RNTI, SL-RNTI,
                         SL-CS-RNTI, SL-PRS-RNTI, SL-PRS-CS-RNTI, SL
                         Semi-Persistent Scheduling V-RNTI, AI-RNTI,
                         G-RNTI, G-CS-RNTI, CG-SDT-CS-RNTI, NCR-RNTI, and
                         cellDTRX-RNTI

  FFF3--FFFA             Reserved

  FFFB                   Multicast MCCH-RNTI

  FFFC                   PEI-RNTI

  FFFD                   MCCH-RNTI

  FFFE                   P-RNTI

  FFFF                   SI-RNTI
  -----------------------------------------------------------------------

Table 7.1-2: RNTI usage.

+--------------------+---------------------------+--------------------+--------------------+
| RNTI               | Usage                     | Transport Channel  | Logical Channel    |
+====================+===========================+====================+====================+
| P-RNTI             | Paging and System         | PCH                | PCCH               |
|                    | Information change        |                    |                    |
|                    | notification              |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| SI-RNTI            | Broadcast of System       | DL-SCH             | BCCH               |
|                    | Information               |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| RA-RNTI            | Random Access Response    | DL-SCH             | N/A                |
+--------------------+---------------------------+--------------------+--------------------+
| MSGB-RNTI          | Random Access Response    | DL-SCH             | CCCH, DCCH, DTCH   |
|                    | for 2-step RA type        |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| Temporary C-RNTI   | Contention Resolution\    | DL-SCH             | CCCH, DCCH, DTCH   |
|                    | (when no valid C-RNTI is  |                    |                    |
|                    | available)                |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| Temporary C-RNTI   | Msg3 transmission         | UL-SCH             | CCCH, DCCH, DTCH   |
+--------------------+---------------------------+--------------------+--------------------+
| C-RNTI, MCS-C-RNTI | Dynamically scheduled     | UL-SCH             | DCCH, DTCH         |
|                    | unicast transmission      |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| C-RNTI             | Dynamically scheduled     | DL-SCH             | CCCH, DCCH, DTCH   |
|                    | unicast transmission      |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| NCR-RNTI           | Transmission of Side      | N/A                | N/A                |
|                    | Control Information for   |                    |                    |
|                    | NCR operation             |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| MCS-C-RNTI         | Dynamically scheduled     | DL-SCH             | DCCH, DTCH         |
|                    | unicast transmission      |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| C-RNTI             | Triggering of PDCCH       | N/A                | N/A                |
|                    | ordered random access     |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| C-RNTI             | Dynamically scheduled PTP | DL-SCH             | MTCH               |
|                    | retransmission for        |                    |                    |
|                    | initial PTM transmission  |                    |                    |
|                    | for multicast MBS.        |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| CG-SDT-CS-RNTI     | Dynamically scheduled     | UL-SCH             | CCCH, DCCH, DTCH   |
|                    | unicast transmission      |                    |                    |
|                    |                           |                    |                    |
|                    | (retransmission)          |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| CS-RNTI            | Configured scheduled      | DL-SCH, UL-SCH     | DCCH, DTCH         |
|                    | unicast transmission\     |                    |                    |
|                    | (activation, reactivation |                    |                    |
|                    | and retransmission)       |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| CS-RNTI            | Configured scheduled      | N/A                | N/A                |
|                    | unicast transmission\     |                    |                    |
|                    | (deactivation)            |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| CS-RNTI            | Configured scheduled      | DL-SCH             | MTCH               |
|                    | unicast transmission\     |                    |                    |
|                    | (PTP retransmission for   |                    |                    |
|                    | initial PTM transmission) |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| CS-RNTI            | Configured scheduled      | N/A                | N/A                |
|                    | unicast transmission\     |                    |                    |
|                    | (MBS SPS deactivation)    |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| G-CS-RNTI          | Configured scheduled      | DL-SCH             | MTCH               |
|                    | multicast transmission\   |                    |                    |
|                    | (activation, reactivation |                    |                    |
|                    | and retransmission)       |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| G-CS-RNTI          | Configured scheduled      | N/A                | N/A                |
|                    | multicast transmission    |                    |                    |
|                    | (deactivation)            |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| TPC-PUCCH-RNTI     | PUCCH power control       | N/A                | N/A                |
+--------------------+---------------------------+--------------------+--------------------+
| TPC-PUSCH-RNTI     | PUSCH power control       | N/A                | N/A                |
+--------------------+---------------------------+--------------------+--------------------+
| TPC-SRS-RNTI       | SRS trigger and power     | N/A                | N/A                |
|                    | control                   |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| INT-RNTI           | Indication pre-emption in | N/A                | N/A                |
|                    | DL                        |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| SFI-RNTI           | Slot Format Indication on | N/A                | N/A                |
|                    | the given cell            |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| SP-CSI-RNTI        | Activation of             | N/A                | N/A                |
|                    | Semi-persistent CSI       |                    |                    |
|                    | reporting on PUSCH        |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| CI-RNTI            | Cancellation indication   | N/A                | N/A                |
|                    | in UL                     |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| PS-RNTI            | DCP to indicate whether   | N/A                | N/A                |
|                    | to start                  |                    |                    |
|                    | *drx-onDurationTimer* for |                    |                    |
|                    | associated DRX cycle      |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| SL-RNTI            | Dynamically scheduled     | SL-SCH             | SCCH, STCH         |
|                    | sidelink transmission     |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| SL-CS-RNTI         | Configured scheduled      | SL-SCH             | SCCH, STCH         |
|                    | sidelink transmission\    |                    |                    |
|                    | (activation, reactivation |                    |                    |
|                    | and retransmission)       |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| SL-CS-RNTI         | Configured scheduled      | N/A                | N/A                |
|                    | sidelink transmission\    |                    |                    |
|                    | (deactivation)            |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| SL-PRS-RNTI        | Dynamically scheduled     | N/A                | N/A                |
|                    | sidelink PRS transmission |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| SL-PRS-CS-RNTI     | Configured scheduled      | N/A                | N/A                |
|                    | sidelink PRS transmission |                    |                    |
|                    | (activation and           |                    |                    |
|                    | reactivation)             |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| SL-PRS-CS-RNTI     | Configured scheduled      | N/A                | N/A                |
|                    | sidelink PRS transmission |                    |                    |
|                    | (deactivation)            |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| SL Semi-Persistent | Semi-Persistently         | SL-SCH             | STCH               |
| Scheduling V-RNTI  | scheduled sidelink        |                    |                    |
| (NOTE 2)           | transmission for V2X      |                    |                    |
|                    | sidelink communication    |                    |                    |
|                    |                           |                    |                    |
|                    | (activation, reactivation |                    |                    |
|                    | and retransmission)       |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| SL Semi-Persistent | Semi-Persistently         | N/A                | N/A                |
| Scheduling V-RNTI  | scheduled sidelink        |                    |                    |
|                    | transmission for V2X      |                    |                    |
| (NOTE 2)           | sidelink communication    |                    |                    |
|                    |                           |                    |                    |
|                    | (deactivation)            |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| AI-RNTI            | Availability indication   | N/A                | N/A                |
|                    | on the given cell         |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| G-RNTI             | Dynamically scheduled MBS | DL-SCH             | MTCH               |
|                    | PTM transmission          |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| MCCH-RNTI          | Dynamically scheduled     | DL-SCH             | MCCH               |
|                    | MCCH signalling and MCCH  |                    |                    |
|                    | change notification for   |                    |                    |
|                    | MBS broadcast             |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| PEI-RNTI           | Paging Early Indication   | N/A                | N/A                |
+--------------------+---------------------------+--------------------+--------------------+
| Multicast          | Dynamically scheduled     | DL-SCH             | MCCH               |
| MCCH-RNTI          | MCCH signalling and MCCH  |                    |                    |
|                    | change notification for   |                    |                    |
|                    | MBS multicast in          |                    |                    |
|                    | RRC_INACTIVE              |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| cellDTRX-RNTI      | Network energy saving     | N/A                | N/A                |
|                    | indication                |                    |                    |
+--------------------+---------------------------+--------------------+--------------------+
| NOTE 1: The usage of MCS-C-RNTI is equivalent to that of C-RNTI in MAC procedures        |
| (except for the C-RNTI MAC CE).                                                          |
|                                                                                          |
| NOTE 2: The MAC entity uses SL Semi-Persistent Scheduling V-RNTI to control              |
| semi-persistently scheduled sidelink transmission on SL-SCH for V2X sidelink             |
| communication as specified in clause 5.14.1.1 of TS 36.321 \[22\].                       |
|                                                                                          |
| NOTE 3: The usage of CG-SDT-CS-RNTI is equivalent to that of CS-RNTI when there is an    |
| CG-SDT procedure ongoing.                                                                |
+------------------------------------------------------------------------------------------+