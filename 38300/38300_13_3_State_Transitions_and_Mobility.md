## 13.3 State Transitions and Mobility

As a general principle, on RRC_IDLE to RRC_CONNECTED transitions, RRC
protection keys and UP protection keys are generated while keys for NAS
protection as well as higher layer keys are assumed to be already
available. These higher layer keys may have been established as a result
of an AKA run, or as a result of a transfer from another AMF during
handover or idle mode mobility see TS 23.502 \[22\]).

On RRC_CONNECTED to RRC_IDLE transitions, the gNBs deletes the keys it
stores for that UE such that state information for idle mode UEs only
has to be maintained in AMF. It is also assumed that gNB does no longer
store state information about the corresponding UE and deletes the
current keys from its memory. In particular, on connected to idle
transitions:

\- The gNB and UE delete NH, K~gNB~, K~RRCint~, K~RRCenc~, K~UPint~ and
K~UPenc~ and related NCC;

\- AMF and UE keeps K~AMF~, K~NASint~ and K~NASenc~ stored.

On mobility with vertical key derivation the NH is further bound to the
target PCI and its frequency ARFCN-DL before it is taken into use as the
K~gNB~ in the target gNB. On mobility with horizontal key derivation the
currently active K~gNB~ is further bound to the target PCI and its
frequency ARFCN-DL before it is taken into use as the K~gNB~ in the
target gNB (see clause 13.1). In both cases, ARFCN-DL is the absolute
frequency of CD-SSB of the target PCell.

It is not required to change the AS security algorithms during
intra-gNB-CU handover. If the UE does not receive an indication of new
AS security algorithms during an intra-gNB-CU handover, the UE shall
continue to use the same algorithms as before the handover (see TS
38.331 \[12\]).