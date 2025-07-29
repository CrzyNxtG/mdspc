### 6.3.1a Positioning System information blocks

#### -- *PosSystemInformation-r16-IEs*

\-- ASN1START

\-- TAG-POSSYSTEMINFORMATION-R16-IES-START

PosSystemInformation-r16-IEs ::= SEQUENCE {

posSIB-TypeAndInfo-r16 SEQUENCE (SIZE (1..maxSIB)) OF CHOICE {

posSib1-1-r16 SIBpos-r16,

posSib1-2-r16 SIBpos-r16,

posSib1-3-r16 SIBpos-r16,

posSib1-4-r16 SIBpos-r16,

posSib1-5-r16 SIBpos-r16,

posSib1-6-r16 SIBpos-r16,

posSib1-7-r16 SIBpos-r16,

posSib1-8-r16 SIBpos-r16,

posSib2-1-r16 SIBpos-r16,

posSib2-2-r16 SIBpos-r16,

posSib2-3-r16 SIBpos-r16,

posSib2-4-r16 SIBpos-r16,

posSib2-5-r16 SIBpos-r16,

posSib2-6-r16 SIBpos-r16,

posSib2-7-r16 SIBpos-r16,

posSib2-8-r16 SIBpos-r16,

posSib2-9-r16 SIBpos-r16,

posSib2-10-r16 SIBpos-r16,

posSib2-11-r16 SIBpos-r16,

posSib2-12-r16 SIBpos-r16,

posSib2-13-r16 SIBpos-r16,

posSib2-14-r16 SIBpos-r16,

posSib2-15-r16 SIBpos-r16,

posSib2-16-r16 SIBpos-r16,

posSib2-17-r16 SIBpos-r16,

posSib2-18-r16 SIBpos-r16,

posSib2-19-r16 SIBpos-r16,

posSib2-20-r16 SIBpos-r16,

posSib2-21-r16 SIBpos-r16,

posSib2-22-r16 SIBpos-r16,

posSib2-23-r16 SIBpos-r16,

posSib3-1-r16 SIBpos-r16,

posSib4-1-r16 SIBpos-r16,

posSib5-1-r16 SIBpos-r16,

posSib6-1-r16 SIBpos-r16,

posSib6-2-r16 SIBpos-r16,

posSib6-3-r16 SIBpos-r16,

\... ,

posSib1-9-v1700 SIBpos-r16,

posSib1-10-v1700 SIBpos-r16,

posSib2-24-v1700 SIBpos-r16,

posSib2-25-v1700 SIBpos-r16,

posSib6-4-v1700 SIBpos-r16,

posSib6-5-v1700 SIBpos-r16,

posSib6-6-v1700 SIBpos-r16,

posSib2-17a-v1770 SIBpos-r16,

posSib2-18a-v1770 SIBpos-r16,

posSib2-20a-v1770 SIBpos-r16,

posSib1-11-v1800 SIBpos-r16,

posSib1-12-v1800 SIBpos-r16,

posSib2-26-v1800 SIBpos-r16,

posSib2-27-v1800 SIBpos-r16,

posSib6-7-v1800 SIBpos-r16,

posSib7-1-v1800 SIBpos-r16,

posSib7-2-v1800 SIBpos-r16,

posSib7-3-v1800 SIBpos-r16,

posSib7-4-v1800 SIBpos-r16

},

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- TAG-POSSYSTEMINFORMATION-R16-IES-STOP

\-- ASN1STOP

#### -- *PosSI-SchedulingInfo*

\-- ASN1START

\-- TAG-POSSI-SCHEDULINGINFO-START

PosSI-SchedulingInfo-r16 ::= SEQUENCE {

posSchedulingInfoList-r16 SEQUENCE (SIZE (1..maxSI-Message)) OF
PosSchedulingInfo-r16,

posSI-RequestConfig-r16 SI-RequestConfig OPTIONAL, \-- Cond MSG-1

posSI-RequestConfigSUL-r16 SI-RequestConfig OPTIONAL, \-- Cond SUL-MSG-1

\...,

\[\[

posSI-RequestConfigRedCap-r17 SI-RequestConfig OPTIONAL \-- Cond
REDCAP-MSG-1

\]\],

\[\[

posSI-RequestConfigMSG1-Repetition-r18 SI-RequestConfigRepetition-r18
OPTIONAL, \-- Cond MSG-1

posSI-RequestConfigSUL-MSG1-Repetition-r18
SI-RequestConfigRepetition-r18 OPTIONAL, \-- Cond SUL-MSG-1

posSI-RequestConfigRedCap-MSG1-Repetition-r18
SI-RequestConfigRepetition-r18 OPTIONAL \-- Cond REDCAP-MSG-1

\]\]

}

PosSchedulingInfo-r16 ::= SEQUENCE {

offsetToSI-Used-r16 ENUMERATED {true} OPTIONAL, \-- Need R

posSI-Periodicity-r16 ENUMERATED {rf8, rf16, rf32, rf64, rf128, rf256,
rf512},

posSI-BroadcastStatus-r16 ENUMERATED {broadcasting, notBroadcasting},

posSIB-MappingInfo-r16 PosSIB-MappingInfo-r16,

\...

}

PosSIB-MappingInfo-r16 ::= SEQUENCE (SIZE (1..maxSIB)) OF
PosSIB-Type-r16

PosSIB-Type-r16 ::= SEQUENCE {

encrypted-r16 ENUMERATED { true } OPTIONAL, \-- Need R

gnss-id-r16 GNSS-ID-r16 OPTIONAL, \-- Need R

sbas-id-r16 SBAS-ID-r16 OPTIONAL, \-- Cond GNSS-ID-SBAS

posSibType-r16 ENUMERATED { posSibType1-1, posSibType1-2, posSibType1-3,
posSibType1-4, posSibType1-5, posSibType1-6,

posSibType1-7, posSibType1-8, posSibType2-1, posSibType2-2,
posSibType2-3, posSibType2-4,

posSibType2-5, posSibType2-6, posSibType2-7, posSibType2-8,
posSibType2-9, posSibType2-10,

posSibType2-11, posSibType2-12, posSibType2-13, posSibType2-14,
posSibType2-15,

posSibType2-16, posSibType2-17, posSibType2-18, posSibType2-19,
posSibType2-20,

posSibType2-21, posSibType2-22, posSibType2-23, posSibType3-1,
posSibType4-1,

posSibType5-1,posSibType6-1, posSibType6-2, posSibType6-3,\... },

areaScope-r16 ENUMERATED {true} OPTIONAL \-- Need S

}

GNSS-ID-r16 ::= SEQUENCE {

gnss-id-r16 ENUMERATED{gps, sbas, qzss, galileo, glonass, bds, \...,
navic-v1760},

\...

}

SBAS-ID-r16 ::= SEQUENCE {

sbas-id-r16 ENUMERATED { waas, egnos, msas, gagan, \...},

\...

}

\-- TAG-POSSI-SCHEDULINGINFO-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *PosSI-SchedulingInfo* field descriptions                             |
+=======================================================================+
| ***areaScope***                                                       |
|                                                                       |
| Indicates that a posSIB is area specific. If the field is absent, the |
| posSIB is cell specific.                                              |
+-----------------------------------------------------------------------+
| ***encrypted***                                                       |
|                                                                       |
| The presence of this field indicates that the *pos-sib-type* is       |
| encrypted as specified in TS 37.355 \[49\].                           |
+-----------------------------------------------------------------------+
| ***gnss-id***                                                         |
|                                                                       |
| The presence of this field indicates that the positioning SIB type is |
| for a specific GNSS. Indicates a specific GNSS (see also TS 37.355    |
| \[49\])                                                               |
+-----------------------------------------------------------------------+
| ***posSchedulingInfoList***                                           |
|                                                                       |
| List of scheduling information for SI messages. If                    |
| *si-SchedulingInfo-v1700* is present, the network ensures that the    |
| total number of SI messages in the concatenated list of SI messages   |
| configured by *posSchedulingInfoList* in *posSI-SchedulingInfo* and   |
| SI messages containing type2 SIB configured by *schedulingInfoList2*  |
| in *si-SchedulingInfo-v1700* does not exceed the limit of             |
| *maxSI-Message*.                                                      |
+-----------------------------------------------------------------------+
| ***posSI-BroadcastStatus***                                           |
|                                                                       |
| Indicates if the SI message is being broadcasted or not. Change of    |
| *posSI-BroadcastStat*us should not result in system information       |
| change notifications in Short Message transmitted with P-RNTI over    |
| DCI (see clause 6.5). The value of the indication is valid until the  |
| end of the BCCH modification period when set to *broadcasting*.       |
+-----------------------------------------------------------------------+
| ***posSI-RequestConfig***                                             |
|                                                                       |
| Configuration of Msg1 resources that the UE uses for requesting       |
| SI-messages for which *posSI-BroadcastStatus* or *si-BroadcastStatus* |
| of the type2 SIB configured by *schedulingInfoList2* in               |
| *si-SchedulingInfo-v1700*, if present, is set to *notBroadcasting*.   |
+-----------------------------------------------------------------------+
| ***posSI-RequestConfigMSG1-Repetition***                              |
|                                                                       |
| Configuration of Msg1 repetition resources on NUL that the UE uses    |
| for requesting SI-messages for which posSI-BroadcastStatus or         |
| *si-BroadcastStatus* of the type2 SIB configured by                   |
| *schedulingInfoList2* in *si-SchedulingInfo-v1700*, if present, is    |
| set to *notBroadcasting*. This field is only applicable when Msg1     |
| repetition resources can be used for requesting SI-messages.          |
+-----------------------------------------------------------------------+
| ***posSI-RequestConfigRedCap***                                       |
|                                                                       |
| Configuration of Msg1 resources for *initialUplinkBWP-RedCap* that    |
| the (e)RedCap UE uses for requesting SI-messages for which            |
| *posSI-BroadcastStatus* or *si-BroadcastStatus* of the type2 SIB      |
| configured by *schedulingInfoList2* in *si-SchedulingInfo-v1700*, if  |
| present, is set to *notBroadcasting*.                                 |
+-----------------------------------------------------------------------+
| ***posSI-RequestConfigRedCap-MSG1-Repetition***                       |
|                                                                       |
| Configuration of Msg1 repetition resources for                        |
| *initialUplinkBWP-RedCap* that the (e)RedCap UE uses for requesting   |
| SI-messages for which *posSI-BroadcastStatus* or *si-BroadcastStatus* |
| of the type2 SIB configured by *schedulingInfoList2* in               |
| *si-SchedulingInfo-v1700*, if present, is set to *notBroadcasting*.   |
| This field is only applicable when Msg1 repetition resources can be   |
| used for requesting SI-messages.                                      |
+-----------------------------------------------------------------------+
| ***posSI-RequestConfigSUL***                                          |
|                                                                       |
| Configuration of Msg1 resources that the UE uses for requesting       |
| SI-messages for which *posSI-BroadcastStatus* or *si-BroadcastStatus* |
| of the type2 SIB configured by *schedulingInfoList2* in               |
| *si-SchedulingInfo-v1700*, if present, is set to *notBroadcasting*.   |
+-----------------------------------------------------------------------+
| ***posSI-RequestConfigSUL-MSG1-Repetition***                          |
|                                                                       |
| Configuration of Msg1 repetition resources on SUL that the UE uses    |
| for requesting SI-messages for which *posSI-BroadcastStatus* or       |
| *si-BroadcastStatus* of the type2 SIB configured by                   |
| *schedulingInfoList2* in *si-SchedulingInfo-v1700*, if present, is    |
| set to *notBroadcasting*. This field is only applicable when Msg1     |
| repetition resources can be used for requesting SI-messages.          |
+-----------------------------------------------------------------------+
| ***posSIB-MappingInfo***                                              |
|                                                                       |
| List of the posSIBs mapped to this *SystemInformation* message.       |
+-----------------------------------------------------------------------+
| ***posSibType***                                                      |
|                                                                       |
| The positioning SIB type is defined in TS 37.355 \[49\].              |
+-----------------------------------------------------------------------+
| ***posSI-Periodicity***                                               |
|                                                                       |
| Periodicity of the SI-message in radio frames, such that rf8 denotes  |
| 8 radio frames, rf16 denotes 16 radio frames, and so on. If the       |
| *offsetToSI-Used* is configured, the *posSI-Periodicity* of rf8       |
| cannot be used.                                                       |
+-----------------------------------------------------------------------+
| ***offsetToSI-Used***                                                 |
|                                                                       |
| This field, if present, indicates that all the SI messages in         |
| *posSchedulingInfoList* are scheduled with an offset of 8 radio       |
| frames compared to SI messages in *schedulingInfoList*.               |
| *offsetToSI-Used* may be present only if the shortest configured SI   |
| message periodicity for SI messages in *schedulingInfoList* is 80ms.  |
| If SI offset is used, this field is present in each of the SI         |
| messages in the *posSchedulingInfoList*.                              |
+-----------------------------------------------------------------------+
| ***sbas-id***                                                         |
|                                                                       |
| The presence of this field indicates that the positioning SIB type is |
| for a specific SBAS. Indicates a specific SBAS (see also TS 37.355    |
| \[49\]).                                                              |
+-----------------------------------------------------------------------+

  ----------------------------------------------------------------------------
  Conditional      Explanation
  presence         
  ---------------- -----------------------------------------------------------
  *GNSS-ID-SBAS*   The field is mandatory present if *gnss-id* is set to
                   *sbas*. It is absent otherwise.

  *MSG-1*          The field is optionally present, Need R, if
                   *posSI-BroadcastStatus* is set to *notBroadcasting* for any
                   SI-message included in *posSchedulingInfoList* or if
                   *si-BroadcastStatus* is set to *notBroadcasting* for any
                   SI-message containing type2 SIB included in
                   *schedulingInfoList2*. It is absent otherwise.

  *SUL-MSG-1*      The field is optionally present, Need R, if
                   *supplementaryUplink* is configured in
                   *ServingCellConfigCommonSIB,* and if
                   *posSI-BroadcastStatus* is set to *notBroadcasting* for any
                   SI-message included in *posSchedulingInfoList* or if
                   *si-BroadcastStatus* is set to *notBroadcasting* for any
                   SI-message containing type2 SIB included in
                   *schedulingInfoList2*. It is absent otherwise.

  *REDCAP-MSG-1*   The field is optionally present, Need R, if
                   *initialUplinkBWP-RedCap* is configured in
                   *UplinkConfigCommonSIB,* and if *posSI-BroadcastStatus* is
                   set to *notBroadcasting* for any SI-message included in
                   *posSchedulingInfoList* or if *si-BroadcastStatus* is set
                   to *notBroadcasting* for any SI-message containing type2
                   SIB included in *schedulingInfoList2*. It is absent
                   otherwise.
  ----------------------------------------------------------------------------

#### -- *SIBpos*

The IE *SIBpos* contains positioning assistance data as defined in TS
37.355 \[49\].

*SIBpos* information element

\-- ASN1START

\-- TAG-SIPOS-START

SIBpos-r16 ::= SEQUENCE {

assistanceDataSIB-Element-r16 OCTET STRING,

lateNonCriticalExtension OCTET STRING OPTIONAL,

\...

}

\-- TAG-SIPOS-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SIBpos* field descriptions                                           |
+=======================================================================+
| ***assistanceDataSIB-Element***                                       |
|                                                                       |
| Parameter *AssistanceDataSIBelement* defined in TS 37.355 \[49\]. The |
| first/leftmost bit of the first octet contains the most significant   |
| bit.                                                                  |
+-----------------------------------------------------------------------+