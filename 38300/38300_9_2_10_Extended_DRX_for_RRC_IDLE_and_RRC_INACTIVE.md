### 9.2.10 Extended DRX for RRC_IDLE and RRC_INACTIVE

When extended DRX (eDRX) is used, the following applies:

\- For RRC_INACTIVE, eDRX configuration for RAN paging is decided and
configured by NG-RAN. In RRC_INACTIVE the UE monitors both RAN and CN
paging;

\- For RRC_IDLE, eDRX for CN paging is configured by upper layers. In
RRC_IDLE the UE monitors only CN paging;

\- Information on whether eDRX for CN paging and RAN paging is allowed
on the cell is provided separately in system information;

\- The maximum value of the eDRX cycle is 10485.76 seconds (2.91 hours)
while the minimum value of the eDRX cycle is 2.56 seconds;

\- The hyper SFN (H-SFN) is broadcast by the cell and increments by one
when the SFN wraps around;

\- Paging Hyperframe (PH) refers to the H-SFN in which the UE starts
monitoring paging according to DRX during a Paging Time Window (PTW).
The PH and PTW are determined based on a formula (see TS 38.304 \[10\])
that is known by the AMF, UE and NG-RAN;

\- H-SFN, PH and PTW are used if the eDRX cycle is greater than 10.24
seconds;

\- When the RRC_IDLE eDRX cycle is longer than the system information
modification period, the UE verifies that stored system information
remains valid before resuming/establishing an RRC connection.

NOTE: If emergency PDU session resources are established, the gNB should
not configure the Extended DRX when sending the UE to RRC_INACTIVE
state. The gNB recognizes the emergency PDU session resources based on
special ARP value of a QoS flow as specified in TS 23.501 \[3\].