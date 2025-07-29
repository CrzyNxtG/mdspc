## 7.7 Carrier Aggregation

When CA is configured, the UE only has one RRC connection with the
network. At RRC connection establishment/re-establishment/handover, one
serving cell provides the NAS mobility information, and at RRC
connection re-establishment/handover, one serving cell provides the
security input. This cell is referred to as the Primary Cell (PCell).
Depending on UE capabilities, Secondary Cells (SCells) can be configured
to form together with the PCell a set of serving cells. The configured
set of serving cells for a UE in a cell group always consists of one
SpCell and one or more SCells.

The reconfiguration, addition and removal of SCells can be performed by
RRC. At intra-NR handover and during connection resume from
RRC_INACTIVE, the network can also add, remove, keep, or reconfigure
SCells for usage with the target PCell. When adding a new SCell,
dedicated RRC signalling is used for sending all required system
information of the SCell i.e. while in connected mode, UEs need not
acquire broadcast system information directly from the SCells.