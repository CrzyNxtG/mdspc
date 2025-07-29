### 5.34.2 Cell Discontinuous Transmission

Cell DTX is configured if *cellDTX-DRX-ConfigType* is set to *dtx* or
*dtxdrx*. Cell DTX operation is activated and deactivated for each
Serving Cell by:

\- receiving a cell DTX indication from lower layers indicating
*activation* or *deactivation* of cell DTX operation, as specified in TS
38.213 \[6\];

\- configuring *cellDTX-DRX-Config* by upper layers: if cell DTX is
configured and *cellDTX-DRX-ActivationStatus* is set to *activated*,
cell DTX operation is activated upon cell DTX configuration; if cell DTX
is configured and *cellDTX-DRX-ActivationStatus* is set to
*deactivated*, cell DTX operation is deactivated upon cell DTX
configuration; if *cellDTX-DRX-Config* is released, cell DTX operation
is deactivated and all the corresponding configurations are released.

When cell DTX is configured and activated for a Serving Cell, the cell
DTX Active Period includes the time while:

\- *cellDTX-DRX-onDurationTimer* is running for the associated Serving
Cell.

For each Serving Cell configured with cell DTX, the MAC entity shall:

1\> if cell DTX is activated for this Serving Cell:

2\> if \[(SFN × 10) + subframe number\] modulo (*cellDTX-DRX-Cycle*) =
(*cellDTX-DRX-StartOffset*):

3\> start *cellDTX-DRX-onDurationTimer* for this serving cell after
*cellDTX-DRX-SlotOffset* from the beginning of the subframe.

NOTE: In case of unaligned SFN across carriers in a cell group, the SFN
of the SpCell is used to calculate the cell DTX duration.

1\> if cell DTX operation is deactivated for this Serving Cell; or

1\> if the Serving Cell is in the cell DTX Active Period:

2\> monitor PDCCH on this Serving Cell, as specified in TS 38.213 \[6\]
and other clauses of this specification.

1\> if any *drx-RetransmissionTimerDL*, *drx-RetransmissionTimerUL* or
*drx-RetransmissionTimerSL* (as described in clause 5.7) is running on
any Serving Cell in the DRX group of this Serving Cell; or

1\> if *ra-ContentionResolutionTimer* (as described in clause 5.1.5) or
*msgB-ResponseWindow* (as described in clause 5.1.4a) is running; or

1\> if a Scheduling Request is sent on PUCCH and is pending (as
described in clause 5.4.4 or 5.22.1.5); or

1\> if a PDCCH indicating a new transmission addressed to the C-RNTI of
the MAC entity has not been received after successful reception of a
Random Access Response for the Random Access Preamble not selected by
the MAC entity among the contention-based Random Access Preamble (as
described in clauses 5.1.4 and 5.1.4a):

2\> monitor PDCCH on the Serving Cells in the DRX group of this Serving
Cell, as specified in TS 38.213 \[6\] and other clauses of this
specification.

1\> if *ra-ResponseWindow* (as described in clause 5.1.4) is running and
this Serving Cell is the SpCell:

2\> monitor PDCCH on this Serving Cell (as described in clause 5.1.4).

For each Serving Cell configured with cell DTX, the MAC entity need not:

1\> if cell DTX operation is activated and the Serving Cell is not in
the cell DTX Active Period:

2\> monitor PDCCH for the MAC entity\'s RNTIs listed in clauses 5.7 and
5.7b, irrespective of the requirements of clauses 5.7 and 5.7b, unless
stated otherwise in this clause;

2\> instruct the physical layer to receive transport block on the DL-SCH
of this Serving Cell according to a configured downlink assignment for
SPS;

2\> indicate the presence of a configured downlink assignment and
deliver the stored HARQ information to the HARQ entity;

2\> set the HARQ Process ID to the HARQ Process ID associated with the
PDSCH duration of a configured downlink assignment;

2\> consider the NDI bit for the HARQ process corresponding to the PDSCH
duration of a configured downlink assignment to have been toggled for
the configured downlink assignment.