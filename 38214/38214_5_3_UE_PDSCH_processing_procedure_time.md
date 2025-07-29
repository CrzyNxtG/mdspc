## 5.3 UE PDSCH processing procedure time

If the first uplink symbol of the PUCCH which carries the HARQ-ACK
information, as defined by the assigned HARQ-ACK timing *K~1\ ~*and
K~offset~, if configured, and the PUCCH resource to be used and
including the effect of the timing advance, starts no earlier than at
symbol *L~1~*, where *L~1~* is defined as the next uplink symbol with
its CP starting after
$T_{proc,1} = (N_{1} + d_{1,1} + d_{2} + d_{3})(2048 + 144) \cdot \kappa 2^{- \mu} \cdot T_{C} + T_{ext}$
after the end of the last symbol of the PDSCH carrying the TB being
acknowledged, then the UE shall provide a valid HARQ-ACK message. For a
PDSCH with disabled HARQ-ACK
feedback,$\ T_{proc,1} = (N_{1} + d_{1,1} + d_{2})(2048 + 144) \cdot \kappa 2^{- \mu} \cdot T_{C} + T_{ext}$.

*- N~1~* is based on *µ* of table 5.3-1 and table 5.3-2 for UE
processing capability 1 and 2 respectively, where *µ* corresponds to the
one of (*µ~PDCCH~*, *µ~PDSCH~*, *µ~UL~*) resulting with the largest
*T~proc,1~*, where the *µ~PDCCH~* corresponds to the subcarrier spacing
of the PDCCH scheduling the PDSCH, the *µ~PDSCH~* corresponds to the
subcarrier spacing of the scheduled PDSCH, and *µ~UL~* corresponds to
the subcarrier spacing of the uplink channel with which the HARQ-ACK is
assumed to be transmitted for PDSCH with or without disabled HARQ-ACK
feedback, and κ is defined in clause 4.1 of \[4, TS 38.211\].

*-* For UE processing capability 2,

*-* if the UE is not indicating *simulDMRS-PDSCH*, the UE is not
expected to be simultaneously configured with higher layer parameter
*processingType2Enabled* set to \'enable\' and higher layer parameter
*dmrs-TypeEnh*, and the additional processing delay *d~3\ ~*is 0.

\- if the UE is indicating *simulDMRS-PDSCH*,

*-* if the UE is configured with higher layer parameter *dmrs-TypeEnh,*
the additional processing delay *d~3\ ~*is indicated by
*simulDMRS-PDSCH*,

*-* otherwise *d~3\ ~*=0.

*-* For operation with shared spectrum channel access in FR1,
![](media/image696.wmf)is calculated according to \[4, TS 38.211\],
otherwise ![](media/image696.wmf)=0.

*-* If the PDSCH DM-RS position $l_{1}$ for the additional DM-RS in
Table 7.4.1.1.2-3 in clause 7.4.1.1.2 of \[4, TS 38.211\] is
$l_{1} = 12$ then *N~1,0~=14* in Table 5.3-1*,* otherwise *N~1,0~=13.*

\- If the UE is configured with multiple active component carriers, the
first uplink symbol which carries the HARQ-ACK information further
includes the effect of timing difference between the component carriers
as given in \[11, TS 38.133\].

\- For the PDSCH mapping type A as given in clause 7.4.1.1 of \[4, TS
38.211\]: if the last symbol of PDSCH is on the *i-*th symbol of the
slot where *i* \< 7, then *d~1,1~ = 7 - i*, otherwise *d~1,1~ = 0*

\- If a PUCCH of a larger priority index would overlap with a PUCCH of a
smaller priority index, or with a PUSCH of a smaller priority index and
the PUCCH of a larger priority index and the PUSCH of a smaller priority
index are not simultaneously transmitted and the UE is not provided
*uci-MuxWithDiffPrio* for the primary PUCCH group or
*uci-MuxWithDiffPrioSecondaryPUCCHgroup* for the secondary PUCCH group,
*d~2~* for the PUCCH of a larger priority is set as reported by the UE;
otherwise *d~2~ = 0.*

\- For UE processing capability 1: If the PDSCH is mapping type B as
given in clause 7.4.1.1 of \[4, TS 38.211\], and

\- if the number of PDSCH symbols allocated is *L* ≥ 7, then *d~1,1~* =
0,

\- if the number of PDSCH symbols allocated is *L* ≥ 4 and *L* ≤ 6, then
*d~1,1~* = 7- *L.*

\- if the number of PDSCH symbols allocated is *L* = *3* then *d~1,1~ =
3 +* min *(d,1)*, where *d* is the number of overlapping symbols of the
scheduling PDCCH and the scheduled PDSCH.

\- if the number of PDSCH symbols allocated is 2, then *d~1,1~* = 3*+d*,
where *d* is the number of overlapping symbols of the scheduling PDCCH
and the scheduled PDSCH.

\- For UE processing capability 2: If the PDSCH is mapping type B as
given in clause 7.4.1.1 of \[4, TS 38.211\],

\- if the number of PDSCH symbols allocated is *L* ≥ 7, then *d~1,1~* =
0,

\- if the number of PDSCH symbols allocated is *L* ≥ 3 and *L* ≤ 6, then
*d~1,1~* is the number of overlapping symbols of the scheduling PDCCH
and the scheduled PDSCH,

\- if the number of PDSCH symbols allocated is 2,

\- if the scheduling PDCCH was in a 3-symbol CORESET and the CORESET and
the PDSCH had the same starting symbol, then *d~1,1~* = 3,

\- otherwise *d~1,1~* is the number of overlapping symbols of the
scheduling PDCCH and the scheduled PDSCH.

\- For UE processing capability 2 with scheduling limitation when
*µ~PDSCH~* = 1, if the scheduled RB allocation exceeds 136 RBs, the UE
defaults to capability 1 processing time. The UE may skip decoding a
number of PDSCHs with last symbol within 10 symbols before the start of
a PDSCH that is scheduled to follow Capability 2, if any of those PDSCHs
are scheduled with more than 136 RBs with 30kHz SCS and following
Capability 1 processing time.

\- For a UE that supports capability 2 on a given cell, the processing
time according to UE processing capability 2 is applied if the high
layer parameter *processingType2Enabled* in *PDSCH-ServingCellConfig* is
configured for the cell and set to \'enable\'.

\- PDSCH processing capability 2 is not applied to PDSCH scheduled by
PDCCH with DCI format 4_0, 4_1, or 4_2.

\- If this PUCCH resource is overlapping with another PUCCH or PUSCH
resource, then HARQ-ACK is multiplexed following the procedure in clause
9.2.5 of \[6, TS 38.213\], otherwise the HARQ-ACK message is transmitted
on PUCCH.

\- UE is not expected to be scheduled to transmit PUCCH carrying the
HARQ-ACK information for PDSCH scheduled by a PDCCH if uplink switching
gap is triggered for the PUCCH as defined in clause 6.1.6 and the first
uplink symbol of the PUCCH starts earlier than the duration of
{$T_{switch}$ + $T_{proc,1}$} from the last symbol of the PDCCH, where
$T_{switch}$ equals to the switching gap duration.

Otherwise the UE may not provide a valid HARQ-ACK corresponding to the
scheduled PDSCH. The value of *T~proc,1~* is used both in the case of
normal and extended cyclic prefix.

For a PDSCH that consists of two PDSCH transmission occasions in time
domain in one slot, *d~1,1~* is calculated based on the first PDSCH
transmission occasion in the slot, and as described above.

For PDSCH with mapping Type B, if PDSCH is scheduled by a PDCCH
reception that includes two PDCCH candidates from two respective search
space sets, as described in clause 10.1 of \[6, TS 38.213\], *d~1,1~*
for PDSCH processing time is determined by considering the PDCCH
candidate that results in larger d~1,1~ value.

Table 5.3-1: PDSCH processing time for PDSCH processing capability 1

+-------------------------+---------------------------------------------------------------------------------------------+
| ![](media/image697.wmf) | PDSCH decoding time *N~1~* \[symbols\]                                                      |
|                         +----------------------------------------------+----------------------------------------------+
|                         | *dmrs-AdditionalPosition* = \'pos0\' in\     | *dmrs-AdditionalPosition* ≠ \'pos0\' in\     |
|                         | *DMRS-DownlinkConfig* in\                    | *DMRS-DownlinkConfig* in any of\             |
|                         | *dmrs-DownlinkForPDSCH-MappingTypeA* and     | *dmrs-DownlinkForPDSCH-MappingTypeA*,        |
|                         | *dmrs-DownlinkForPDSCH-MappingTypeB* if      | *dmrs-DownlinkForPDSCH-MappingTypeB,         |
|                         | either higher layer parameter is configured, | dmrs-DownlinkForPDSCH-MappingTypeA-DCI-1-2,  |
|                         | and in                                       | dmrs-DownlinkForPDSCH-MappingTypeB-DCI-1-2,* |
|                         | *dmrs-DownlinkForPDSCH-MappingTypeA-DCI-1-2* |                                              |
|                         | and                                          | or if none of the higher layer parameters is |
|                         | *dmrs-DownlinkForPDSCH-MappingTypeB-DCI-1-2* | configured                                   |
|                         | if either higher layer parameter is          |                                              |
|                         | configured                                   |                                              |
+=========================+==============================================+==============================================+
| 0                       | 8                                            | *N~1,0~*                                     |
+-------------------------+----------------------------------------------+----------------------------------------------+
| 1                       | 10                                           | 13                                           |
+-------------------------+----------------------------------------------+----------------------------------------------+
| 2                       | 17                                           | 20                                           |
+-------------------------+----------------------------------------------+----------------------------------------------+
| 3                       | 20                                           | 24                                           |
+-------------------------+----------------------------------------------+----------------------------------------------+
| 5                       | 80                                           | 96                                           |
+-------------------------+----------------------------------------------+----------------------------------------------+
| 6                       | 160                                          | 192                                          |
+-------------------------+----------------------------------------------+----------------------------------------------+

Table 5.3-2: PDSCH processing time for PDSCH processing capability 2

+-------------------------+-----------------------------------------------------------------+
| ![](media/image697.wmf) | PDSCH decoding time *N~1~* \[symbols\]                          |
|                         +-----------------------------------------------------------------+
|                         | *dmrs-AdditionalPosition* = \'pos0\' in\                        |
|                         | *DMRS-DownlinkConfig* in\                                       |
|                         | *dmrs-DownlinkForPDSCH-MappingTypeA* and                        |
|                         | *dmrs-DownlinkForPDSCH-MappingTypeB* if either higher layer     |
|                         | parameter is configured, and in                                 |
|                         | *dmrs-DownlinkForPDSCH-MappingTypeA-DCI-1-2* and                |
|                         | *dmrs-DownlinkForPDSCH-MappingTypeB-DCI-1-2* if either higher   |
|                         | layer parameter is configured                                   |
+=========================+=================================================================+
| 0                       | 3                                                               |
+-------------------------+-----------------------------------------------------------------+
| 1                       | 4.5                                                             |
+-------------------------+-----------------------------------------------------------------+
| 2                       | 9 for frequency range 1                                         |
+-------------------------+-----------------------------------------------------------------+