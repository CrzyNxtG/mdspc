## 9.A PUCCH cell switching

This clause is applicable when a UE is provided a PUCCH-sSCell by
*pucch-sSCell* and the PUCCH-sSCell is activated and does not have a
dormant UL/DL active BWP. This clause is not applicable for slots with
$N_{sym}^{slot}$ symbols \[4, TS 38.211\] of a reference SCS
configuration provided by *tdd-UL-DL-ConfigurationCommon* for the PCell
where the UE would transmit a PUCCH with ![](media/image63.wmf)
repetitions of any priority, starting from the slot following the slot
indicated to the UE as described in clause 9.2.3 for HARQ-ACK reporting,
or following the slot determined as described in clause 9.2.4 for SR
reporting, or in clause 5.2.1.4 of \[6, TS 38.214\] for CSI reporting,
until the slot of the last repetition of the PUCCH transmission, as
described in clause 9.2.6 if the UE is provided *PUCCH-sSCellPattern*.

A UE can be provided a periodic cell switching pattern for PUCCH
transmissions by *pucch-sSCellPattern.* Each bit of the pattern
corresponds to a slot with $N_{sym}^{slot}$ symbols \[4, TS 38.211\] for
a reference SCS configuration provided
by *tdd-UL-DL-ConfigurationCommon* for the PCell with a value of \'0\'
or a value of \'1\' indicating, respectively, the PCell or the
PUCCH-sSCell as the cell for PUCCH transmissions during the slot with
$N_{sym}^{slot}$ symbols of the reference SCS configuration. The UE does
not transmit a PUCCH in a slot on a cell if the pattern indicates a
different cell for PUCCH transmission during the slot. A slot on the
active UL BWP of the PUCCH-sSCell does not overlap with more than one
slot on the active UL BWP of the PCell. If a slot for the active UL BWP
of the PCell overlaps with more than one slot on the active BWP of the
PUCCH-sSCell and the UE would transmit a PUCCH on the PUCCH-sSCell, the
UE considers the first of the overlapping slots for the PUCCH
transmission on the PUCCH-sSCell.

If a UE is provided *pucch-sSCellDyn* or *pucch-sSCellDynDCI-1-2* or
*pucch-sSCellDynDCI-1-3*, a corresponding DCI format associated with
generation of HARQ-ACK information by the UE can include a PUCCH cell
indicator field \[5, TS 38.212\] with a value of \'0\' or a value of
\'1\' indicating, respectively, whether a PUCCH transmission with the
HARQ-ACK information by the UE is on the PCell or on the PUCCH-sSCell.
When the UE transmits a PUCCH with HARQ-ACK information that is
associated only with SPS PDSCH receptions, the UE transmits the PUCCH on
the PCell. The UE does not expect the PUCCH cell indicator field to
indicate the PUCCH-sSCell for a PUCCH transmission in a slot that
overlaps with a slot on the PCell where the UE would transmit another
PUCCH of same or different priority index.

A UE transmits a PUCCH on a PUCCH-sSCell with a power that the UE
determines as described in clause 7.2.1, where the UE applies

\- a *p0-PUCCH-Value* from *pucch-PowerControl* in *PUCCH-Config* for
the PUCCH-sSCell for the determination of $P_{O,PUCCH,b,f,c}(q_{u})$

\- a *pucch-PathlossReferenceRS-Id* from *pucch-PowerControl* in
*PUCCH-Config* for the PUCCH-sSCell for the determination of
${PL}_{b,f,c}(q_{d})$

\- a PUCCH power control adjustment state $g_{b,0,c}(i,0)$ for active UL
BWP $b$ of the UL carrier of PUCCH-sSCell $c$ and PUCCH transmission
occasion $i$ where $\delta_{PUCCH,b,0,c}(i,0)$ is a TPC command value
included in a DCI format associated with generation of HARQ-ACK
information for multiplexing in a PUCCH transmission on the PUCCH-sSCell
as indicated either by a *pucch-sSCellPattern* or by a PUCCH cell
indicator field in the DCI format, or provided by DCI format 2_2 with
CRC scrambled by TPC-PUCCH-RNTI for the PUCCH-sSCell as described in
clause 11.3