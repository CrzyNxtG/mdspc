## 10.4A PDCCH monitoring for early indication of paging

A UE can be provided the following for detection of a DCI format 2_7 in
RRC_IDLE state or in RRC_INACTIVE state \[12, TS 38.331\]

\- a search space set, by *pei-SearchSpace*, to monitor PDCCH for
detection of DCI format 2_7 according to a Type2A-PDCCH CSS set as
described in clause 10.1

\- a number of frames, by *pei-FrameOffset*, from the start of a frame
to the start of a first paging frame of paging frames associated with a
number of PDCCH monitoring occasions for DCI format 2_7 \[17, TS
38.304\]

\- a number of symbols, by *firstPDCCH-MonitoringOccasionOfPEI-O*, from
the start of the frame to the start of the first PDCCH monitoring
occasion for DCI format 2_7

\- a size, by *payloadSizeDCI-2-7*

\- a number of subgroups per paging occasion, $N_{SG}^{PO}$, by
*subgroupsNumPerPO*

\- a number of paging occasions associated with the number of PDCCH
monitoring occasions for DCI format 2_7, $N_{PO}^{PEI}$, by
*po-NumPerPEI*

A paging indication field of DCI format 2_7 includes $N_{PO}^{PEI}$
segments of $K$ bits, where ${K = N}_{SG}^{PO}$. For a subgroup index
$i_{SG}$, $0 \leq i_{SG} < K$, a UE determines a value for the
$\left( i_{PO} \cdot K + i_{SG} \right)$ bit in the paging indication
field, where
$i_{PO} = \left( (UE\_ IDmodN) \cdot N_{S} + i\_ s \right)modN_{PO}^{PEI}$
is a paging occasion index, and $N$, $N_{S}$, $i_{SG}$, and $i\_ s$ are
defined in \[17, TS 38.304\], and $UE\_ ID$ is defined in clause 7.1 of
\[17, TS 38.304\]. When the value is \'1\', the UE monitors a paging
occasion determined according to \[17, TS 38.304\]; otherwise, the UE is
not required to monitor the paging occasion.

If $N_{PO}^{PEI} < N_{S}$, the number of symbols from the start of the
frame to the start of the first PDCCH monitoring occasion for DCI format
2_7 that is associated with paging occasion index $i_{PO}$ is the
$\left( \left\lfloor \frac{i\_ s}{N_{PO}^{PEI}} \right\rfloor_{} + 1 \right)$-th
value from the $\frac{N_{S}}{N_{PO}^{PEI}}$ values provided by
*firstPDCCH-MonitoringOccasionOfPEI-O*.