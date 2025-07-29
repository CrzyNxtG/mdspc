### 9.2.6 Random Access Procedure

The random access procedure is triggered by a number of events:

\- Initial access from RRC_IDLE;

\- RRC Connection Re-establishment procedure;

\- DL or UL data arrival, during RRC_CONNECTED or during RRC_INACTIVE
while SDT procedure (see clause 18.0) is ongoing, when UL
synchronisation status is \"non-synchronised\";

\- UL data arrival, during RRC_CONNECTED or during RRC_INACTIVE while
SDT procedure is ongoing, when there are no PUCCH resources for SR
available;

\- Handover, except for when RACH-less HO is configured;

\- SR failure;

\- Explicit request by RRC upon synchronous reconfiguration;

\- RRC Connection Resume procedure from RRC_INACTIVE;

\- To establish time alignment for a primary or a secondary TAG;

\- Request for Other SI (see clause 7.3);

\- Beam failure recovery;

\- Consistent UL LBT failure on SpCell;

\- SDT in RRC_INACTIVE (see clause 18);

\- Positioning purpose during RRC_CONNECTED requiring random access
procedure, e.g., when timing advance is needed for UE positioning;

\- Early UL synchronization with an LTM candidate cell;

\- RACH-based LTM cell switch.

Two types of random access procedure are supported: 4-step RA type with
MSG1 and 2-step RA type with MSGA. Both types of RA procedure support
contention-based random access (CBRA) and contention-free random access
(CFRA) as shown on Figure 9.2.6-1 below.

The UE selects the type of random access at initiation of the random
access procedure based on network configuration:

\- when CFRA resources are not configured, an RSRP threshold is used by
the UE to select between 2-step RA type and 4-step RA type;

\- when CFRA resources for 4-step RA type are configured, UE performs
random access with 4-step RA type;

\- when CFRA resources for 2-step RA type are configured, UE performs
random access with 2-step RA type.

The network does not configure CFRA resources for 4-step and 2-step RA
types at the same time for a Bandwidth Part (BWP). CFRA with 2-step RA
type is only supported for handover.

The MSG1 of the 4-step RA type consists of a preamble on PRACH. After
MSG1 transmission, the UE monitors for a response from the network
within a configured window. For CFRA, dedicated preamble for MSG1
transmission is assigned by the network and upon receiving random access
response from the network, the UE ends the random access procedure as
shown in Figure 9.2.6-1(c). For CBRA, upon reception of the random
access response, the UE sends MSG3 using the UL grant scheduled in the
response and monitors contention resolution as shown in Figure
9.2.6-1(a). If contention resolution is not successful after MSG3
(re)transmission(s), the UE goes back to MSG1 transmission.

The MSGA of the 2-step RA type includes a preamble on PRACH and a
payload on PUSCH. After MSGA transmission, the UE monitors for a
response from the network within a configured window. For CFRA,
dedicated preamble and PUSCH resource are configured for MSGA
transmission and upon receiving the network response, the UE ends the
random access procedure as shown in Figure 9.2.6-1(d). For CBRA, if
contention resolution is successful upon receiving the network response,
the UE ends the random access procedure as shown in Figure 9.2.6-1(b);
while if fallback indication is received in MSGB, the UE performs MSG3
transmission using the UL grant scheduled in the fallback indication and
monitors contention resolution as shown in Figure 9.2.6-2. If contention
resolution is not successful after MSG3 (re)transmission(s), the UE goes
back to MSGA transmission.

If the random access procedure with 2-step RA type is not completed
after a number of MSGA transmissions, the UE can be configured to switch
to CBRA with 4-step RA type.

For the random access procedure towards an LTM candidate cell for early
UL TA acquisition, CFRA triggered by a PDCCH order is used. The UE sends
MSG1 towards the cell without monitoring for a response from it as shown
in Figure 9.2.6-1 (e). To support UE power ramping, the UE may perform
MSG1 retransmission as indicated by the network.

![](media/image53.emf) ![](media/image54.emf)

\(a\) CBRA with 4-step RA type (b) CBRA with 2-step RA type

![](media/image55.emf) ![](media/image56.emf)

\(c\) CFRA with 4-step RA type (d) CFRA with 2-step RA type

![](media/image57.emf)

\(e\) CFRA without network response with 4-step RA type

Figure 9.2.6-1: Random Access Procedures

![](media/image58.emf)

Figure 9.2.6-2: Fallback for CBRA with 2-step RA type

For random access in a cell configured with SUL, the network can
explicitly signal which carrier to use (UL or SUL). Otherwise, the UE
selects the SUL carrier if and only if the measured quality of the DL is
lower than a broadcast threshold. UE performs carrier selection before
selecting between 2-step and 4-step RA type. The RSRP threshold for
selecting between 2-step and 4-step RA type can be configured separately
for UL and SUL. Once started, all uplink transmissions of the random
access procedure remain on the selected carrier.

The network can associate a set of RACH resources with feature(s)
applicable to a Random Access procedure: Network Slicing (see clause
16.3), (e)RedCap (see clause 16.13), SDT (see clause 18), and NR
coverage enhancement (see clause 19). A set of RACH resources associated
with a feature is only valid for random access procedures applicable to
at least that feature; and a set of RACH resources associated with
several features is only valid for random access procedures having at
least all of these features. The UE selects the set(s) of applicable
RACH resources, after uplink carrier (i.e. NUL or SUL) and BWP selection
and before selecting the RA type.

When CA is configured, random access procedure with 2-step RA type is
only performed on SpCell while contention resolution can be
cross-scheduled by the SpCell.

When CA is configured, for random access procedure with 4-step RA type,
the first three steps of CBRA always occur on the SpCell while
contention resolution (step 4) can be cross-scheduled by the SpCell. The
three steps of a CFRA started on the SpCell remain on the SpCell. CFRA
on SCell can only be initiated by the gNB to establish timing advance
for a secondary TAG: the procedure is initiated by the gNB with a PDCCH
order (step 0) that is sent on an activated SCell of the secondary TAG,
preamble transmission (step 1) takes place on the SCell, and Random
Access Response (step 2) takes place on SpCell.

When two TAG IDs are configured for the serving cell, the TAG for which
the TA command is applied is indicated in Random Access Response message
or in MSGB. To establish timing advance for the other PTAG, CFRA is
initiated by the gNB with a PDCCH order.