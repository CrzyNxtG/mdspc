### 4.9.5 Network-controlled repeater management

Network-Controlled Repeater identification is performed in RAN, and
Network-Control Repeater authorization is performed in 5GC. The general
procedure of the Network-Controlled Repeater management is illustrated
in Figure 4.9.5-1:

![](media/image18.emf)

Figure 4.9.5-1: Network-Controlled Repeater management.

1\. The gNB broadcasts the Network-Controlled Repeater supported
information via system information.

6\. When a Network-Controlled Repeater is trying to access the network
as a Network-Controlled Repeater, the Network-Controlled Repeater
indication is sent to the serving gNB.

7\. The serving gNB selects an appropriate AMF for the
Network-Controlled Repeater.

9\. AMF provides Network-Controlled Repeater authorization information
to the gNB.

Other steps refer to the signalling flow as defined in 9.2.1.3.