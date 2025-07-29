## 20.3 UE notification on Network Switching

For MUSIM operation, a MUSIM device in RRC_CONNECTED state in Network A
may have to switch from Network A to Network B. Network A is NR and
Network B can either be E-UTRA or NR. Before switching from Network A, a
MUSIM device should notify Network A to either leave RRC_CONNECTED
state, or be kept in RRC_CONNECTED state in Network A while temporarily
switching to Network B.

When configured to do so, a MUSIM device can signal to the Network A a
preference to leave RRC_CONNECTED state by using RRC (see TS 38.331
\[12\]) or NAS signalling (see TS 23.501 \[3\]). After sending a
preference to leave RRC_CONNECTED state by using RRC signalling, if the
MUSIM device does not receive an *RRCRelease* message from the Network A
within a certain time period (configured by the Network A, see TS 38.331
\[12\]), the MUSIM device can enter RRC_IDLE state in Network A.

When configured to do so, a MUSIM device can signal to the Network A a
preference to be temporarily switching to Network B while remaining in
RRC_CONNECTED state in Network A. This is indicated by scheduling gaps
preference. This preference can include information for setup or release
of gap(s). The Network A can configure at most 4 gap patterns for MUSIM
purpose: three periodic gaps and a single aperiodic gap. The Network A
should always provide at least one of the requested gap pattern or no
gaps. Network providing an alternative gap pattern instead of the one
requested by the UE is not supported in this release.

When configured to do so, a MUSIM device can include priority of
periodic gap(s) in addition to scheduling gaps preference, and the
priority preference should be indicated for all periodic gap(s). If the
MUSIM device indicates gap priority preference, it can also indicate its
preference on using *keep solution* (defined in TS 38.133 \[13\]).