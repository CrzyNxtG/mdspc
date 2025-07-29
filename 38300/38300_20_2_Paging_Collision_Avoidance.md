## 20.2 Paging Collision Avoidance

The purpose of paging collision avoidance is to address the overlap of
paging occasions on both USIMs when a MUSIM device (e.g. dual USIM
device) is in RRC_IDLE/RRC_INACTIVE state in both the networks (e.g.
Network A and Network B) associated with respective USIMs. Network A is
NR and Network B is E-UTRA or NR.

A MUSIM device may determine potential paging collision on two networks
and may trigger actions to prevent potential paging collision on NR
network as specified in TS 23.501 \[3\].

NOTE: It is left to UE implementation as to how it selects one of the
two RATs/networks for paging collision avoidance.