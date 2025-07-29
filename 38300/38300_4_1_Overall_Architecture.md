## 4.1 Overall Architecture

An NG-RAN node is either:

\- a gNB, providing NR user plane and control plane protocol
terminations towards the UE; or

\- an ng-eNB, providing E-UTRA user plane and control plane protocol
terminations towards the UE.

The gNBs and ng-eNBs are interconnected with each other by means of the
Xn interface. The gNBs and ng-eNBs are also connected by means of the NG
interfaces to the 5GC, more specifically to the AMF (Access and Mobility
Management Function) by means of the NG-C interface and to the UPF (User
Plane Function) by means of the NG-U interface (see TS 23.501 \[3\]).

NOTE: The architecture and the F1 interface for a functional split are
defined in TS 38.401 \[4\].

The NG-RAN architecture is illustrated in Figure 4.1-1 below.

![](media/image3.emf)

Figure 4.1-1: Overall Architecture