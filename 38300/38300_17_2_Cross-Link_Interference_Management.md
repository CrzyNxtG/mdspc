## 17.2 Cross-Link Interference Management

When different TDD DL/UL patterns are used between neighbouring cells,
UL transmission in one cell may interfere with DL reception in another
cell: this is referred to as Cross Link Interference (CLI).

To mitigate CLI, gNBs can exchange and coordinate their intended TDD
DL-UL configurations over Xn and F1 interfaces; and the victim UEs can
be configured to perform CLI measurements. There are two types of CLI
measurements:

\- SRS-RSRP measurement in which the UE measures SRS-RSRP over SRS
resources of aggressor UE(s);

\- CLI-RSSI measurement in which the UE measures the total received
power observed over RSSI resources.

Layer 3 filtering applies to CLI measurement results and both event
triggered and periodic reporting are supported.