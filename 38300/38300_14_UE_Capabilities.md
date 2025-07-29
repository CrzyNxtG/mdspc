# 14 UE Capabilities

The UE capabilities in NR rely on a hierarchical structure where each
capability parameter is defined per UE, per duplex mode (FDD/TDD), per
frequency range (FR1/FR2), per band, per band combinations, ... as the
UE may support different functionalities depending on those (see TS
38.306 \[11\]).

NOTE 1: Some capability parameters are always defined per UE (e.g. SDAP,
PDCP and RLC parameters) while some other not always (e.g. MAC and
Physical Layer Parameters).

The UE capabilities in NR do not rely on UE categories: UE categories
associated to fixed peak data rates are only defined for marketing
purposes and not signalled to the network. Instead, the peak data rate
for a given set of aggregated carriers in a band or band combination is
the sum of the peak data rates of each individual carrier in that band
or band combination, where the peak data rate of each individual carrier
is computed according to the capabilities supported for that carrier in
the corresponding band or band combination.

For each block of contiguous serving cells in a band, the set of
features supported thereon is defined in a Feature Set (FS). The UE may
indicate several Feature Sets for a band (also known as feature sets per
band) to advertise different alternative features for the associated
block of contiguous serving cells in that band. The two-dimensional
matrix of feature sets for all the bands of a band combination (i.e. all
the feature sets per band) is referred to as a feature set combination.
In a feature set combination, the number of feature sets per band is
equal to the number of band entries in the corresponding band
combination, and all feature sets per band have the same number of
feature sets. Each band combination is linked to one feature set
combination. This is depicted on Figure 14-1 below:

![](media/image62.emf)

Figure 14-1: Feature Set Combinations

In addition, for some features in intra-band contiguous CA, the UE
reports its capabilities individually per carrier. Those capability
parameters are sent in feature set per component carrier and they are
signalled in the corresponding FSs (per Band) i.e. for the corresponding
block of contiguous serving cells in a band. The capability applied to
each individual carrier in a block is agnostic to the order in which
they are signalled in the corresponding FS.

NOTE 2: For intra-band non-contiguous CA, there are as many feature sets
per band signalled as the number of (groups of contiguous) carriers that
the UE is able to aggregate non-contiguously in the corresponding band.

To limit signalling overhead, the gNB can request the UE to provide NR
capabilities for a restricted set of bands. When responding, the UE can
skip a subset of the requested band combinations according to the UE
capability fallback behaviour as specified in TS 38.306 \[11\] and in TS
38.331 \[12\]. An eRedCap UE may ignore UE capability filtering and send
all supported bands in the mirrored UE capability filter with an
explicit indication on whether the filter was ignored or not.

If supported by the UE and the network, the UE may provide an ID in NAS
signalling that represents its radio capabilities for one or more RATs
in order to reduce signalling overhead. The ID may be assigned either by
the manufacturer or by the serving PLMN. The manufacturer-assigned ID
corresponds to a pre-provisioned set of capabilities. In the case of the
PLMN-assigned ID, assignment takes place in NAS signalling.

The AMF stores the UE Radio Capability uploaded by the gNB as specified
in TS 23.501 \[3\].

The gNB can request the UE capabilities for RAT-Types NR, EUTRA,
UTRA-FDD. The UTRAN capabilities, i.e. the INTER RAT HANDOVER INFO,
include START-CS, START-PS and \"predefined configurations\", which are
\"dynamic\" IEs. In order to avoid the START values desynchronisation
and the key replaying issue, the gNB always requests the UE UTRA-FDD
capabilities before handover to UTRA-FDD. The gNB does not upload the UE
UTRA-FDD capabilities to the AMF.