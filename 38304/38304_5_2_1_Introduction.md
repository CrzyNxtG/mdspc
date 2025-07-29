### 5.2.1 Introduction

UE shall perform measurements for cell selection and reselection
purposes as specified in TS 38.133 \[8\].

When evaluating Srxlev and Squal of non-serving cells for reselection
evaluation purposes, the UE shall use parameters provided by the serving
cell and for the final check on cell selection criterion, the UE shall
use parameters provided by the target cell for cell reselection.

The NAS can control the RAT(s) in which the cell selection should be
performed, for instance by indicating RAT(s) associated with the
selected PLMN, and by maintaining a list of forbidden registration
area(s) and a list of equivalent PLMNs. The UE shall select a suitable
cell based on RRC_IDLE or RRC_INACTIVE state measurements and cell
selection criteria.

In order to expedite the cell selection process, stored information for
several RATs, if available, may be used by the UE.

When camped on a cell, the UE shall regularly search for a better cell
according to the cell reselection criteria. If a better cell is found,
that cell is selected. The change of cell may imply a change of RAT.
Details on performance requirements for cell reselection can be found in
TS 38.133 \[8\].

For NCRs, if the NCR-MT in RRC_INACTIVE (re)selects a cell other than
the last serving cell on which side control configuration was received,
then the NCR-MT shall indicate to NCR-Fwd to cease forwarding. If the
NCR-MT in RRC_INACTIVE detects no suitable cell, then the NCR-MT shall
indicate to NCR-Fwd to cease forwarding.

The NAS is informed if the cell selection and reselection result in
changes in the received system information relevant for NAS.

For normal service, the UE shall camp on a suitable cell, monitor
control channel(s) of that cell so that the UE can:

\- receive system information from the PLMN or SNPN; and

\- receive registration area information from the PLMN or SNPN, e.g.,
tracking area information; and

\- receive other AS and NAS Information; and

\- if registered:

\- receive paging and notification messages from the PLMN or SNPN; and

\- initiate transfer to Connected mode.

For cell selection in multi-beam operations, measurement quantity of a
cell is up to UE implementation.

For cell reselection in multi-beam operations, including inter-RAT
reselection from E-UTRA to NR, the measurement quantity of this cell is
derived amongst the beams corresponding to the same cell based on
SS/PBCH block as follows:

> \- if *nrofSS-BlocksToAverage* (*maxRS-IndexCellQual* in E-UTRA) is
> not configured in *SIB2/SIB4* (*SIB24* in E-UTRA); or
>
> \- if *absThreshSS-BlocksConsolidation* (*threshRS-Index* in E-UTRA)
> is not configured in *SIB2/SIB4* (*SIB24* in E-UTRA); or

\- if the highest beam measurement quantity value is below or equal to
*absThreshSS-BlocksConsolidation* (*threshRS-Index* in E-UTRA):

\- derive a cell measurement quantity as the highest beam measurement
quantity value, where each beam measurement quantity is described in TS
38.215 \[11\].

\- else:

\- derive a cell measurement quantity as the linear average of the power
values of up to *nrofSS-BlocksToAverage* (*maxRS-IndexCellQual* in
E-UTRA) of highest beam measurement quantity values above
*absThreshSS-BlocksConsolidation* (*threshRS-Index* in E-UTRA).

NOTE: If both suitable cell(s) and suitable L2 U2N Relay UE(s) (as
specified in TS 38.331 \[3\]) are available, it is up to L2 U2N Remote
UE\'s implementation to select either a suitable cell or a suitable L2
U2N Relay UE.