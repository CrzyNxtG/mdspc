## 7.1 Discontinuous Reception for paging

The UE may use Discontinuous Reception (DRX) in RRC_IDLE and
RRC_INACTIVE state in order to reduce power consumption. The UE monitors
one paging occasion (PO) per DRX cycle. A PO is a set of PDCCH
monitoring occasions and can consist of multiple time slots (e.g.
subframe or OFDM symbol) where paging DCI can be sent (TS 38.213 \[4\]).
One Paging Frame (PF) is one Radio Frame and may contain one or multiple
PO(s) or starting point of a PO. A L2 U2N Relay UE monitors the paging
occasions of its PC5-RRC connected L2 U2N Remote UEs. In this case, the
DRX cycle and UE ID mentioned in this clause refer to those of the L2
U2N Remote UE.

In multi-beam operations, the UE assumes that the same paging message
and the same Short Message are repeated in all transmitted beams and
thus the selection of the beam(s) for the reception of the paging
message and Short Message is up to UE implementation. The paging message
is same for both RAN initiated paging and CN initiated paging.

The UE initiates RRC Connection Resume procedure upon receiving RAN
initiated paging. If the UE receives a CN initiated paging in
RRC_INACTIVE state, the UE moves to RRC_IDLE and informs NAS. However,
if a L2 U2N Relay UE in RRC_INACTIVE state receives a CN initiated
paging for a L2 U2N Remote UE, the L2 U2N Relay UE does not move to
RRC_IDLE state.

NOTE 0a: The L2 U2N Remote UE does not need to monitor the PO in order
to receive the paging message.

NOTE 0b: While the SDT procedure is ongoing in RRC_INACTIVE state, the
UE monitors the PO in order to receive only the Short Message as
specified in TS 38.331 \[3\].

The PF and PO for paging are determined by the following formulae:

SFN for the PF is determined by:

(SFN + PF_offset) mod T = (T div N)\*(UE_ID mod N)

Index (i_s), indicating the index of the PO is determined by:

i_s = floor (UE_ID/N) mod Ns

The PDCCH monitoring occasions for paging are determined according to
*pagingSearchSpace* as specified in TS 38.213 \[4\] and
*firstPDCCH-MonitoringOccasionOfPO* and
*nrofPDCCH-MonitoringOccasionPerSSB-InPO* if configured as specified in
TS 38.331 \[3\]. When *SearchSpaceId* = 0 is configured for
*pagingSearchSpace*, the PDCCH monitoring occasions for paging are same
as for RMSI as defined in clause 13 in TS 38.213 \[4\].

When *SearchSpaceId* = 0 is configured for *pagingSearchSpace*, Ns is
either 1 or 2. For Ns = 1, there is only one PO which starts from the
first PDCCH monitoring occasion for paging in the PF. For Ns = 2, PO is
either in the first half frame (i_s = 0) or the second half frame (i_s
= 1) of the PF.

When *SearchSpaceId* other than 0 is configured for *pagingSearchSpace,*
the UE monitors the (i_s + 1)^th^ PO. A PO is a set of \'S\*X \'
consecutive PDCCH monitoring occasions where \'S\' is the number of
actual transmitted SSBs determined according to *ssb-PositionsInBurst*
in *SIB1* and X is the *nrofPDCCH-MonitoringOccasionPerSSB-InPO* if
configured or is equal to 1 otherwise. The \[x\*S+K\]^th^ PDCCH
monitoring occasion for paging in the PO corresponds to the K^th^
transmitted SSB, where x=0,1,...,X-1, K=1,2,...,S. The PDCCH monitoring
occasions for paging which do not overlap with UL symbols (determined
according to *tdd-UL-DL-ConfigurationCommon*) are sequentially numbered
from zero starting from the first PDCCH monitoring occasion for paging
in the PF. When *firstPDCCH-MonitoringOccasionOfPO* is present, the
starting PDCCH monitoring occasion number of (i_s + 1)^th^ PO is the
(i_s + 1)^th^ value of the *firstPDCCH-MonitoringOccasionOfPO*
parameter; otherwise, it is equal to i_s \* S\*X. If X \> 1, when the UE
detects a PDCCH transmission addressed to P-RNTI within its PO, the UE
is not required to monitor the subsequent PDCCH monitoring occasions for
this PO.

NOTE 1: A PO associated with a PF may start in the PF or after the PF.

NOTE 2: The PDCCH monitoring occasions for a PO can span multiple radio
frames. When *SearchSpaceId* other than 0 is configured for
*paging-SearchSpace* the PDCCH monitoring occasions for a PO can span
multiple periods of the paging search space.

The following parameters are used for the calculation of PF and i_s
above:

T: DRX cycle of the UE.

If the UE does not operate in eDRX as defined in clause 7.4:

\- T is determined by the shortest of the UE specific DRX value
configured by RRC (if any), the UE specific DRX value configured by
upper layers (if any), and a default DRX value broadcast in system
information. For L2 U2N Relay UE, T for a L2 U2N Remote UE is determined
by the shortest of the UE specific DRX value provided in PC5-RRC
signalling and a default DRX value broadcast in system information.

In RRC_IDLE state, if the UE operates in eDRX and eDRX is configured by
upper layers, i.e., T~eDRX,\ CN~, according to clause 7.4:

\- If T~eDRX,\ CN~ is no longer than 1024 radio frames:

\- T = T~eDRX,\ CN~;

\- else:

\- During CN configured PTW, T is determined by the shortest of UE
specific DRX value, if configured by upper layers, and the default DRX
value broadcast in system information.

In RRC_INACTIVE state, if the UE operates in eDRX and eDRX is configured
by RRC, i.e., T~eDRX,\ RAN~ (if any), and upper layers, i.e.,
T~eDRX,\ CN~, as defined in clause 7.4:

\- If both T~eDRX,\ CN~ and used T~eDRX,\ RAN~ are no longer than 1024
radio frames:

\- T = min{T~eDRX,\ RAN~, T~eDRX,\ CN~}.

\- If T~eDRX,\ CN~ is no longer than 1024 radio frames and no
T~eDRX,\ RAN~ is configured or used:

\- T is determined by the shortest of UE specific DRX value configured
by RRC and T~eDRX,\ CN~.

\- If T~eDRX,\ CN~ is longer than 1024 radio frames:

\- If T~eDRX,\ RAN~ is not configured or used:

\- During CN configured PTW, T is determined by the shortest of the UE
specific DRX value configured by RRC, the UE specific DRX value
configured by upper layers (if any), and a default DRX value broadcast
in system information. Outside the CN configured PTW, T is determined by
the UE specific DRX value configured by RRC;

\- else if used T~eDRX,\ RAN~ is no longer than 1024 radio frames:

\- During CN configured PTW, T is determined by the shortest of the UE
specific DRX value, if configured by upper layers and T~eDRX,\ RAN~, and
a default DRX value broadcast in system information. Outside the CN
configured PTW, T is determined by T~eDRX,\ RAN;~

\- else if used T~eDRX,\ RAN~ is longer than 1024 radio frames:

\- During the overlapped part of CN configured PTW and RAN configured
PTW, T is determined by the shortest of the UE specific DRX value
configured by RRC, the UE specific DRX value configured by upper layers
(if any), and a default DRX value broadcast in system information;

\- During CN configured PTW and outside RAN configured PTW, T is
determined by the shortest of the UE specific DRX value configured by
upper layers (if any), and a default DRX value broadcast in system
information;

\- Outside CN configured PTW and during RAN configured PTW, T is
determined by the UE specific DRX value configured by RRC.

N: number of total paging frames in T

Ns: number of paging occasions for a PF

PF_offset: offset used for PF determination

UE_ID:

If the UE operates in eDRX as specified in clause 7.4:

\- 5G-S-TMSI mod 4096

else:

\- 5G-S-TMSI mod 1024

Parameters *Ns*, *nAndPagingFrameOffset*,
*nrofPDCCH-MonitoringOccasionPerSSB-InPO*, and the length of default DRX
Cycle are signaled in *SIB1*. The values of N and PF_offset are derived
from the parameter *nAndPagingFrameOffset* as defined in TS 38.331
\[3\]. The parameter *firstPDCCH-MonitoringOccasionOfPO* is signalled in
*SIB1* for paging in the BWP configured by *initialDownlinkBWP*. For
paging in a DL BWP other than the BWP configured by
*initialDownlinkBWP*, the parameter *first-PDCCH-MonitoringOccasionOfPO*
is signaled in the corresponding BWP configuration.

If the UE has no 5G-S-TMSI, for instance when the UE has not yet
registered onto the network, the UE shall use as default identity UE_ID
= 0 in the PF and i_s formulas above.

5G-S-TMSI is a 48 bit long bit string as defined in TS 23.501 \[10\].
5G-S-TMSI shall in the formulae above be interpreted as a binary number
where the left most bit represents the most significant bit.

In RRC_INACTIVE state, if the UE supports
*inactiveStatePO-Determination* and the network broadcasts
*ranPagingInIdlePO* with value \"true\", the UE shall use the same i_s
as for RRC_IDLE state. Otherwise, the UE determines the i_s based on the
parameters and formula above.

In RRC_INACTIVE state, if used eDRX value configured by upper layers is
no longer than 1024 radio frames, the UE shall use the same i_s as for
RRC_IDLE state.

In RRC_INACTIVE state, if used eDRX value configured by upper layers is
longer than 1024 radio frames, during CN PTW, the UE shall use the same
i_s as for RRC_IDLE state. Outside CN PTW, the UE shall use the i_s for
RRC_INACTIVE state.