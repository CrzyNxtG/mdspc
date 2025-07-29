### 4.2.13 IMS Parameters

+----------------------------------------------------+-----+----+---------+---------+
| Definitions for parameters                         | Per | M  | FDD-TDD | FR1-FR2 |
|                                                    |     |    |         |         |
|                                                    |     |    | DIFF    | DIFF    |
+----------------------------------------------------+-----+----+---------+---------+
| ***voiceFallbackIndicationEPS-r16***               | UE  | No | No      | No      |
|                                                    |     |    |         |         |
| Indicates whether the UE supports                  |     |    |         |         |
| *voiceFallbackIndication* in *RRCRelease* and      |     |    |         |         |
| *MobilityFromNRCommand*. If this field is          |     |    |         |         |
| included, the UE shall support IMS voice over NR   |     |    |         |         |
| and IMS voice over E-UTRA via EPC.                 |     |    |         |         |
+----------------------------------------------------+-----+----+---------+---------+
| ***voiceOverEUTRA-5GC***                           | UE  | No | No      | No      |
|                                                    |     |    |         |         |
| Indicates whether the UE supports IMS voice over   |     |    |         |         |
| E-UTRA via 5GC. It is mandated to the UE if the UE |     |    |         |         |
| is capable of IMS voice over E-UTRA via 5GC.       |     |    |         |         |
| Otherwise, the UE does not include this field. If  |     |    |         |         |
| this field is included and the UE is capable of    |     |    |         |         |
| E-UTRA with EPC, the UE shall support IMS voice    |     |    |         |         |
| over E-UTRA via EPC.                               |     |    |         |         |
+----------------------------------------------------+-----+----+---------+---------+
| ***voiceOverNR, voiceOverNR-r17***                 | UE  | No | No      | Yes     |
|                                                    |     |    |         |         |
| Indicates whether the UE supports IMS voice over   |     |    |         | (Incl   |
| NR. It is mandated to the UE if the UE is capable  |     |    |         | FR2-2   |
| of IMS voice over NR (including SNPN if the UE is  |     |    |         | DIFF)   |
| SNPN capable). Otherwise, the UE does not include  |     |    |         |         |
| this field. If this field is included and the UE   |     |    |         |         |
| is capable of E-UTRA with EPC, the UE shall        |     |    |         |         |
| support IMS voice over E-UTRA via EPC.             |     |    |         |         |
+----------------------------------------------------+-----+----+---------+---------+
| ***voiceOverSCG-BearerEUTRA-5GC***                 | UE  | No | No      | N/A     |
|                                                    |     |    |         |         |
| Indicates whether the UE supports IMS voice over   |     |    |         |         |
| SCG bearer of NE-DC.                               |     |    |         |         |
+====================================================+=====+====+=========+=========+

NOTE: In this release of specification, IMS voice over split bearer is
not supported for NR-DC, NE-DC, and L2 multi-path relay.