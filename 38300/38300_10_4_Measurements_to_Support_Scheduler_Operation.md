## 10.4 Measurements to Support Scheduler Operation

Measurement reports are required to enable the scheduler to operate in
both uplink and downlink. These include transport volume and
measurements of a UEs radio environment.

Uplink buffer status reports (BSR) are needed to provide support for
QoS-aware packet scheduling. In NR, uplink buffer status reports refer
to the data that is buffered in for a group of logical channels (LCG) in
the UE. Four formats are used for reporting in uplink:

\- A short format to report only one BSR (of one LCG);

\- A flexible long format to report several BSRs (up to all eight LCGs);

\- An extended short format to report one BSR (of one LCG);

\- An extended long format to report several BSRs (up to all 256 LCGs).

NOTE: The Extended versions of the BSR formats can only be used by IAB
nodes.

Uplink buffer status reports are transmitted using MAC signalling. When
a BSR is triggered (e.g. when new data arrives in the transmission
buffers of the UE), a Scheduling Request (SR) can be transmitted by the
UE (e.g. when no resources are available to transmit the BSR).

For IAB, the Pre-emptive BSR can be configured on the backhaul links.
The Pre-emptive BSR is sent based on expected data rather than buffered
data, as described in clause 4.7.3.3.

Power headroom reports (PHR) are needed to provide support for
power-aware packet scheduling. In NR, three types of reporting are
supported: a first one for PUSCH transmission, a second one for PUSCH
and PUCCH transmission in an LTE Cell Group in EN-DC (see TS 37.340
\[21\]) and a third one for SRS transmission on SCells configured with
SRS only. In case of CA, when no transmission takes place on an
activated SCell, a reference power is used to provide a virtual report.
To allow network to detect UL power reduction, the PHR reports may also
contain Power Management Maximum Power Reduction (P-MPR, see TS 38.101-2
\[35\]) information that UE uses to ensure UE compliance with the
Maximum Permissible Exposure (MPE) exposure regulation for FR2, which is
set for limiting RF exposure on human body. Power headroom reports are
transmitted using MAC signalling.