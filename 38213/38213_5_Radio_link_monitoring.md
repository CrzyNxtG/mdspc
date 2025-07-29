# 5 Radio link monitoring

The downlink radio link quality of the primary cell is monitored by a UE
for the purpose of indicating out-of-sync/in-sync status to higher
layers. The UE is not required to monitor the downlink radio link
quality in DL BWPs other than the active DL BWP, as described in clause
12, on the primary cell unless the UE indicates a capability
*bwpOperationMeasWithoutInterrupt* \[18, TS 38.306\]. If the active DL
BWP is the initial DL BWP and for SS/PBCH block and CORESET multiplexing
pattern 2 or 3, as described in clause 13, the UE is expected to perform
RLM using the associated SS/PBCH block when the associated SS/PBCH block
index is provided by *RadioLinkMonitoringRS*.

If the UE is configured with a SCG, as described in \[12, TS 38.331\],
and the parameter *rlf-TimersAndConstants* is provided by higher layers
and is not set to release, the downlink radio link quality of the PSCell
of the SCG is monitored by the UE for the purpose of indicating
out-of-sync/in-sync status to higher layers. The UE is not required to
monitor the downlink radio link quality in DL BWPs other than the active
DL BWP on the PSCell unless the UE indicates a capability
*bwpOperationMeasWithoutInterrupt* \[18, TS 38.306\].

A UE can be configured for each DL BWP of a SpCell \[11, TS 38.321\]
with a set of resource indexes, through a corresponding set of
*RadioLinkMonitoringRS*, for radio link monitoring by
*failureDetectionResources*. The UE is provided either a CSI-RS resource
configuration index, by *csi-RS-Index*, or a SS/PBCH block index, by
*ssb-Index*. The UE can be configured with up to $N_{LR - RLM}$
*RadioLinkMonitoringRS* for link recovery procedures, as described in
clause 6, and for radio link monitoring. From the $N_{LR - RLM}$
*RadioLinkMonitoringRS*, up to $N_{RLM}$ *RadioLinkMonitoringRS* can be
used for radio link monitoring depending on $L_{\max}\ $ as described in
Table 5-1, wherein $L_{\max}$ is as defined in clause 4.1, and up to two
*RadioLinkMonitoringRS* can be used for link recovery procedures.

For operation with shared spectrum channel access, when a UE is provided
a SS/PBCH block index by *ssb-Index*, the UE is expected to perform
radio link monitoring using SS/PBCH block(s) in the discovery burst
transmission window as described in clause 4.1, where the SS/PBCH
block(s) have candidate SS/PBCH block index(es) corresponding to SS/PBCH
block index provided by *ssb-Index*.

If the UE is not provided *RadioLinkMonitoringRS* and the UE is provided
for PDCCH receptions TCI states that include one or more of a CSI-RS

\- the UE uses for radio link monitoring the RS provided for the active
TCI state for PDCCH reception if the active TCI state for PDCCH
reception includes only one RS

\- if the active TCI state for PDCCH reception includes two RS, the UE
expects that one RS is configured with *qcl-Type* set to \'typeD\' \[6,
TS 38.214\] and the UE uses the RS configured with *qcl-Type* set to
\'typeD\' for radio link monitoring; the UE does not expect both RS to
be configured with *qcl-Type* set to \'typeD\'

\- the UE is not required to use for radio link monitoring an aperiodic
or semi-persistent RS

\- For $L_{\max} = 4$, the UE selects the $N_{RLM}$ RS provided for
active TCI states for PDCCH receptions in CORESETs associated with the
search space sets in an order from the shortest monitoring periodicity.
If more than one CORESETs are associated with search space sets having
same monitoring periodicity, the UE determines the order of the CORESET
from the highest CORESET index as described in clause 10.1.

A UE does not expect to use more than $N_{RLM}$ *RadioLinkMonitoringRS*
for radio link monitoring when the UE is not provided
*RadioLinkMonitoringRS*.

Values of $N_{LR - RLM}$ and $N_{RLM}$ for different values of
$L_{\max}$ are given in Table 5-1.

Table 5-1: ![](media/image12.wmf){width="0.5104166666666666in"
height="0.19791666666666666in"} and $\mathbf{N}_{\mathbf{RLM}}$ as a
function of maximum number $\mathbf{L}_{\mathbf{\max}}$ of SS/PBCH
blocks per half frame

  -----------------------------------------------------------------------------------------------------
  $$\mathbf{L}_{\mathbf{\max}}$$   $$\mathbf{N}_{\mathbf{LR - RLM}}$$   $$\mathbf{N}_{\mathbf{RLM}}$$
  -------------------------------- ------------------------------------ -------------------------------
  4                                2                                    2

  8                                6                                    4

  64                               8                                    8
  -----------------------------------------------------------------------------------------------------

For a CSI-RS resource configuration, *powerControlOffsetSS* is not
applicable and a UE expects to be provided only \'noCDM\' from
*cdm-Type,* only \'one\' and \'three\' from *density*, and only \'1
port\' from *nrofPorts* \[6, TS 38.214\].

If a UE is configured with multiple DL BWPs for a serving cell, the UE
performs RLM using the RS(s) corresponding to resource indexes provided
by *RadioLinkMonitoringRS* for the active DL BWP or, if
*RadioLinkMonitoringRS* is not provided for the active DL BWP, using the
RS(s) provided for the active TCI state for PDCCH receptions in CORESETs
on the active DL BWP.

In non-DRX mode operation, the physical layer in the UE assesses once
per indication period the radio link quality, evaluated over the
previous time period defined in \[10, TS 38.133\] against thresholds
(Q~out~ and Q~in~) configured by *rlmInSyncOutOfSyncThreshold*. The UE
determines the indication period as the maximum between the shortest
periodicity for radio link monitoring resources and 10 msec.

In DRX mode operation, the physical layer in the UE assesses once per
indication period the radio link quality, evaluated over the previous
time period defined in \[10, TS 38.133\], against thresholds (Q~out~ and
Q~in~) provided by *rlmInSyncOutOfSyncThreshold*. The UE determines the
indication period as the maximum between the shortest periodicity for
radio link monitoring resources and the DRX period.

The physical layer in the UE indicates, in frames where the radio link
quality is assessed, out-of-sync to higher layers when the radio link
quality is worse than the threshold Q~out~ for all resources in the set
of resources for radio link monitoring. When the radio link quality is
better than the threshold Q~in~ for any resource in the set of resources
for radio link monitoring, the physical layer in the UE indicates, in
frames where the radio link quality is assessed, in-sync to higher
layers.