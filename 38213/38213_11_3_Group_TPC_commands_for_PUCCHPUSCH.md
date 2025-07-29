## 11.3 Group TPC commands for PUCCH/PUSCH

For PUCCH transmission on a serving cell, a UE can be provided

\- a TPC-PUCCH-RNTI for a DCI format 2_2 by *tpc-PUCCH-RNTI*

\- a field in DCI format 2_2 is a TPC command of 2 bits mapping to
$\delta_{PUCCH,b,f,c}$ values as described in clause 7.2.1

\- an index for a location in DCI format 2_2 of a first bit for a TPC
command field for the PCell, or for a carrier of the PCell by
*tpc-IndexPCell*

\- an index for a location in DCI format 2_2 of a first bit for a TPC
command field for a PUCCH-sSCell in the primary PUCCH cell group, by
*tpc-IndexPUCCH-sScell*

\- an index for a location in DCI format 2_2 of a first bit for a TPC
command field for the PUCCH-SCell or for a carrier for the PUCCH-SCell
by *tpc-IndexPUCCH-Scell*

\- an index for a location in DCI format 2_2 of a first bit for a TPC
command field for a PUCCH-sSCell in the secondary PUCCH cell group, by
*tpc-IndexPUCCH-sScellSecondaryPUCCHgroup*

\- a mapping for the PUCCH power control adjustment state
$l \in \left\{ 0,1 \right\}$, by a corresponding {0, 1} value of a
closed loop index field that is appended to the TPC command field in DCI
format 2_2 if the UE indicates a capability to support two PUCCH power
control adjustment states by *twoDifferentTPC-Loop-PUCCH*, and if the UE
is configured for two PUCCH power control adjustment states by
*twoPUCCH-PC-AdjustmentStates*

The UE is also provided on a serving cell with a configuration for a
search space set $s$ and a corresponding CORESET $p$ for monitoring
PDCCH candidates for DCI format 2_2 with CRC scrambled by a
TPC-PUCCH-RNTI as described in clause 10.1.

For PUSCH transmission on a serving cell, a UE can be provided

\- a TPC-PUSCH-RNTI for a DCI format 2_2 by *tpc-PUSCH-RNTI*

\- a field in DCI format 2_2 is a TPC command of 2 bits mapping to
$\delta_{PUSCH,b,f,c}$ values as described in clause 7.1.1

\- an index for a location in DCI format 2_2 of a first bit for a TPC
command field for an uplink carrier of the serving cell by *tpc-Index*

\- an index for a location in DCI format 2_2 of a first bit for a TPC
command field for a supplementary uplink carrier of the serving cell by
*tpc-IndexSUL*

\- an index of the serving cell by *targetCell*. If *targetCell* is not
provided, the serving cell is the cell of the PDCCH reception for DCI
format 2_2

\- a mapping for the PUSCH power control adjustment state
$l \in \left\{ 0,1 \right\}$, by a corresponding {0, 1} value of a
closed loop index field that is appended to the TPC command field for
the uplink carrier or for the supplementary uplink carrier of the
serving cell in DCI format 2_2 if the UE indicates a capability to
support two PUSCH power control adjustment states, by
*twoDifferentTPC-Loop-PUSCH*, and if the UE is configured for two PUSCH
power control adjustment states by *twoPUSCH-PC-AdjustmentStates*

The UE is also provided for the serving cell of the PDCCH reception for
DCI format 2_2 with a configuration for a search space set $s$ and a
corresponding CORESET $p$ for monitoring PDCCH candidates for DCI format
2_2 with CRC scrambled by a TPC-PUSCH-RNTI as described in clause 10.1.