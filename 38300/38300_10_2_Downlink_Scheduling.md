## 10.2 Downlink Scheduling

In the downlink, the gNB can dynamically allocate resources to UEs via
the C-RNTI on PDCCH(s). A UE always monitors the PDCCH(s) in order to
find possible assignments when its downlink reception is enabled
(activity governed by DRX and cell DTX when configured). When CA is
configured, the same C-RNTI applies to all serving cells.

The gNB may pre-empt an ongoing PDSCH transmission to one UE with a
latency-critical transmission to another UE. The gNB can configure UEs
to monitor interrupted transmission indications using INT-RNTI on a
PDCCH. If a UE receives the interrupted transmission indication, the UE
may assume that no useful information to that UE was carried by the
resource elements included in the indication, even if some of those
resource elements were already scheduled to this UE.

In addition, with Semi-Persistent Scheduling (SPS), the gNB can allocate
downlink resources for the initial HARQ transmissions to UEs: RRC
defines the periodicity of the configured downlink assignments while
PDCCH addressed to CS-RNTI can either signal and activate the configured
downlink assignment, or deactivate it; i.e. a PDCCH addressed to CS-RNTI
indicates that the downlink assignment can be implicitly reused
according to the periodicity defined by RRC, until deactivated.

NOTE: When required, retransmissions are explicitly scheduled on
PDCCH(s).

The dynamically allocated downlink reception overrides the configured
downlink assignment in the same serving cell, if they overlap in time.
Otherwise a downlink reception according to the configured downlink
assignment is assumed, if activated.

The UE may be configured with up to 8 active configured downlink
assignments for a given BWP of a serving cell. When more than one is
configured:

\- The network decides which of these configured downlink assignments
are active at a time (including all of them); and

\- Each configured downlink assignment is activated separately using a
DCI command and deactivation of configured downlink assignments is done
using a DCI command, which can either deactivate a single configured
downlink assignment or multiple configured downlink assignments jointly.