## 4.4 Functions

The MAC sublayer supports the following functions:

\- mapping between logical channels and transport channels;

\- multiplexing of MAC SDUs from one or different logical channels onto
transport blocks (TB) to be delivered to the physical layer on transport
channels;

\- demultiplexing of MAC SDUs to one or different logical channels from
transport blocks (TB) delivered from the physical layer on transport
channels;

\- scheduling information reporting;

\- error correction through HARQ;

\- logical channel prioritization;

\- priority handling between overlapping resources of one UE;

\- radio resource selection.

The relevance of MAC functions for uplink, downlink, and sidelink is
indicated in Table 4.4-1.

Table 4.4-1: The link direction association of MAC functions.

  --------------------------------------------------------------------------------
  MAC function                           Downlink   Uplink   Sidelink   Sidelink
                                                             TX         RX
  -------------------------------------- ---------- -------- ---------- ----------
  Mapping between logical channels and   X          X        X          X
  transport channels                                                    

  Multiplexing                                      X        X          

  Demultiplexing                         X                              X

  Scheduling information reporting                  X        X          

  Error correction through HARQ          X          X        X          X

  Logical Channel prioritization                    X        X          

  Radio resource selection                                   X          
  --------------------------------------------------------------------------------