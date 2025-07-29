### 7.3.2 Scheduling

The MIB is mapped on the BCCH and carried on BCH while all other SI
messages are mapped on the BCCH, where they are dynamically carried on
DL-SCH. The scheduling of SI messages part of Other SI is indicated by
*SIB1*.

For UEs in RRC_IDLE and RRC_INACTIVE while SDT procedure is not ongoing
(see clause 18), a request for Other SI triggers a random access
procedure (see clause 9.2.6) where MSG3 includes the SI request message
unless the requested SI is associated to a subset of the PRACH
resources, in which case MSG1 is used for indication of the requested
Other SI. When MSG1 is used, the minimum granularity of the request is
one SI message (i.e. a set of SIBs), one RACH preamble and/or PRACH
resource can be used to request multiple SI messages and the gNB
acknowledges the request in MSG2. When MSG 3 is used, the gNB
acknowledges the request in MSG4.

For UEs in RRC_CONNECTED, a request for Other SI may be sent to the
network, if configured by the network, in a dedicated manner (i.e., via
UL-DCCH) and the granularity of the request is one SIB. The gNB may
respond with an *RRCReconfiguration* including the requested SIB(s). It
is a network choice to decide which requested SIBs are delivered in a
dedicated or broadcasted manner.

The Other SI may be broadcast at a configurable periodicity and for a
certain duration. The Other SI may also be broadcast when it is
requested by UE in RRC_IDLE/RRC_INACTIVE/RRC_CONNECTED.

For a UE to be allowed to camp on a cell it must have acquired the
contents of the Minimum SI from that cell. There may be cells in the
system that do not broadcast the Minimum SI and where the UE therefore
cannot camp.