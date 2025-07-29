### 7.2.1 Paging Early Indication reception

The UE may use Paging Early Indication (PEI) in RRC_IDLE and
RRC_INACTIVE states in order to reduce power consumption. If PEI
configuration is provided in system information, the UE in RRC_IDLE or
RRC_INACTIVE state supporting PEI (except for the UEs expecting MBS
group notification) can monitor PEI using PEI parameters in system
information according to the procedure described below.

If *lastUsedCellOnly* is configured in system information of a cell, the
UE monitors PEI in this cell only if the UE most recently received
*RRCRelease* without *noLastCellUpdate* in this cell. Otherwise (i.e.,
if *lastUsedCellOnly* is not configured in system information of a
cell), the UE monitors PEI in the camped cell.

The UE monitors one PEI occasion per DRX cycle. A PEI occasion (PEI-O)
is a set of PDCCH monitoring occasions (MOs) and can consist of multiple
time slots (e.g. subframes or OFDM symbols) where PEI can be sent (TS
38.213 \[4\]). In multi-beam operations, the UE assumes that the same
PEI is repeated in all transmitted beams and thus the selection of the
beam(s) for the reception of the PEI is up to UE implementation.

The time location of PEI-O for UE\'s PO is determined by a reference
point and an offset:

\- The reference point is the start of a reference frame determined by a
frame-level offset from the start of the first PF of the PF(s)
associated with the PEI-O, provided by *pei-FrameOffset* in SIB1;

\- The offset is a symbol-level offset from the reference point to the
start of the first PDCCH MO of this PEI-O, provided by
*firstPDCCH-MonitoringOccasionOfPEI-O* in SIB1.

If one PEI-O is associated with POs of two PFs, the two PFs are
consecutive PFs calculated by the parameters *PF_offset*, *T*, *Ns*, and
*N*. The first PF of the PFs associated with the PEI-O is provided by
(SFN for PF) - floor (*i~PO~*/*Ns*)\**T*/*N*, where SFN for PF is
determined in clause 7.1, *i~PO~* is defined in clause 10.4a in TS
38.213\[4\], *T*, *Ns*, and *N* are determined in clause 7.1.

The PDCCH MOs for PEI are determined as specified in TS 38.213 \[4\]
according to *pei-SearchSpace*, *pei-FrameOffset*,
*firstPDCCH-MonitoringOccasionOfPEI-O* and
*nrofPDCCH-MonitoringOccasionPerSSB-InPO* if configured as specified in
TS 38.331 \[3\]. When *SearchSpaceId* = 0 is configured for
*pei-SearchSpace*, the PDCCH MOs for PEI are same as for RMSI as defined
in clause 13 in TS 38.213 \[4\]. UE determines first PDCCH MO for PEI-O
based on *pei-FrameOffset* and *firstPDCCH-MonitoringOccasionOfPEI-O*,
as for the case with *SearchSpaceId* \> 0 configured.

When *SearchSpaceId* = 0 is configured for *pei-SearchSpace*, the UE
monitors the PEI-O according to *searchSpaceZero*. When *SearchSpaceId*
other than 0 is configured for *pei-SearchSpace,* the UE monitors the
PEI-O according to the search space with the configured *SearchSpaceId*.

A PEI occasion is a set of \'S\*X\' consecutive PDCCH MOs, where \'S\'
is the number of actual transmitted SSBs determined according to
*ssb-PositionsInBurst* in *SIB1*, and X is the
*nrofPDCCH-MonitoringOccasionPerSSB-InPO* if configured or is equal to 1
otherwise. The \[x\*S+K\]^th^ PDCCH MO for PEI in the PEI-O corresponds
to the K^th^ transmitted SSB, where x=0,1,...,X-1, K=1,2,...,S. The
PDCCH MOs for PEI which do not overlap with UL symbols (determined
according to *tdd-UL-DL-ConfigurationCommon*) are sequentially numbered
from zero starting from the first PDCCH MO for PEI in the PEI-O. When
the UE detects a PEI within its PEI-O, the UE is not required to monitor
the subsequent MO(s) associated with the same PEI-O.

If the UE detects PEI and the PEI indicates the subgroup the UE belongs
to monitor its associated PO, as specified in clause 10.4a in TS 38.213
\[4\], the UE monitors the associated PO as specified in clause 7.1. If
the UE does not detect PEI on the monitored PEI occasion or the PEI does
not indicate the subgroup the UE belongs to monitor its associated PO,
as specified in clause 10.4a in TS 38.213 \[4\], the UE is not required
to monitor the associated PO as specified in clause 7.1.

If the UE is unable to monitor the PEI occasion (i.e. all valid PDCCH MO
for PEI) corresponding to its PO, e.g. during cell re-selection, the UE
monitors the associated PO according to clause 7.1.

In RRC_INACTIVE state, when the UE uses the same i­\_s as for RRC_IDLE
state as specified in clause 7.1, the UE shall use the same *i~PO~* as
for RRC_IDLE state. Otherwise, the UE determines the *i~PO~* based on
the formula defined in clause 10.4a in TS 38.213 \[4\].