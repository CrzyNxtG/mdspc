### 9.2.9 Timing Advance

In RRC_CONNECTED, the gNB is responsible for maintaining the timing
advance to keep the L1 synchronised. Serving cells having UL to which
the same timing advance applies and using the same timing reference cell
are grouped in a TAG. Each TAG contains at least one serving cell with
configured uplink, and the mapping of each serving cell to a TAG is
configured by RRC.

For the primary TAG the UE uses the SpCell as timing reference, except
with shared spectrum channel access where an SCell can also be used in
certain cases (see clause 7.1, TS 38.133 \[13\]). In a secondary TAG,
the UE may use any of the activated SCells of this TAG as a timing
reference cell, but should not change it unless necessary.

Timing advance updates are signalled by the gNB to the UE via MAC CE
commands. Such commands restart a TAG-specific timer which indicates
whether the L1 can be synchronised or not: when the timer is running,
the L1 is considered synchronised, otherwise, the L1 is considered
non-synchronised (in which case uplink transmission can only take place
through MSG1/MSGA).

When two TAG IDs are configured for the SpCell, both TAGs are regarded
as primary TAG.