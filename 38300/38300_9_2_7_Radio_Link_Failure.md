### 9.2.7 Radio Link Failure

In RRC_CONNECTED, the UE performs Radio Link Monitoring (RLM) in the
active BWP based on reference signals (SSB/CSI-RS) and signal quality
thresholds configured by the network. SSB-based RLM is based on the
CD-SSB associated to the initial DL BWP and can be configured for the
initial DL BWP, for DL BWPs containing the CD-SSB associated to the
initial DL BWP, and, if supported, for DL BWPs not containing the CD-SSB
associated to the initial DL BWP. Besides, SSB-based RLM can be also
performed based on a non-cell defining SSB, if configured for the active
DL BWP. RLM can be also performed based on CSI-RS, if configured for the
active DL BWP. In case of DAPS handover, the UE continues the detection
of radio link failure at the source cell until the successful completion
of the random access procedure to the target cell.

The UE declares Radio Link Failure (RLF) when one of the following
criteria are met:

\- Expiry of a radio problem timer started after indication of radio
problems from the physical layer (if radio problems are recovered before
the timer is expired, the UE stops the timer); or

\- Expiry of a timer started upon triggering a measurement report for a
measurement identity for which the timer has been configured while
another radio problem timer is running; or

\- Random access procedure failure; or

\- RLC failure; or

\- Detection of consistent uplink LBT failures for operation with shared
spectrum channel access as described in 5.6.1; or

\- For IAB-MT, the reception of a BH RLF indication received from its
parent node.

After RLF is declared, the UE:

\- stays in RRC_CONNECTED;

\- in case of DAPS handover, for RLF in the source cell:

\- stops any data transmission or reception via the source link and
releases the source link, but maintains the source RRC configuration;

\- if handover failure is then declared at the target cell, the UE:

\- selects a suitable cell and then initiates RRC re-establishment;

\- enters RRC_IDLE if a suitable cell was not found within a certain
time after handover failure was declared.

\- in case of CHO, for RLF in the source cell:

\- selects a suitable cell and if the selected cell is a CHO candidate
and if network configured the UE to try CHO after RLF then the UE
attempts CHO execution once, otherwise re-establishment is performed;

\- enters RRC_IDLE if a suitable cell was not found within a certain
time after RLF was declared.

\- in case of MCG LTM, for RLF in the source cell:

\- selects a suitable cell and if the selected cell is an LTM candidate
cell and if network configured the UE to try LTM after RLF then the UE
attempts RACH-based LTM execution once, otherwise re-establishment is
performed;

\- enters RRC_IDLE if a suitable cell was not found within a certain
time after RLF was declared.

\- otherwise, for RLF in the serving cell or in case of DAPS handover,
for RLF in the target cell before releasing the source cell:

\- selects a suitable cell and then initiates RRC re-establishment;

\- enters RRC_IDLE if a suitable cell was not found within a certain
time after RLF was declared.

When RLF occurs at the IAB BH link, the same mechanisms and procedures
are applied as for the access link. This includes BH RLF detection and
RLF recovery.

The IAB-DU can transmit a BH RLF detection indication to its child nodes
in the following cases:

\- The collocated IAB-MT initiates RRC re-establishment;

\- The collocated IAB-MT is dual-connected, detects BH RLF on a BH link,
and cannot perform UL re-routing for any traffic. This includes the
scenario of an IAB-node operating in EN-DC or NR-DC, which uses only one
link for backhauling and has BH RLF on this BH link;

\- The collocated IAB-MT has received a BH RLF detection indication from
a parent node, and there is no remaining backhaul link that is
unaffected by the BH RLF condition indicated.

Upon reception of the BH RLF detection indication, the child node may
perform local rerouting for upstream traffic, if possible, over an
available BH link.

If the IAB-DU has transmitted a BH RLF detection indication to a child
node due to an RLF condition on the collocated IAB-MT\'s parent link,
and the collocated IAB-MT\'s subsequent RLF recovery is successful, the
IAB-DU may transmit a BH RLF recovery indication to this child node.

If the IAB-DU has transmitted a BH RLF detection indication to a child
node due to the reception of a BH RLF detection indication by the
collocated IAB-MT, and the collocated IAB-MT receives a BH RLF recovery
indication, the IAB-DU may also transmit a BH RLF recovery indication to
this child node.

Upon reception of the BH RLF recovery indication, the child node reverts
the actions triggered by the reception of the previous BH RLF detection
indication.

In case the RRC re-establishment procedure fails, the IAB-node may
transmit a BH RLF indication to its child nodes. The BH RLF detection
indication, BH RLF recovery indication and BH RLF indication are
transmitted as BAP Control PDUs.