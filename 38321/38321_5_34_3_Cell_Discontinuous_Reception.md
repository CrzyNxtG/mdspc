### 5.34.3 Cell Discontinuous Reception

Cell DRX is configured if *cellDTX-DRX-ConfigType* is set to *drx* or
*dtxdrx*. Cell DRX operation is activated and deactivated for each
Serving Cell by:

\- receiving a cell DRX indication from lower layers indicating
*activation* or *deactivation* of cell DRX operation, as specified in TS
38.213 \[6\];

\- configuring *cellDTX-DRX-Config* by upper layers: if cell DRX is
configured and *cellDTX-DRX-ActivationStatus* is set to *activated*,
cell DRX operation is activated upon cell DRX configuration; if cell DRX
is configured and *cellDTX-DRX-ActivationStatus* is set to
*deactivated*, cell DRX operation is deactivated upon cell DRX
configuration; if *cellDTX-DRX-Config* is released, cell DRX operation
is deactivated and all the corresponding configurations are released.

When cell DRX is configured and activated for a Serving Cell, the cell
DRX Active Period includes the time while:

\- *cellDTX-DRX-onDurationTimer* is running for the associated Serving
Cell.

For each Serving Cell configured with cell DRX, the MAC entity shall:

1\> if cell DRX is activated for this Serving Cell:

2\> if \[(SFN × 10) + subframe number\] modulo (*cellDTX-DRX-Cycle*) =
(*cellDTX-DRX-StartOffset*):

3\> start *cellDTX-DRX-onDurationTimer* for this serving cell after
*cellDTX-DRX-SlotOffset* from the beginning of the subframe.

NOTE 1: In case of unaligned SFN across carriers in a cell group, the
SFN of the SpCell is used to calculate the cell DRX duration.

1\> if cell DRX is activated and the Serving Cell is not in the cell DRX
Active Period:

2\> not instruct the physical layer to signal a SR on a PUCCH resource
for SR;

2\> not increment the *SR_COUNTER* for a SR;

2\> not start the *sr-ProhibitTimer* for a SR;

2\> not deliver any configured uplink grant and the associated HARQ
information to the HARQ entity;

2\> not instruct a HARQ process associated with a configured uplink
grant to trigger a new transmission or a retransmission;

2\> not report CSI on PUCCH and semi-persistent CSI configured on PUSCH;

2\> if an emergency service is initiated by upper layers and this
Serving Cell is the SpCell:

3\> initiate a Random Access procedure (as specified in clause 5.1.1).

NOTE 2: How the MAC layer in the UE is aware of an ongoing emergency
service is up to UE implementation.

2\> if upper layers provide Access Identity 1 or Access Identity 2 and
this Serving Cell is the SpCell:

3\> initiate a Random Access procedure (as specified in clause 5.1.1).