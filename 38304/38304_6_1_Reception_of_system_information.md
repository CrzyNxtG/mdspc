## 6.1 Reception of system information

The NAS is informed if the cell selection and reselection results in
changes in the received NAS system information.

The UE shall monitor the Paging Occasions (POs) as described in clause
7.1 to receive System Information change notifications in RRC_IDLE and
RRC_INACTIVE. The changes in the system information are notified by the
network using a Short Message as specified in TS 38.331 \[3\]. When the
Short Message notifies system information changes, then the UE shall
acquire or re-acquire the concerned system information as specified in
TS 38.331 \[3\].

A L2 U2N Remote UE when in RRC_IDLE or RRC_INACTIVE may not monitor POs
as described in clause 7.1 to receive Short Message when connected with
a U2N Relay UE, as specified in TS 38.331 \[3\].

A L2 U2N Remote UE in RRC_IDLE or RRC_INACTIVE does not receive Short
Message from a L2 U2N Relay UE. When receiving a Short Message, the L2
U2N Relay UE may forward to the L2 U2N Remote UE only Public Warning
System information (e.g., *SIB6*, *SIB7*, and *SIB8*).

When system information changes, the L2 U2N Remote UE, when in RRC_IDLE
or RRC_INACTIVE, relies on the U2N L2 Relay UE to acquire or re-acquire
the concerned system information and forward them. Further, the L2 U2N
Remote UE, when in RRC_CONNECTED, relies on the network to receive
concerned system information that has changed.