### 16.13.3 Identification, access and camping restrictions

A RedCap UE can be identified by the network during Random Access
procedure via MSG3/MSGA from a RedCap specific LCID(s) and optionally
via MSG1/MSGA (PRACH occasion or PRACH preamble). An eRedCap UE can be
identified by the network during Random Access procedure via MSG3/MSGA
from an eRedCap specific LCID(s) and optionally via MSG1. For RedCap UE
identification via MSG1/MSGA, RedCap specific Random Access
configuration may be configured by the network. For eRedCap UE
identification via MSG1, eRedCap specific Random Access configuration
may be configured by the network. For MSG3/MSGA, an (e)RedCap UE is
identified by the dedicated LCID(s) indicated for CCCH identification
(CCCH or CCCH1) regardless whether (e)RedCap specific Random Access
configuration is configured by the network.

(e)RedCap UEs with 1 Rx branch and 2 Rx branches can be allowed
separately via system information. In addition, (e)RedCap UEs in
Half-Duplex FDD mode can be allowed via system information. A RedCap
specific IFRI can be provided in SIB1, when absent, RedCap UEs access is
not allowed. An eRedCap specific IFRI can be provided in SIB1, when
absent, eRedCap UEs access is not allowed. Information on which
frequencies (e)RedCap UE access is allowed can be provided in system
information.

An (e)RedCap UE with 1 Rx branch applies the associated offset for
broadcasted cell specific RSRP thresholds for random access, SDT, cell
edge condition and cell (re)selection criterion as specified in TS
38.133 \[13\].

NOTE: It is up to the E-UTRA network, if possible, to avoid handover
attempts of an (e)RedCap UE to a target NR cell not supporting (e)RedCap
as specified in TS 36.300 \[2\]. It is up to the (e)RedCap UE
implementation, if possible, to recover from handover attempts to a
target NR cell not supporting (e)RedCap.