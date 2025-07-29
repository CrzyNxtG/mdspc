### 6.2.1 MAC subheader for DL-SCH and UL-SCH

The MAC subheader consists of the following fields:

\- LCID: The Logical Channel ID field identifies the logical channel
instance of the corresponding MAC SDU or the type of the corresponding
MAC CE or padding as described in Tables 6.2.1-1 and 6.2.1-1c for the
DL-SCH and Tables 6.2.1-2 and 6.2.1-2c for the UL-SCH. There is one LCID
field per MAC subheader. The size of the LCID field is 6 bits. If the
LCID field is set to 34 as in Table 6.2.1-1 or 6.2.1-2, one additional
octet is present in the MAC subheader containing the eLCID field and
follow the octet containing LCID field. If the LCID field is set to 33
as in Table 6.2.1-1 or 6.2.1-2, two additional octets are present in the
MAC subheader containing the eLCID field and these two additional octets
follow the octet containing LCID field;

NOTE 1: For MBS broadcast, a logical channel is identified based on
G-RNTI and LCID if the same LCID is allocated for logical channels
corresponding to different G-RNTIs.

\- eLCID: The extended Logical Channel ID field identifies the logical
channel instance of the corresponding MAC SDU or the type of the
corresponding MAC CE as described in tables 6.2.1-1a, 6.2.1-1b, 6.2.1-2a
and 6.2.1-2b for the DL-SCH and UL-SCH respectively. The size of the
eLCID field is either 8 bits or 16 bits.

NOTE 2: The extended Logical Channel ID space using two-octet eLCID and
the relevant MAC subheader format is used, only when configured, on the
NR backhaul links between IAB nodes or between IAB node and IAB Donor,
or for multicast MTCHs.

\- L: The Length field indicates the length of the corresponding MAC SDU
or variable-sized MAC CE in bytes. There is one L field per MAC
subheader except for subheaders corresponding to fixed-sized MAC CEs,
padding, and MAC SDUs containing UL CCCH. The size of the L field is
indicated by the F field;

\- F: The Format field indicates the size of the Length field. There is
one F field per MAC subheader except for subheaders corresponding to
fixed-sized MAC CEs, padding, and MAC SDUs containing UL CCCH. The size
of the F field is 1 bit. The value 0 indicates 8 bits of the Length
field. The value 1 indicates 16 bits of the Length field;

\- LX: The LCID extension field indicates the use of extended LCID
space. The size of the LX field is 1 bit. The LX field set to 1
indicates the use of Table 6.2.1-2c, otherwise R bit is present instead
(i.e. set to 0);

\- R: Reserved bit, set to 0.

The MAC subheader is octet aligned.

Table 6.2.1-1: Values of LCID for DL-SCH

  ------------------------------------------------------------------------
  Codepoint/Index   LCID values
  ----------------- ------------------------------------------------------
  0                 CCCH

  1--32             Identity of the logical channel of DCCH, DTCH and
                    multicast MTCH

  33                Extended logical channel ID field (two-octet eLCID
                    field)

  34                Extended logical channel ID field (one-octet eLCID
                    field)

  35--46            Reserved

  47                Recommended bit rate

  48                SP ZP CSI-RS Resource Set Activation/Deactivation

  49                PUCCH spatial relation Activation/Deactivation

  50                SP SRS Activation/Deactivation

  51                SP CSI reporting on PUCCH Activation/Deactivation

  52                TCI State Indication for UE-specific PDCCH

  53                TCI States Activation/Deactivation for UE-specific
                    PDSCH

  54                Aperiodic CSI Trigger State Subselection

  55                SP CSI-RS/CSI-IM Resource Set Activation/Deactivation

  56                Duplication Activation/Deactivation

  57                SCell Activation/Deactivation (four octets)

  58                SCell Activation/Deactivation (one octet)

  59                Long DRX Command

  60                DRX Command

  61                Timing Advance Command

  62                UE Contention Resolution Identity

  63                Padding
  ------------------------------------------------------------------------

Table 6.2.1-1a: Values of two-octet eLCID for DL-SCH

  ------------------------------------------------------------------------
  Codepoint        Index            LCID values
  ---------------- ---------------- --------------------------------------
  0 to (2^16^ --   320 to (2^16^ +  Identity of the logical channel
  1)               319)             

  ------------------------------------------------------------------------

Table 6.2.1-1b: Values of one-octet eLCID for DL-SCH

  ------------------------------------------------------------------------
  Codepoint        Index            LCID values
  ---------------- ---------------- --------------------------------------
  0 to 215         64 to 279        Reserved

  216              280              Aggregated SP Positioning SRS
                                    Activation/Deactivation

  217              281              Enhanced SP CSI reporting on PUCCH
                                    Activation/Deactivation

  218              282              Cross-RRH TCI State Indication for
                                    UE-specific PDCCH

  219              283              LTM Cell Switch Command

  220              284              Candidate Cell TCI States
                                    Activation/Deactivation

  221              285              PSI-Based SDU Discard
                                    Activation/Deactivation

  222              286              Enhanced Unified TCI states
                                    Activation/Deactivation MAC CE for
                                    Joint TCI States

  223              287              Enhanced Unified TCI states
                                    Activation/Deactivation MAC CE for
                                    Separate TCI States

  224              288              NCR Access Link Beam Indication

  225              289              NCR Downlink Backhaul Link Beam
                                    Indication

  226              290              NCR Uplink Backhaul Link Beam
                                    Indication

  227              291              Serving Cell Set based SRS TCI State
                                    Indication

  228              292              SP/AP SRS TCI State Indication

  229              293              BFD-RS Indication

  230              294              Differential Koffset

  231              295              Enhanced SCell Activation/Deactivation
                                    (one octet C~i~ field)

  232              296              Enhanced SCell Activation/Deactivation
                                    (four octet C~i~ field)

  233              297              Unified TCI States
                                    Activation/Deactivation

  234              298              PUCCH Power Control Set Update for
                                    multiple TRP PUCCH repetition

  235              299              PUCCH spatial relation
                                    Activation/Deactivation for multiple
                                    TRP PUCCH repetition

  236              300              Enhanced TCI States Indication for
                                    UE-specific PDCCH

  237              301              Positioning Measurement Gap
                                    Activation/Deactivation Command

  238              302              PPW Activation/Deactivation Command

  239              303              DL Tx Power Adjustment

  240              304              Timing Case Indication

  241              305              Child IAB-DU Restricted Beam
                                    Indication

  242              306              Case-7 Timing advance offset

  243              307              Provided Guard Symbols for Case-6
                                    timing

  244              308              Provided Guard Symbols for Case-7
                                    timing

  245              309              Serving Cell Set based SRS Spatial
                                    Relation Indication

  246              310              PUSCH Pathloss Reference RS Update

  247              311              SRS Pathloss Reference RS Update

  248              312              Enhanced SP/AP SRS Spatial Relation
                                    Indication

  249              313              Enhanced PUCCH Spatial Relation
                                    Activation/Deactivation

  250              314              Enhanced TCI States
                                    Activation/Deactivation for
                                    UE-specific PDSCH

  251              315              Duplication RLC
                                    Activation/Deactivation

  252              316              Absolute Timing Advance Command

  253              317              SP Positioning SRS
                                    Activation/Deactivation

  254              318              Provided Guard Symbols

  255              319              Timing Delta
  ------------------------------------------------------------------------

Table 6.2.1-1c: Values of LCID for MBS multicast MCCH and MBS broadcast
on DL-SCH

  ------------------------------------------------------------------------
  Codepoint/Index   LCID values
  ----------------- ------------------------------------------------------
  0                 Broadcast MCCH or multicast MCCH

  1--32             Identity of the logical channel of broadcast MTCH

  33--63            Reserved
  ------------------------------------------------------------------------

Table 6.2.1-2: Values of LCID for UL-SCH when the LX field is not
present or is set to 0

+-------------------------------------+-------------------------------------------------------+
| Codepoint/Index                     | LCID values                                           |
+=====================================+=======================================================+
| 0                                   | CCCH of size 64 bits, except for an (e)RedCap UE      |
+-------------------------------------+-------------------------------------------------------+
| 1--32                               | Identity of the logical channel of DCCH and DTCH      |
+-------------------------------------+-------------------------------------------------------+
| 33                                  | Extended logical channel ID field (two-octet eLCID    |
|                                     | field)                                                |
+-------------------------------------+-------------------------------------------------------+
| 34                                  | Extended logical channel ID field (one-octet eLCID    |
|                                     | field)                                                |
+-------------------------------------+-------------------------------------------------------+
| 35                                  | CCCH of size 48 bits for a RedCap UE                  |
+-------------------------------------+-------------------------------------------------------+
| 36                                  | CCCH of size 64 bits for a RedCap UE                  |
+-------------------------------------+-------------------------------------------------------+
| 37--42                              | Reserved                                              |
+-------------------------------------+-------------------------------------------------------+
| 43                                  | Truncated Enhanced BFR (one octet C~i~)               |
+-------------------------------------+-------------------------------------------------------+
| 44                                  | Timing Advance Report                                 |
+-------------------------------------+-------------------------------------------------------+
| 45                                  | Truncated Sidelink BSR                                |
+-------------------------------------+-------------------------------------------------------+
| 46                                  | Sidelink BSR                                          |
+-------------------------------------+-------------------------------------------------------+
| 47                                  | Reserved                                              |
+-------------------------------------+-------------------------------------------------------+
| 48                                  | LBT failure (four octets)                             |
+-------------------------------------+-------------------------------------------------------+
| 49                                  | LBT failure (one octet)                               |
+-------------------------------------+-------------------------------------------------------+
| 50                                  | BFR (one octet C~i~)                                  |
+-------------------------------------+-------------------------------------------------------+
| 51                                  | Truncated BFR (one octet C~i~)                        |
+-------------------------------------+-------------------------------------------------------+
| 52                                  | CCCH of size 48 bits, except for an (e)RedCap UE      |
+-------------------------------------+-------------------------------------------------------+
| 53                                  | Recommended bit rate query                            |
+-------------------------------------+-------------------------------------------------------+
| 54                                  | Multiple Entry PHR (four octets C~i~)                 |
+-------------------------------------+-------------------------------------------------------+
| 55                                  | Configured Grant Confirmation                         |
+-------------------------------------+-------------------------------------------------------+
| 56                                  | Multiple Entry PHR (one octet C~i~)                   |
+-------------------------------------+-------------------------------------------------------+
| 57                                  | Single Entry PHR                                      |
+-------------------------------------+-------------------------------------------------------+
| 58                                  | C-RNTI                                                |
+-------------------------------------+-------------------------------------------------------+
| 59                                  | Short Truncated BSR                                   |
+-------------------------------------+-------------------------------------------------------+
| 60                                  | Long Truncated BSR                                    |
+-------------------------------------+-------------------------------------------------------+
| 61                                  | Short BSR                                             |
+-------------------------------------+-------------------------------------------------------+
| 62                                  | Long BSR                                              |
+-------------------------------------+-------------------------------------------------------+
| 63                                  | Padding                                               |
+-------------------------------------+-------------------------------------------------------+
| NOTE: CCCH of size 48 bits and CCCH of size 64 bits are referred to as CCCH and CCCH1,      |
| respectively, in TS 38.331 \[5\].                                                           |
+---------------------------------------------------------------------------------------------+

Table 6.2.1-2a: Values of two-octet eLCID for UL-SCH

  ------------------------------------------------------------------------
  Codepoint        Index            LCID values
  ---------------- ---------------- --------------------------------------
  0 to (2^16^ --   320 to (2^16^ +  Identity of the logical channel
  1)               319)             

  ------------------------------------------------------------------------

Table 6.2.1-2b: Values of one-octet eLCID for UL-SCH

  ------------------------------------------------------------------------
  Codepoint   Index     LCID values
  ----------- --------- --------------------------------------------------
  0 to 218    64 to 282 Reserved

  219         283       Enhanced Multiple Entry PHR for multiple TRP STx2P
                        (four octets Ci)

  220         284       Enhanced Multiple Entry PHR for multiple TRP STx2P
                        (one octets Ci)

  221         285       Enhanced Single Entry PHR for multiple TRP STx2P

  222         286       SL LBT Failure

  223         287       Multiple Entry PHR with assumed PUSCH (four octets
                        C~i~)

  224         288       Multiple Entry PHR with assumed PUSCH (one octets
                        C~i~)

  225         289       Single Entry PHR with assumed PUSCH

  226         290       SL-PRS Resource Request

  227         291       Refined Long BSR

  228         292       Delay Status Report

  229         293       Enhanced Multiple Entry PHR for multiple TRP (four
                        octets C~i~)

  230         294       Enhanced Multiple Entry PHR for multiple TRP (one
                        octets C~i~)

  231         295       Enhanced Single Entry PHR for multiple TRP

  232         296       Enhanced Multiple Entry PHR (four octets C~i~)

  233         297       Enhanced Multiple Entry PHR (one octets C~i~)

  234         298       Enhanced Single Entry PHR

  235         299       Enhanced BFR (one octet C~i~)

  236         300       Enhanced BFR (four octet C~i~)

  237         301       Truncated Enhanced BFR (four octet C~i~)

  238         302       Positioning Measurement Gap
                        Activation/Deactivation Request

  239         303       IAB-MT Recommended Beam Indication

  240         304       Desired IAB-MT PSD range

  241         305       Desired DL Tx Power Adjustment

  242         306       Case-6 Timing Request

  243         307       Desired Guard Symbols for Case 6 timing

  244         308       Desired Guard Symbols for Case 7 timing

  245         309       Extended Short Truncated BSR

  246         310       Extended Long Truncated BSR

  247         311       Extended Short BSR

  248         312       Extended Long BSR

  249         313       Extended Pre-emptive BSR

  250         314       BFR (four octets C~i~)

  251         315       Truncated BFR (four octets C~i~)

  252         316       Multiple Entry Configured Grant Confirmation

  253         317       Sidelink Configured Grant Confirmation

  254         318       Desired Guard Symbols

  255         319       Pre-emptive BSR
  ------------------------------------------------------------------------

Table 6.2.1-2c: Values of LCID for UL-SCH when the LX field is set to 1

+-------------------------+-------------------------+--------------------------------------------+
| Codepoint               | Index                   | LCID values                                |
+=========================+=========================+============================================+
| 0                       | (2^16^ + 320)           | CCCH of size 48 bits for an eRedCap UE     |
+-------------------------+-------------------------+--------------------------------------------+
| 1                       | (2^16^ + 321)           | CCCH of size 64 bits for an eRedCap UE     |
+-------------------------+-------------------------+--------------------------------------------+
| 2                       | (2^16^ + 322)           | CCCH of size 48 bits for PUCCH repetition  |
|                         |                         | of Msg4 HARQ-ACK, except for an (e)RedCap  |
|                         |                         | UE                                         |
+-------------------------+-------------------------+--------------------------------------------+
| 3                       | (2^16^ + 323)           | CCCH of size 64 bits for PUCCH repetition  |
|                         |                         | of Msg4 HARQ-ACK, except for an (e)RedCap  |
|                         |                         | UE                                         |
+-------------------------+-------------------------+--------------------------------------------+
| 4                       | (2^16^ + 324)           | CCCH of size 48 bits for PUCCH repetition  |
|                         |                         | of Msg4 HARQ-ACK of a RedCap UE            |
+-------------------------+-------------------------+--------------------------------------------+
| 5                       | (2^16^ + 325)           | CCCH of size 64 bits for PUCCH repetition  |
|                         |                         | of Msg4 HARQ-ACK of a RedCap UE            |
+-------------------------+-------------------------+--------------------------------------------+
| 6                       | (2^16^ + 326)           | CCCH of size 48 bits for PUCCH repetition  |
|                         |                         | of Msg4 HARQ-ACK of an eRedCap UE          |
+-------------------------+-------------------------+--------------------------------------------+
| 7                       | (2^16^ + 327)           | CCCH of size 64 bits for PUCCH repetition  |
|                         |                         | of Msg4 HARQ-ACK of an eRedCap UE          |
+-------------------------+-------------------------+--------------------------------------------+
| 8 to 63                 | (2^16^ + 328) to        | Reserved                                   |
|                         | (2^16^ + 383)           |                                            |
+-------------------------+-------------------------+--------------------------------------------+
| NOTE 1: The MAC entity may use the code point corresponding to a given feature or feature      |
| combination in Table 6.2.1-2c only if network indicates support for the corresponding feature  |
| or feature combination.                                                                        |
|                                                                                                |
| NOTE 2: CCCH of size 48 bits and CCCH of size 64 bits are referred to as CCCH and CCCH1,       |
| respectively, in TS 38.331 \[5\].                                                              |
|                                                                                                |
| NOTE 3: For UE capable of PUCCH repetition of Msg4 HARQ-ACK, the MAC entity uses the code      |
| points corresponding to PUCCH repetition of Msg4 HARQ-ACK if                                   |
| *numberOfMsg4HARQ-ACK-Repetitions* is configured and *rsrp-ThresholdMsg4HARQ-ACK* is not       |
| configured, or if both are configured and the RSRP of the downlink pathloss reference is less  |
| than *rsrp-ThresholdMsg4HARQ-ACK.*                                                             |
+------------------------------------------------------------------------------------------------+