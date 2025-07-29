#  12 Processing delay requirements for RRC procedures

The UE performance requirements for RRC procedures are specified in the
following tables. The performance requirement is expressed as the time
in \[ms\] from the end of reception of the network -\> UE message on the
UE physical layer up to when the UE shall be ready for the reception of
uplink grant for the UE -\> network response message with no access
delay other than the TTI-alignment (e.g. excluding delays caused by
scheduling, the random access procedure or physical layer
synchronisation). In case the RRC procedure triggers BWP switching, the
RRC procedure delay is the value defined in the following table plus the
BWP switching delay defined in TS 38.133 \[14\], clause 8.6.3.

![](media/image69.emf)

Figure 12.1-1: Illustration of RRC procedure delay

Table 12.1-1: UE performance requirements for RRC procedures for UEs

+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| Procedure title:              | Network -\> UE              | UE -\> Network                             | Value \[ms\]     | Notes                     |
+===============================+=============================+============================================+==================+===========================+
| **RRC Connection Control Procedures**                                                                                                                   |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| RRC reconfiguration           | *RRCReconfiguration*        | *RRCReconfigurationComplete*               | 10               |                           |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| RRC reconfiguration (scell    | *RRCReconfiguration*        | *RRCReconfigurationComplete*               | 16               |                           |
| addition/release)             |                             |                                            |                  |                           |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| RRC reconfiguration (LTE/NR   | *RRCReconfiguration*        | *RRCReconfigurationComplete*               | 16               |                           |
| SCG establishment/            |                             |                                            |                  |                           |
| modification/ release)        |                             |                                            |                  |                           |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| RRC reconfiguration (Intra-NR | *RRCReconfiguration*        | *RRCReconfigurationComplete*               | 16               |                           |
| mobility with LTE/NR SCG      |                             |                                            |                  |                           |
| establishment/ modification/  |                             |                                            |                  |                           |
| release)                      |                             |                                            |                  |                           |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| RRC reconfiguration           | *DLDedicatedMessageSegment* | *RRCReconfigurationComplete*               | 16+( Nseg        | Nseg                      |
|                               |                             |                                            |                  |                           |
|                               |                             |                                            | -1)\*10          | is number of RRC segments |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| RRC setup                     | *RRCSetup*                  | *RRCSetupComplete*                         | 10               |                           |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| RRC Release                   | *RRCRelease*                |                                            | NA               |                           |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| RRC re-establishment          | *RRCReestablishment*        | *RRCReestablishmentComplete*               | 10               |                           |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| RRC resume                    | *RRCResume*                 | *RRCResumeComplete*                        | 6 or 10          | Value=6 applies for a UE  |
|                               |                             |                                            |                  | supporting reduced CP     |
|                               |                             |                                            |                  | latency for the case of   |
|                               |                             |                                            |                  | RRCResume message only    |
|                               |                             |                                            |                  | including MAC and PHY     |
|                               |                             |                                            |                  | configuration,            |
|                               |                             |                                            |                  | reestablishPDCP and       |
|                               |                             |                                            |                  | reestablishRLC for SRB2,  |
|                               |                             |                                            |                  | multicast MRB(s) and      |
|                               |                             |                                            |                  | DRB(s), and no DRX, SPS,  |
|                               |                             |                                            |                  | configured grant, CA or   |
|                               |                             |                                            |                  | MIMO re-configuration     |
|                               |                             |                                            |                  | will be triggered by this |
|                               |                             |                                            |                  | message. Further, the UL  |
|                               |                             |                                            |                  | grant for transmission of |
|                               |                             |                                            |                  | *RRCResumeComplete* and   |
|                               |                             |                                            |                  | the data is transmitted   |
|                               |                             |                                            |                  | over common search space  |
|                               |                             |                                            |                  | with DCI format 0_0.      |
|                               |                             |                                            |                  |                           |
|                               |                             |                                            |                  | In this scenario, the RRC |
|                               |                             |                                            |                  | procedure delay \[ms\]    |
|                               |                             |                                            |                  | can extend beyond the     |
|                               |                             |                                            |                  | reception of the UL       |
|                               |                             |                                            |                  | grant, up to 7 ms.        |
|                               |                             |                                            |                  |                           |
|                               |                             |                                            |                  | For other cases, Value =  |
|                               |                             |                                            |                  | 10 applies.               |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| RRC resume (MCG SCell         | *RRCResume*                 | *RRCResumeComplete*                        | 16               |                           |
| addition/restoration/release) |                             |                                            |                  |                           |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| RRC resume (SCG               | *RRCResume*                 | *RRCResumeComplete*                        | 16               |                           |
| establishment/                |                             |                                            |                  |                           |
| restoration/release)          |                             |                                            |                  |                           |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| RRC resume                    | *DLDedicatedMessageSegment* | *RRCResumeComplete*                        | 16+( Nseg        | Nseg                      |
|                               |                             |                                            |                  |                           |
|                               |                             |                                            | -1)\*10          | is number of RRC segments |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| Initial AS security           | *SecurityModeCommand*       | *SecurityModeComplete/SecurityModeFailure* | 5                |                           |
| activation                    |                             |                                            |                  |                           |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| **Inter RAT mobility**                                                                                                                                  |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| Handover to NR                | *RRCReconfiguration (sent   | *RRCReconfigurationComplete*               | NA               | The performance of this   |
|                               | by other RAT)*              |                                            |                  | procedure is specified in |
|                               |                             |                                            |                  | TS 36.133 \[40\] clauses  |
|                               |                             |                                            |                  | 5.3.4.2, 5.3.4A.2 and     |
|                               |                             |                                            |                  | 5.3.5.2 in case of        |
|                               |                             |                                            |                  | handover from E-UTRA to   |
|                               |                             |                                            |                  | NR.                       |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| Handover from NR              | *MobilityFromNRCommand*     |                                            | NA               | The performance of this   |
|                               |                             |                                            |                  | procedure is specified in |
|                               |                             |                                            |                  | TS 38.133 \[14\], clauses |
|                               |                             |                                            |                  | 6.1.2.1.2 and 6.1.2.2.2.  |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| **Other procedures**                                                                                                                                    |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| UE assistance information     |                             | *UEAssistanceInformation*                  | NA               |                           |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| UE capability transfer        | *UECapabilityEnquiry*       | *UECapabilityInformation*                  | 80               |                           |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| UE capability transfer        | *UECapabilityEnquiry*       | *ULDedicatedMessageSegment*                | 80               | Applicable when UL RRC    |
|                               |                             |                                            |                  | segmentation is enabled   |
|                               |                             |                                            |                  | by the field              |
|                               |                             |                                            |                  | *rrc-SegAllowed*.         |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| UE capability transfer        | *UECapabilityEnquiry*       | *ULDedicatedMessageSegment*                | 560+max (0,      | Applicable when UL RRC    |
|                               |                             |                                            | Nseg-7)\*80      | segmentation is enabled   |
|                               |                             |                                            |                  | by the field              |
|                               |                             |                                            |                  | *rrc-MaxCapaSegAllowed*.  |
|                               |                             |                                            |                  |                           |
|                               |                             |                                            |                  | Nseg is the value         |
|                               |                             |                                            |                  | indicated by              |
|                               |                             |                                            |                  | *rrc-MaxCapaSegAllowed*.  |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| Counter check                 | *CounterCheck*              | *CounterCheckResponse*                     | 5                |                           |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| UE information                | *UEInformationRequest*      | *UEInformationResponse*                    | 15               |                           |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| DL Information transfer MR-DC | *DLInformationTransferMRDC* |                                            | NA               | The UE shall apply the    |
|                               |                             |                                            |                  | performance requirements  |
|                               |                             |                                            |                  | of the RRC message        |
|                               |                             |                                            |                  | included within the       |
|                               |                             |                                            |                  | DLInformationTransferMRDC |
|                               |                             |                                            |                  | message.                  |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| IAB other information         |                             | *IABOtherInformation*                      | NA               |                           |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| Sidelink UE information       |                             | *SidelinkUEInformationNR*                  | NA               |                           |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+
| UE Positioning assistance     |                             | *UEPositioningAssistanceInfo*              | NA               |                           |
| information                   |                             |                                            |                  |                           |
+-------------------------------+-----------------------------+--------------------------------------------+------------------+---------------------------+