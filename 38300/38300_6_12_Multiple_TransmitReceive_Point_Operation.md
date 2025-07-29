## 6.12 Multiple Transmit/Receive Point Operation

In Multiple Transmit/Receive Point (multi-TRP) operation, a serving cell
can schedule the UE from two TRPs, providing better coverage,
reliability and/or data rates for PDSCH, PDCCH, PUSCH, and PUCCH.

There are two different operation modes to schedule multi-TRP PDSCH
transmissions: single-DCI and multi-DCI. For both modes, control of
uplink and downlink operation can be done by physical layer and MAC
layer, within the configuration provided by the RRC layer. In single-DCI
mode, the UE is scheduled by the same DCI for both TRPs and in multi-DCI
mode, the UE is scheduled by independent DCIs from each TRP.

There are two different operation modes for multi-TRP PDCCH: PDCCH
repetition as in Clause 5.2.3 and Single Frequency Network (SFN) based
PDCCH transmission. In both modes, the UE can receive two PDCCH
transmissions, one from each TRP, carrying the same DCI. In PDCCH
repetition mode, the UE can receive the two PDCCH transmissions carrying
the same DCI from two linked search spaces each associated with a
different CORESET. In SFN based PDCCH transmission mode, the UE can
receive the two PDCCH transmissions carrying the same DCI from a single
search space/CORESET using different TCI states.

For multi-TRP PUSCH repetition, according to indications in a single DCI
or in a semi-static configured grant provided over RRC, the UE performs
PUSCH transmission of the same contents toward two TRPs with
corresponding beam directions associated with different spatial
relations. For multi-TRP PUCCH repetition, the UE performs PUCCH
transmission of the same contents toward two TRPs with corresponding
beam directions associated with different spatial relations.

For inter-cell multi-TRP operation, for multi-DCI PDSCH transmission,
one or more TCI states can be associated with SSB with a PCI different
from the serving cell PCI. The activated TCI states can be associated
with at most one PCI different from the serving cell PCI at a time.

For inter-cell and intra-cell multi-DCI multi-TRP operation, up to two
TAGs with associated TAG IDs can be configured per serving cell. Each
UL/Joint TCI state is associated with a TAG ID and the UE applies the
timing advance of the TAG ID associated with the UL/joint TCI state
utilized for UL transmission.

For single-DCI multi-TRP Simultaneous Transmission with Multi-Panel
(STxMP) Spatial Domain Multiplexing (SDM) PUSCH transmission, different
layers of one PUSCH are separately transmitted towards two TRPs. For
single-DCI multi-TRP STxMP SFN PUSCH transmission, same layers of one
PUSCH are transmitted towards two TRPs. For multi-DCI based multi-TRP
STxMP PUSCH+PUSCH transmission, two PUSCHs are transmitted towards two
TRPs. For single-DCI multi-TRP STxMP SFN PUCCH transmission, one PUCCH
is transmitted towards two TRPs.