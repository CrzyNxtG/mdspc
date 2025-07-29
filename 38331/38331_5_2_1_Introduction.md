### 5.2.1 Introduction

System Information (SI) is divided into the *MIB* and a number of SIBs
and posSIBs where:

\- the *MIB* is always transmitted on the BCH with a periodicity of 80
ms and repetitions made within 80 ms (TS 38.212 \[17\], clause 7.1) and
it includes parameters that are needed to acquire *SIB1* from the cell.
The first transmission of the *MIB* is scheduled in subframes as defined
in TS 38.213 \[13\], clause 4.1 and repetitions are scheduled according
to the period of SSB;

NOTE 1: If the period of SSB is larger than 80 ms, the MIB is
transmitted with the same periodicity as that of SSB.

\- the *SIB1* is transmitted on the DL-SCH with a periodicity of 160 ms
and variable transmission repetition periodicity within 160 ms as
specified in TS 38.213 \[13\], clause 13. The default transmission
repetition periodicity of *SIB1* is 20 ms but the actual transmission
repetition periodicity is up to network implementation. For SSB and
CORESET multiplexing pattern 1, *SIB1* repetition transmission period is
20 ms. For SSB and CORESET multiplexing pattern 2/3, *SIB1* transmission
repetition period is the same as the SSB period (TS 38.213 \[13\],
clause 13). *SIB1* includes information regarding the availability and
scheduling (e.g. mapping of SIBs to SI message, periodicity, SI-window
size) of other SIBs with an indication whether one or more SIBs are only
provided on-demand and, in that case, the configuration needed by the UE
to perform the SI request. *SIB1* is cell-specific SIB;

\- SIBs other than *SIB1* and posSIBs are carried in *SystemInformation*
(SI) messages, which are transmitted on the DL-SCH. Only SIBs or posSIBs
having the same periodicity can be mapped to the same SI message. SIBs
and posSIBs are mapped to different SI messages, i.e. an SI message
contains either only SIBs or only posSIBs. Each SI message is
transmitted within periodically occurring time domain windows (referred
to as SI-windows with same length for all SI messages). Each SI message
is associated with an SI-window and the SI-windows of different SI
messages do not overlap. That is, within one SI-window only the
corresponding SI message is transmitted. An SI message may be repeated
with the same content a number of times within the SI-window. Any SIB or
posSIB except *SIB1* can be configured to be cell specific or area
specific, using an indication in *SIB1*. The cell specific SIB is
applicable only within a cell that provides the SIB while the area
specific SIB is applicable within an area referred to as SI area, which
consists of one or several cells and is identified by
s*ystemInformationAreaID*;

\- The mapping of SIBs to SI messages is configured in
*schedulingInfoList* and *schedulingInfoList2*, while the mapping of
posSIBs to SI messages is configured in *posSchedulingInfoList* and
*schedulingInfoList2.\*
Each SIB and each posSIB is mapped to a single SI message. posSIBs of
the same *posSibType* carrying GNSS Generic Assistance Data for
different GNSS/SBAS (identified by *gnss-id/sbas-id*, see TS 37.355
\[49\]) are mapped to different SI messages.\
Each SIB and posSIB is contained at most once in an SI message.\
For SIBs and posSIBs with segments, the segments contained in SI
messages are transmitted according to the SI message periodicity, with
one segment of a particular *sibType*/*posSibType* in each SI message;

\- For a UE in RRC_CONNECTED, the network can provide system information
through dedicated signalling using the *RRCReconfiguration* message,
e.g. if the UE has an active BWP with no common search space configured
to monitor system information, paging, or upon request from the UE.

\- For PSCell and SCells, the network provides the required SI by
dedicated signalling, i.e. within an *RRCReconfiguration* message.
Nevertheless, the UE shall acquire *MIB* of the PSCell to get SFN timing
of the SCG (which may be different from MCG). Upon change of relevant SI
for SCell, the network releases and adds the concerned SCell. For
PSCell, the required SI can only be changed with Reconfiguration with
Sync.

NOTE 2: The physical layer imposes a limit to the maximum size a SIB can
take. The maximum *SIB1* or *SI message* size is 2976 bits.