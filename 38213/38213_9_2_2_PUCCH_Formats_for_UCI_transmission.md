### 9.2.2 PUCCH Formats for UCI transmission

If a UE is not transmitting PUSCH, and the UE is transmitting UCI, the
UE transmits UCI in a PUCCH using

\- PUCCH format 0 if

\- the transmission is over 1 symbol or 2 symbols,

\- the number of HARQ-ACK information bits with positive or negative SR
(HARQ-ACK/SR bits) is 1 or 2

\- PUCCH format 1 if

\- the transmission is over 4 or more symbols,

\- the number of HARQ-ACK/SR bits is 1 or 2

\- PUCCH format 2 if

\- the transmission is over 1 symbol or 2 symbols,

\- the number of UCI bits is more than 2

\- PUCCH format 3 if

\- the transmission is over 4 or more symbols,

\- the number of UCI bits is more than 2,

> \- the PUCCH resource does not include an orthogonal cover code, or
> the UE is provided *useInterlacePUCCH-PUSCH* in *BWP-UplinkDedicated*

\- PUCCH format 4 if

\- the transmission is over 4 or more symbols,

\- the number of UCI bits is more than 2,

\- the PUCCH resource includes an orthogonal cover code and the UE is
not provided *useInterlacePUCCH-PUSCH* in *BWP-UplinkDedicated*

A spatial setting for a PUCCH transmission by a UE is provided by

\- an indicated *TCI-State* or *TCI-UL-State*, if provided, as described
in \[6, TS 38.214\];

\- *PUCCH-SpatialRelationInfo* if the UE is configured with a single
value for *pucch-SpatialRelationInfoId*;

\- as described in \[11, TS 38.321\], if the UE is provided multiple
values for *PUCCH-SpatialRelationInfo*. The UE applies corresponding
actions in \[11, TS 38.321\] and a corresponding setting for a spatial
domain filter to transmit PUCCH in the first slot that is after slot
$k + 3 \cdot N_{\text{slot}}^{\text{subframe,}\mu}$ where $k$ is the
slot where the UE would transmit a PUCCH with HARQ-ACK information with
ACK value corresponding to a PDSCH reception providing the
*PUCCH-SpatialRelationInfo*, each slot consists of
$N_{\text{symb}}^{\text{slot}}$ symbols as defined in \[4, TS 38.211\],
and $\mu$ is the SCS configuration for the PUCCH

\- If *PUCCH-SpatialRelationInfo* or the indicated *TCI-UL-State*
provides *ssb-Index*, the UE transmits the PUCCH using a same spatial
domain filter as for a reception of a SS/PBCH block with index provided
by *ssb-Index* for a same serving cell or, if *servingCellId* is
provided, for a serving cell indicated by *servingCellId*

\- else if *PUCCH-SpatialRelationInfo* or the indicated *TCI-UL-State*
provides *csi-RS-Index*, or the indicated *TCI-State* provides *csi-rs*
configured with *qcl-Type* set to \'typeD\', the UE transmits the PUCCH
using a same spatial domain filter as for a reception of a CSI-RS with
resource index provided by *csi-RS-Index* or csi-rs for a same serving
cell or, if *servingCellId* or *cell* is provided, for a serving cell
indicated by *servingCellId* or *cell*

\- else *PUCCH-SpatialRelationInfo* or the indicated *TCI-UL-State*
provides *srs*, the UE transmits the PUCCH using a same spatial domain
filter as for a transmission of an SRS with resource index provided by
*resource* for a same serving cell and/or active UL BWP or, if
*servingCellId* and/or *uplinkBWP* are provided, for a serving cell
indicated by *servingCellId* and/or for an UL BWP indicated by
*uplinkBWP*

\- an indicated *applyIndicatedTCI-State*, if provided

\- if *applyIndicatedTCI-State* = \'first\', the UE transmits a PUCCH
using a spatial domain filter corresponding to a first *TCI-State* or
*TCI-UL-State*

\- if *applyIndicatedTCI-State* = \'second\', the UE transmits a PUCCH
using a spatial domain filter corresponding to second *TCI-State* or
*TCI-UL-State*

\- if *applyIndicatedTCI-State* = \'both\', the UE transmits a PUCCH
using respective first and second spatial domain filters corresponding
to the first and the second *TCI-State* or *TCI-UL-State*

If the UE

\- is not provided *coresetPoolIndex* or is provided *coresetPoolIndex*
with a value of 0 for first CORESETs on an active DL BWP of a serving
cell, and

\- is provided *coresetPoolIndex* with a value of 1 for second CORESETs
on the active DL BWP of the serving cells,

the first and second *TCI-State* or *TCI-UL-State* are specific to the
first and second CORESETs, respectively.

If a UE

\- is not provided *pathlossReferenceRSs* in *PUCCH-PowerControl*,

\- is provided *enableDefaultBeamPL-ForPUCCH*, and

\- is not provided *PUCCH-SpatialRelationInfo*, and

\- is not provided *coresetPoolIndex* value of 1 for any CORESET, or is
provided *coresetPoolIndex* value of 1 for all CORESETs, in
*ControlResourceSet *and no codepoint of a TCI field, if any, in a DCI
format of any search space set maps to two TCI states \[5, TS 38.212\]

a spatial setting for a PUCCH transmission from the UE is same as a
spatial setting for PDCCH receptions by the UE in the CORESET with the
lowest ID on the active DL BWP of the PCell and, if the CORESET has two
activated TCI states as described in clause 10.1, the UE determines the
spatial setting for the PUCCH transmission based on the first TCI state.
For a PUCCH transmission over multiple slots, a same spatial setting
applies to the PUCCH transmission in each of the multiple slots.

A number of DMRS symbols for a PUCCH transmission using PUCCH format 3
or 4 is provided by *additionalDMRS*.

Use of π/2-BPSK, instead of QPSK, for a PUCCH transmission using PUCCH
format 3 or 4 is indicated by *pi2BPSK*.

A UE that has indicated a capability
*beamCorrespondenceWithoutUL-BeamSweeping* set to \'supported\', as
described in \[18, TS 38.306\], can determine a spatial domain filter to
be used while performing the applicable channel access procedures
described in \[15, TS 37.213\] prior to a PUCCH transmission as follows:

\- if UE is configured with a single value for
*pucch-SpatialRelationInfoId* for the UL transmission, the UE may use a
spatial domain filter that is same as the spatial domain filter
associated with *referenceSignal* in the corresponding
*pucch-SpatialRelationInfo*,

\- if UE is configured with more than one value for
*pucch-SpatialRelationInfoId* for the UL transmission, the UE may use a
spatial domain filter that is same as the spatial domain filter
associated with *referenceSignal* in the activated
*pucch-SpatialRelationInfo*.