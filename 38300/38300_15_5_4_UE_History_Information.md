### 15.5.4 UE History Information

The source NG-RAN node collects and stores the UE History Information
for as long as the UE stays in one of its cells.

The UE may report the UE history information when connecting to a cell
of the NG-RAN node, consisting of PCell and PSCell mobility history
information, as specified in TS 38.331 \[12\].

When information needs to be discarded because the list is full, such
information will be discarded in order of its position in the list,
starting with the oldest cell record. If the list is full, and the UE
history information from the UE is available, the UE history information
from the UE should also be discarded.

The resulting information is then used in subsequent handover
preparations by means of the Handover Preparation procedures over the NG
and XN interfaces, which provide the target NG-RAN node with a list of
previously visited cells and associated (per-cell) information elements.
The Handover Preparation procedures also trigger the target NG-RAN node
to start collection and storage of UE history Information and thus to
propagate the collected information.

In case of CHO, the target NG-RAN node updates the time UE stayed in
cell of the latest PCell entry (i.e. the source cell) when the UE
successfully accesses a candidate cell of the target NG-RAN node. The
updated value of the time UE stayed in the source cell is equal to the
value received from the source NG-RAN node during the Handover
Preparation plus the time from receiving the Handover Request message
from the source NG-RAN node to receiving the RRC Reconfiguration
Complete message from the UE. When the target NG-RAN node receives the
SCG UHI from the source NG-RAN node via the Handover Request message,
the target NG-RAN node also updates the time UE stayed in cell of the
latest PSCell entry (i.e. the source PSCell) as specified in TS 37.340
\[21\].