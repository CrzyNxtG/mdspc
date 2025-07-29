## 7.9 UE Assistance Information

When configured to do so, the UE can signal the network through
*UEAssistanceInformation*:

\- If it prefers an adjustment in the connected mode DRX cycle length,
for the purpose of delay budget reporting;

\- If it is experiencing internal overheating;

\- If it prefers certain DRX parameter values, and/or a reduced maximum
number of secondary component carriers, and/or a reduced maximum
aggregated bandwidth and/or a reduced maximum number of MIMO layers
and/or minimum scheduling offsets K0 and K2 for power saving purpose;

\- If it expects not to send or receive any more data in the near
future, and in this case, it can provide its preference to transition
out of RRC_CONNECTED where this indication may express its preferred RRC
state, or alternately, it may cancel an earlier indicated preference to
transition out of RRC_CONNECTED;

\- If it prefers (not) to be provisioned with reference time
information;

\- If it prefers to transition out of RRC_CONNECTED state for MUSIM
operation and its preferred RRC state after transition;

\- If it wants to include assistance information for setup or release of
MUSIM gaps, and/or for setup the priority of periodic MUSIM gaps, and/or
for keeping the colliding MUSIM gaps;

\- If it prefers to restrict UE capability temporarily or remove the
restriction for MUSIM operation;

\- When affected by IDC problems that it cannot solve by itself:

\- The list of frequencies affected by IDC problems (see clause 23.4 of
TS 36.300 \[2\]);

\- The list of frequency ranges/frequency range combinations affected by
the IDC problems;

\- DRX based TDM assistance information (see clause 23.4.2 of TS 36.300
\[2\]);

\- Its RRM measurement relaxation status indicating whether RRM
measurement relaxation criteria are met or not;

\- Its RLM measurement relaxation status indicating whether the UE is
applying RLM measurements relaxation;

\- Its BFD measurement relaxation status indicating whether the UE is
applying BFD measurements relaxation;

\- If it prefers not operating on multi-Rx (i.e. not supporting
simultaneous reception with different QCL-typeD) for FR2.

NOTE: The requirements on RRM/RLM/CSI measurements in different phases
of IDC interference defined in TS 36.300 \[2\] are applicable except
that for NR serving cell, the requirements in TS 38.133 \[13\] and TS
38.101-1 \[18\], TS 38.101-2 \[35\], TS 38.101-3 \[36\] apply.

In the second case, the UE can express a preference for temporarily
reducing the number of maximum secondary component carriers, the maximum
aggregated bandwidth and the number of maximum MIMO layers. In all
cases, it is up to the gNB whether to accommodate the request.

For sidelink, the UE can report SL traffic pattern(s) to NG-RAN, for
periodic traffic.