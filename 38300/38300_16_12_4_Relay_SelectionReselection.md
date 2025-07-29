### 16.12.4 Relay Selection/Reselection

The U2N Remote UE performs radio measurements at PC5 interface and uses
them for U2N Relay selection and reselection along with higher layer
criteria, as specified in TS 23.304 \[48\]. When there is no unicast PC5
connection between the U2N Relay UE and the U2N Remote UE, the U2N
Remote UE uses SD-RSRP measurements to evaluate whether PC5 link quality
towards a U2N Relay UE satisfies relay selection criterion.

For relay reselection, U2N Remote UE uses SL-RSRP measurements towards
the serving U2N Relay UE for relay reselection trigger evaluation when
there is data transmission from U2N Relay UE to U2N Remote UE, and it is
left to UE implementation whether to use SL-RSRP or SD-RSRP for relay
reselection trigger evaluation in case of no data transmission from U2N
Relay UE to U2N Remote UE.

A U2N Relay UE is considered suitable by a U2N Remote UE in terms of
radio criteria if the PC5 link quality measured by U2N Remote UE towards
the U2N Relay UE exceeds configured threshold (pre-configured or
provided by gNB). The U2N Remote UE searches for suitable U2N Relay UE
candidates that meet all AS layer and higher layer criteria (see TS
23.304 \[48\]). If there are multiple such suitable U2N Relay UEs, it is
up to U2N Remote UE implementation to choose one U2N Relay UE among
them. For L2 U2N Relay (re)selection, the PLMN ID and cell ID can be
used as additional AS criteria.

The U2N Remote UE triggers U2N Relay selection in following cases:

\- Direct Uu signal strength of current serving cell of the U2N Remote
UE is below a configured signal strength threshold;

\- Indicated by upper layer of the U2N Remote UE.

The U2N Remote UE may trigger U2N Relay reselection in following cases:

\- PC5 signal strength of current U2N Relay UE is below a
(pre)configured signal strength threshold;

\- Cell reselection, handover, Uu RLF, or Uu RRC connection
establishment/resume failure has been indicated by U2N Relay UE via
PC5-RRC signalling;

\- When U2N Remote UE receives a PC5-S link release message from U2N
Relay UE;

\- When U2N Remote UE detects PC5 RLF;

\- Indicated by upper layer.

For L2 U2N Remote UEs in RRC_IDLE or RRC_INACTIVE and L3 U2N Remote UEs,
the cell (re)selection procedure and relay (re)selection procedure run
independently. If both suitable cells and suitable U2N Relay UEs are
available, it is up to the U2N Remote UE implementation to select either
a cell or a U2N Relay UE. A L3 U2N Remote UE may select a cell and a L3
U2N Relay UE simultaneously and this is up to implementation of L3 U2N
Remote UE.

For both L2 and L3 U2N Relay UEs in RRC_IDLE or RRC_INACTIVE, the
PC5-RRC message(s) are used to inform their connected U2N Remote UE(s)
when U2N Relay UEs select a new cell. The PC5-RRC message(s) are also
used to inform their connected L2 or L3 U2N Remote UE(s) when L2 or L3
U2N Relay UE performs handover, detects Uu RLF, or its Uu RRC connection
establishment/resume fails. Upon reception of the PC5 RRC message for
notification, it is up to U2N Remote UE implementation whether to
release or keep the unicast PC5 link. If U2N Remote UE decides to
release the unicast PC5 link, it triggers the PC5 release procedure and
may perform cell or relay reselection.

The U2U Remote UE performs radio measurements (i.e., SD-RSRP and/or
SL-RSRP) at PC5 interface and uses them for U2U Relay selection and
reselection along with higher layer criteria, as specified in TS 23.304
\[48\].

For relay selection, U2U Remote UE uses SL-RSRP measurements towards the
peer U2U Remote UE for relay selection trigger evaluation when valid
SL-RSRP measurements are available. For relay reselection, U2U Remote UE
uses SL-RSRP measurement towards the U2U Relay UE for relay reselection
trigger evaluation when there is data transmission from U2U Relay UE to
U2U Remote UE. It is left to U2U Remote UE implementation whether to use
SL-RSRP or SD-RSRP for relay selection or reselection trigger evaluation
in case of no data transmission. The thresholds for SD-RSRP and SL-RSRP
can be configured separately for the trigger evaluation of U2U relay
selection or reselection. The same value(s) of the SD-RSRP and SL-RSRP
thresholds, which is used for relay selection or reselection, are
applied for all the discovery models including DCR with integrated
discovery.

The U2U Remote UE may trigger U2U Relay selection in the following
cases:

\- When the SL-RSRP or SD-RSRP between U2U Remote UEs is below a
(pre)configured signal strength threshold;

\- When U2U Remote UE receives an indication to trigger U2U relay
selection from the upper layer of the UE.

The U2U Remote UE may trigger U2U Relay reselection in the following
cases:

\- When the SL-RSRP or SD-RSRP of the current U2U Relay UE is below a
(pre)configured signal strength threshold;

\- When U2U Remote UE receives an indication from the upper layer due to
detecting PC5 RLF;

\- When L2 U2U Remote UE receives an indication from the upper layer due
to receiving the PC5 RLF indication from the L2 U2U Relay UE;

\- When U2U Remote UE receives a PC5-S link release message from U2U
Relay UE;

\- When U2U Remote UE receives an indication to trigger U2U relay
reselection from the upper layer of the UE.

For the discovery model A, the U2U Relay UE should announce via
discovery announcement message only the neighbour U2U Remote UE(s) for
which the SD-RSRP/SL-RSRP between the U2U Relay and the neighbour U2U
Remote UE(s) is above a configured threshold. Upon discovery message
reception, U2U Remote UE considers a U2U Relay UE as a candidate U2U
Relay UE if the SD-RSRP towards the U2U Relay UE is above a configured
threshold and the upper layer criteria are met.

For the discovery model B, when the U2U Relay UE receives the discovery
solicitation message from U2U Remote UE, the U2U Relay UE forwards the
discovery solicitation message only if the SD-RSRP between the U2U Relay
UE and the U2U Remote UE is above a threshold. After the peer U2U remote
UE receives a discovery solicitation message from the U2U Relay UE, the
peer U2U Remote UE transmits the discovery response message only if the
SD-RSRP between the peer U2U Remote UE and the U2U Relay UE is above a
configured threshold. Upon discovery response message reception
forwarded by the U2U Relay UE, the U2U Remote UE considers a U2U Relay
UE as a candidate U2U Relay UE if the SD-RSRP towards the U2U Relay UE
is above a configured threshold and the upper layer criteria are met.

For the DCR message with integrated discovery, when the U2U Relay UE
receives the DCR message with integrated discovery from U2U Remote UE,
the U2U Relay UE forwards the DCR message with integrated discovery only
if the SL-RSRP between the U2U Relay UE and the U2U Remote UE is above a
configured SD-RSRP threshold (not the SL-RSRP, as broadcast is used).
Upon receiving DCR message with integrated discovery from one or
multiple U2U Relay UEs, the peer U2U Remote UE should consider to which
received DCR message to respond amongst candidate U2U Relay UEs towards
which the SL-RSRP is above a configured SD-RSRP threshold (not the
SL-RSRP, as broadcast is used) and that satisfy upper-layer criteria,
and select a U2U Relay UE among them.