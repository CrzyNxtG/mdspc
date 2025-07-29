## 20.4 Temporary UE capability restriction and removal of restriction

For MUSIM operation, a MUSIM device in RRC_CONNECTED state in Network A
may indicate its preference on temporary UE capability restriction or
removal of restriction via UE assistance information with Network A when
the MUSIM device needs transmission or reception in Network B (e.g.,
including start/stop connection to Network B). Network A is NR and
Network B can either be E-UTRA or NR. The MUSIM device may request a
temporary capability restriction only after the Network signals via RRC
that this is allowed.

When configured to do so, a MUSIM device can indicate one or more of the
following temporary capability restriction or removal of restriction to
the Network A:

\- A MUSIM device can explicitly request SCell(s) or SCG to be released;

\- A MUSIM device can indicate its preference on temporary maximum MIMO
layers and/or supported channel bandwidth for specific serving cells for
both UL/DL;

\- A MUSIM device can indicate its preference on the temporary maximum
number of CCs per UL/DL;

\- A MUSIM device can indicate its preference on the concerned band(s)
or band combination(s) (e.g. avoided and/or affected band(s) or band
combination(s)) based on a band-filter list configured by network. For
affected band(s) and band combination(s), this preference can include
temporary maximum MIMO layers and/or supported channel bandwidth for
both UL/DL;

\- A MUSIM device can indicate the measurement gap requirement changes.

When it is allowed by Network A in SIB1, a MUSIM device can indicate in
*RRCSetupComplete/RRCResumeComplete/RRCReestablishmentComplete* message
to the Network A that its capabilities are temporarily restricted due to
ongoing transmission/reception in Network B. This indication allows
Network A to know whether UE capabilities without restrictions can be
used by Network A, or if Network A needs to configure the UE to indicate
its temporary capability restrictions, as described above. When
configured to do so, a MUSIM device can also indicate to the Network A
there is no temporary capability restriction via UE assistance
information.

When a MUSIM device is in RRC_CONNECTED state in both Network A and
Network B, if Network B is NR, it is up to UE implementation to select
which network to request temporary UE capability restriction; if Network
B is E-UTRA, the request for temporary UE capability restriction can
only be performed on Network A.