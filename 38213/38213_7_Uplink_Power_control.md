# 7 Uplink Power control

Uplink power control determines a power for PUSCH, PUCCH, SRS, and PRACH
transmissions.

A UE does not expect to simultaneously maintain more than four pathloss
estimates per serving cell for all PUSCH/PUCCH/SRS transmissions as
described in clauses 7.1.1, 7.2.1, and 7.3.1, except for SRS
transmissions configured by *SRS-PosResourceSet* as described in clause
7.3.1. If the UE is provided a number of RS resources for pathloss
estimation for PUSCH/PUCCH/SRS transmissions that is larger than 4, the
UE maintains for pathloss estimation RS resources corresponding to RS
resource indexes $q_{d}$ as described in clauses 7.1.1, 7.2.1, and
7.3.1. If an RS resource updated by MAC CE, as described in clauses
7.1.1, 7.2.1 and 7.3.1, is one from the RS resources the UE maintains
for pathloss estimation for PUSCH/PUCCH/SRS transmissions, the UE
applies the pathloss estimation based on the RS resources starting from
the first slot that is after slot
$k + 3 \bullet N_{slot}^{subframe,\ \ \mu} + {2^{\mu} \bullet k}_{mac}$
where $k$ is the slot where the UE would transmit a PUCCH or PUSCH with
HARQ-ACK information for the PDSCH providing the MAC CE, $\mu\ \ $is the
SCS configuration for the PUCCH or PUSCH, respectively, that is
determined in the slot when the MAC CE command is applied and $k_{mac}$
is a number of slots for SCS configuration $\mu = 0$ provided by *kmac*
or $k_{mac} = 0$ if *kmac* is not provided*.*

A PUSCH/PUCCH/SRS/PRACH transmission occasion $i$ is defined by a slot
index $n_{s,f}^{\mu}$ within a frame with system frame number $SFN$, a
first symbol $S$ within the slot, and a number of consecutive symbols
$L$. For a PUSCH transmission with repetition Type B, a PUSCH
transmission occasion is a nominal repetition \[6, TS 38.214\].

In the remaining of this clause, if a UE is provided *TCI-State* in
*dl-OrJointTCI-StateList* or *TCI-UL-State* or *CandidateTCI-State* or
*CandidateTCI-UL-State* indicated in the LTM Cell Switch Command MAC
CE*,* and for each indicated one or two *TCI-State* or *TCI-UL-State* or
*CandidateTCI-State* or *CandidateTCI-UL-State* of a PUSCH, PUCCH, or
SRS transmission occasion as described in \[6, TS 38.214\]

\- in clauses 7.1.1, 7.2.1, and 7.3.1, the RS index $q_{d}$ for
obtaining the downlink pathloss estimate for PUSCH, PUCCH, and SRS
transmission is provided by *pathlossReferenceRS-Id-r17* associated with
or included in the indicated *TCI-State* or *TCI-UL-State* except for
SRS transmission that is not provided *followUnifiedTCI-StateSRS,* or by
*pathlossReferenceRS-Id* included in *CandidateTCI-State* or
*CandidateTCI-UL-State* indicated in the LTM Cell Switch Command MAC CE

\- in clause 7.1.1, if *p0AlphaSetforPUSCH* is provided, the values of
$P_{\text{O\_UE\_PUSCH},b,f,c}(j)$, $\alpha_{b,f,c}(j)$, and the PUSCH
power control adjustment state $l$ are provided by *p0AlphaSetforPUSCH*
associated with the indicated *TCI-State* or *TCI-UL-State*, or by
*p0AlphaSetforPUSCH* associated with the *CandidateTCI-State* or
*CandidateTCI-UL-State* indicated in the LTM Cell Switch Command MAC CE

\- in clause 7.2.1, if *p0AlphaSetforPUCCH* is provided, the values of
$P_{\text{O\_UE\_PUCCH}}\left( q_{u} \right)$ and the PUCCH power
control adjustment state $l$ are provided by *p0AlphaSetforPUCCH*
associated with the indicated *TCI-State* or *TCI-UL-State*, or by
*p0AlphaSetforPUCCH* associated with the *CandidateTCI-State* or
*CandidateTCI-UL-State* indicated in the LTM Cell Switch Command MAC CE

\- in clause 7.3.1, if *p0AlphaSetforSRS* is provided,

\- if *followUnifiedTCI-StateSRS* is provided for a SRS resource set,
the values of $P_{\text{O\_UE\_SRS},b,f,c}\left( q_{s} \right)$,
$\alpha_{SRS,b,f,c}\left( q_{s} \right)$, and SRS power control
adjustment state $l$ are provided by *p0AlphaSetforSRS* associated with
the indicated *TCI-State* or *TCI-UL-State*, or by *p0AlphaSetforSRS*
associated with the *CandidateTCI-State* or *CandidateTCI-UL-State*
indicated in the LTM Cell Switch Command MAC CE

\- else, if *followUnifiedTCI-StateSRS* is not provided for a SRS
resource set and for a SRS resource from the SRS resource set, the
values of $P_{\text{O\_UE\_SRS},b,f,c}\left( q_{s} \right)$,
$\alpha_{SRS,b,f,c}\left( q_{s} \right)$, and SRS power control
adjustment state $l$ are provided by *p0AlphaSetforSRS* associated with
*TCI-State* or *TCI-UL-State* of an SRS resource with lowest
*SRS-ResourceId* in the SRS resource set and a RS index $q_{d}$ for
obtaining a pathloss estimate for the SRS transmission is provided by
*pathlossReferenceRS-Id-r17* associated with or included in the
*TCI-State* or *TCI-UL-State* of an SRS resource with lowest
*SRS-ResourceId* in the SRS resource set

$P_{\text{O\_SRS},b,f,c}\left( q_{s} \right)$ is the sum of the
component $P_{\text{O\_UE\_SRS},b,f,c}\left( q_{s} \right)$ and a
component *p0* provided by *SRS-ResourceSet* corresponding to the SRS
resource set.

In the remaining of this clause, if a PDCCH reception by a UE includes
two PDCCH candidates from corresponding search space sets, as described
in clause 10.1

\- a PDCCH monitoring occasion is the union of the PDCCH monitoring
occasions for the two PDCCH candidates

\- the end of the PDCCH reception is the end of the PDCCH candidate that
ends later

The PDCCH reception includes the two PDCCH candidates also when the UE
is not required to monitor one of the two PDCCH candidates as described
in clauses 10 (except clause 10.4), 11.1, 11.1.1 and 17.2.