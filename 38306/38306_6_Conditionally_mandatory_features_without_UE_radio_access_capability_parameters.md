# 6 Conditionally mandatory features without UE radio access capability parameters

+--------------------------------+---------------------------------------------+
| Features                       | Condition                                   |
+--------------------------------+---------------------------------------------+
| Acquisition of positioning SI  | It is mandatory to support acquisition of   |
| messages with 80 milliseconds  | positioning SI messages with 80             |
| offset position compared to SI | milliseconds offset position compared to SI |
| messages in                    | messages in *schedulingInfoList* for UEs    |
| *schedulingInfoList*           | which support the acquisition of the posSIB |
|                                | types in *posSchedulingInfoList* as         |
|                                | specified in TS 38.331 \[9\].               |
+================================+=============================================+
| Acquisition of SI messages     | It is mandatory to support acquisition of   |
| with explicit SI window        | SI messages with explicit SI window         |
| positions                      | positions for UEs which support the SIB     |
|                                | types in *schedulingInfoList2* as specified |
|                                | in TS 38.331 \[9\].                         |
+--------------------------------+---------------------------------------------+
| AS layer memory size for QoE   | It is mandatory to support the minimum AS   |
| paused measurement reports     | layer memory size of 64KB for QoE paused    |
|                                | measurement reports for UEs which support   |
|                                | *qoe-Streaming-MeasReport-r17*,             |
|                                | *qoe-MTSI-MeasReport-r17* or                |
|                                | *qoe-VR-MeasReport-r17*.                    |
+--------------------------------+---------------------------------------------+
| AS layer memory size for QoE   | It is mandatory to support the minimum AS   |
| measurement reports in         | layer memory size of 64KB for QoE           |
| RRC_IDLE and RRC_INACTIVE      | measurement reports stored in               |
|                                | RRC_IDLE/RRC_INACTIVE for UEs which support |
|                                | *qoe-IdleInactiveMeasReport-r18* and any of |
|                                | *qoe-Streaming-MeasReport-r17* or           |
|                                | *qoe-MTSI-MeasReport-r17* or                |
|                                | *qoe-VR-MeasReport-r17*. This memory size   |
|                                | is additional to \"AS layer memory size for |
|                                | QoE paused measurement reports\"            |
+--------------------------------+---------------------------------------------+
| ATG specific P-max             | It is mandatory to support the ATG specific |
|                                | P-max configured by network for UEs         |
|                                | supporting *airToGroundNetwork-r18*.        |
+--------------------------------+---------------------------------------------+
| Downlink SDAP header           | Either NAS reflective QoS or                |
|                                | *as-ReflectiveQoS* is supported.            |
+--------------------------------+---------------------------------------------+
| Extended values for            | It is mandatory for UEs which support FR2-2 |
| *drx-HARQ-RTT-TimerDL/UL*      | bands with SCS 480kHz and/or 960kHz.        |
+--------------------------------+---------------------------------------------+
| IMS emergency call             | It is mandatory to support IMS emergency    |
|                                | call over PLMN for UEs which are IMS voice  |
|                                | capable in NR.                              |
|                                |                                             |
|                                | It is mandatory to support IMS emergency    |
|                                | call over SNPN for UEs that are SNPN        |
|                                | capable and IMS voice capable over SNPNs.   |
+--------------------------------+---------------------------------------------+
| Logged measurements suspension | It is mandatory to support Logged           |
| due to IDC interference        | measurements suspension due to IDC          |
|                                | interference for UEs which are supporting   |
|                                | logged measurements in RRC_IDLE and         |
|                                | RRC_INACTIVE upon request from the network  |
|                                | and in-device coexistence indication as     |
|                                | specified in TS 38.331 \[9\].               |
+--------------------------------+---------------------------------------------+
| MAC subheaders with LX field   | It is mandatory to support MAC subheaders   |
|                                | with LX field for UEs supporting MAC SDU(s) |
|                                | using the LCID value(s) as specified in     |
|                                | Table 6.2.1-2c in TS 38.321 \[8\].          |
+--------------------------------+---------------------------------------------+
| MAC subheaders with one-octet  | It is mandatory to support MAC subheaders   |
| eLCID field                    | with one-octet eLCID field for              |
|                                | UEs/IAB-MTs/NCR-MTs supporting MAC CEs      |
|                                | using extended LCID values as specified in  |
|                                | TS 38.321 \[8\].                            |
+--------------------------------+---------------------------------------------+
| Paging cause in RAN paging     | It is mandatory for a UE to support paging  |
| message                        | cause in RAN paging if UE supports paging   |
|                                | cause in CN paging.                         |
+--------------------------------+---------------------------------------------+
| Receiving PSCCH/PSSCH from     | It is mandatory for a UE supporting NR      |
| 2^nd^ starting symbol in a     | sidelink in shared spectrum and when shared |
| slot                           | spectrum channel access must be used to     |
|                                | support receiving PSCCH/PSSCH transmitted   |
|                                | from 2nd starting symbol in a slot in       |
|                                | addition to the first starting symbol and   |
|                                | monitor a total up to the number reported   |
|                                | in *pscch-RxSidelink-r16* of PSCCHs in a    |
|                                | slot in the 1st and 2nd starting symbols.   |
|                                |                                             |
|                                | A UE supporting this feature shall indicate |
|                                | support of *sl-Reception-r16*.              |
+--------------------------------+---------------------------------------------+
| Receiving UE to UE COT sharing | It is mandatory for a UE supporting NR SL   |
| information                    | in shared spectrum where shared spectrum    |
|                                | channel access must be used to support      |
|                                | monitoring SCI to read COT sharing          |
|                                | information and transmitting NR SL based on |
|                                | COT sharing information subject to COT      |
|                                | sharing conditions.                         |
|                                |                                             |
|                                | A UE supporting this feature shall indicate |
|                                | support of *sl-DynamicChannelAccess-r18*.   |
+--------------------------------+---------------------------------------------+
| SON report in PNI-NPN          | It is mandatory for a UE to support a SON   |
|                                | report in PNI-NPN if UE supports PNI-NPN    |
|                                | and supports the SON report in PLMN.        |
+--------------------------------+---------------------------------------------+
| Skipping UL configured grant   | Either configuredUL-GrantType1 or           |
| if no data to transmit, as     | *configuredUL-GrantType1-v1650* or          |
| specified in release-15        | configuredUL-GrantType2 or                  |
| version of TS 38.321 \[8\].    | *configuredUL-GrantType2-v1650* is          |
|                                | supported.                                  |
+--------------------------------+---------------------------------------------+
| TA reporting during initial    | It is mandatory to support TA reporting     |
| access                         | during initial access for UEs supporting    |
|                                | *uplink-TA-Reporting-r17* or                |
|                                | *uplinkTA-ReportingATG-r18* as specified in |
|                                | TS 38.321 \[8\].                            |
+--------------------------------+---------------------------------------------+
| Inter-frequency configuration  | It is mandatory to support configuration of |
| for less than 5MHz in SIB4     | *dl-CarrierFreq-r18* and                    |
|                                | *frequencyBandList-r18* as specified in TS  |
|                                | 38.331 \[9\] for UEs supporting             |
|                                | *support5MHz-ChannelBW-20PRB-CORESET0-r18*, |
|                                | *support3MHz-ChannelBW-Symmetric-r18* or    |
|                                | *support3MHz-ChannelBW-Asymmetric-r18*.     |
+--------------------------------+---------------------------------------------+