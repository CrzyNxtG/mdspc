## 11.4 SRS switching

DCI format 2_3 is applicable for uplink carrier(s) of serving cells
where a UE is not configured for PUSCH/PUCCH transmission or for uplink
carrier(s) of a serving cell where *srs-PowerControlAdjustmentStates*
indicates a separate power control adjustment state between SRS
transmissions and PUSCH transmissions.

A UE configured by higher layers with parameter *carrierSwitching* can
be provided

\- a TPC-SRS-RNTI for a DCI format 2_3 by *tpc-SRS-RNTI*

\- an index of a serving cell where the UE interrupts transmission in
order to transmit SRS on one or more other serving cells by
*srs-SwitchFromServCellIndex*

\- an indication of an uplink carrier where the UE interrupts
transmission in order to transmit SRS on one or more other serving cells
by *srs-SwitchFromCarrier*

\- a DCI format 2_3 field configuration type by *typeA* or *typeB*

\- for *typeA*, an index for a set of serving cells is provided by
*cc-SetIndex*, indexes of serving cells in the set of serving cells are
provided by *cc-IndexInOneCC-Set*, and a DCI format 2_3 field includes a
TPC command for each serving cell from the set of serving cells and can
also include a SRS request for SRS transmission on the set of serving
cells

\- for *typeB*, DCI format 2_3 field includes a TPC command for a
serving cell index and can also include a SRS request for SRS
transmission on the serving cell

\- an indication for a serving cell for whether or not a field in DCI
format 2_3 includes a SRS request by *fieldTypeFormat2-3* where a value
of 0/1 indicates absence/presence of the SRS request -- a mapping for a
2 bit SRS request to SRS resource sets is as provided in \[6, TS
38.214\]

\- an index for a location in DCI format 2_3 of a first bit for a field
for a non-supplementary uplink carrier of the serving cell by
*startingBitOfFormat2-3*

\- an index for a location in DCI format 2_3 of a first bit for a field
for a supplementary uplink carrier of the serving cell by
*startingBitOfFormat2-3SUL-v1530*