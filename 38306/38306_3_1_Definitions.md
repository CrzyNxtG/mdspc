## 3.1 Definitions

For the purposes of the present document, the terms and definitions
given in TR 21.905 \[1\] and the following apply. A term defined in the
present document takes precedence over the definition of the same term,
if any, in TR 21.905 \[1\].

**eRedCap UE:** a UE with enhanced reduced capabilities as specified in
clause 4.2.22.1.

**Fallback band combination:** A Uu band combination that would result
from another Uu band combination (parent band combination) by releasing
at least one SCell or uplink configuration of SCell, or SCG, or SUL. A
PC5 band combination that would result from another PC5 band combination
(parent band combination) by releasing at least one sidelink carrier. An
intra-band non-contiguous band combination is not considered to be a
fallback band combination of an intra-band contiguous band combination.
A fallback band combination supports the same channel bandwidth(s) for
each carrier as its parent band combination(s).

**Fallback per band feature set:** A feature set per band that has same
or lower capabilities than the reported capabilities from the reported
feature set per band for a given band.

**Fallback per CC feature set:** A feature set per CC that has same or
lower capabilities than the capabilities of UE (e.g. supported MIMO
layers, BW, modulation order) while keeping the numerology the same from
the reported feature set per CC for a given carrier per band. The
*supportedMinBandwidthDL*/*supportedMinBandwidthUL* defines the lower
bound of the bandwidth supported by the UE.

**RedCap UE:** The UE with reduced capabilities as specified in clause
4.2.21.1.

**SON report(s):** A SON report corresponds to one report from UE such
as Random Access report, Radio Link Failure report, Connection
Establishment Failure report, Mobility History Information report,
Successful Handover report, and Successful PSCell change report.

**Switching SCell (sSCell):** The SCell configured with cross-carrier
scheduling to PCell/PSCell.