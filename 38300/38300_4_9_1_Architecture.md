### 4.9.1 Architecture

A Network-Controlled Repeater node, referred to as NCR-node, is an RF
repeater that enables wireless amplifying-and-forwarding functionality
in NG-RAN. The NCR-node is capable of receiving and applying side
control information from a gNB with additional functionality to support
Network-Controlled Repeater.

The NCR-node comprises an NCR-MT and an NCR-Fwd. The NCR-MT is an entity
supporting a subset of the UE functionality that communicates with the
gNB to receive side control information via a control link based on the
NR Uu interface. The NCR-Fwd is the function performing
amplifying-and-forwarding of signals between gNB and UE via the NCR-Fwd
backhaul link and NCR-Fwd access link, respectively. The NCR-Fwd can
support multiple beams towards the UE. The NCR-Fwd can support multiple
beams in the backhaul link, and those may be different from the beams in
the control link. The behaviour of the NCR-Fwd is controlled according
to the side control information received from the gNB. The NCR-node is
modelled as depicted in Figure 4.9.1-1.

![](media/image17.emf)

Figure 4.9.1-1: Conceptual model of network-controlled repeater.

An NCR-MT establishes SRBs and, optionally, DRB(s) with a gNB. The
establishment of DRB(s) can be used to transport OAM traffic.

The signal that NCR-Fwd forwards is associated to the cell that the
NCR-MT is connected to via the control link. Whether the NCR-Fwd can
forward other signals is up to implementation.