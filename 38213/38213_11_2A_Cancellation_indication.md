## 11.2A Cancellation indication

If a UE is provided *UplinkCancellation*, the UE is provided, in one or
more serving cells, search space sets for monitoring the first PDCCH
candidate with a CCE aggregation level of $L_{CI}$ CCEs of each search
space set for detection of a DCI format 2_4 \[5, TS 38.212\] with a
CI-RNTI provided by *ci-RNTI* as described in clause 10.1.
*UplinkCancellation* additionally provides to the UE

\- a set of serving cells, by *ci-ConfigurationPerServingCell*, that
includes a set of serving cell indexes and a corresponding set of
locations for fields in DCI format 2_4 by *positionInDCI*

\- a number of fields in DCI format 2_4, by *positionInDCI-forSUL*, for
each serving cell for a SUL carrier, if the serving cell is configured
with a SUL carrier

\- an information payload size for DCI format 2_4 by
*dci-PayloadSize-ForCI*

\- an indication for time-frequency resources by *timeFrequencyRegion*

For a serving cell having an associated field in a DCI format 2_4, for
the field denote by

\- $N_{\text{CI}}$ a number of bits provided by *ci-PayloadSize*

\- $B_{\text{CI}}$ a number of PRBs provided by *frequencyRegionforCI*
in *timeFrequencyRegion*

\- $T_{\text{CI}}$ a number of symbols, excluding symbols for reception
of SS/PBCH blocks and DL symbols indicated by
*tdd-UL-DL-ConfigurationCommon*, from a number of symbols that

\- is provided by *timeDurationforCI* in *timeFrequencyRegion*, if the
PDCCH monitoring periodicity for the search space set with the DCI
format 2_4 is one slot and there are more than one PDCCH monitoring
occasions in a slot, or

\- is equal to the PDCCH monitoring periodicity, otherwise.

\- $G_{\text{CI}}$ a number of partitions for the $T_{\text{CI}}$
symbols provided by *timeGranularityforCI* in *timeFrequencyRegion*

$G_{\text{CI}}$ sets of bits from the MSB of the $N_{\text{CI}}$ bits
have a one-to-one mapping with $G_{\text{CI}}$ groups of symbols where
each of the first
$G_{\text{CI}} - T_{\text{CI}} + \left\lfloor \frac{T_{\text{CI}}}{G_{\text{CI}}} \right\rfloor \cdot G_{\text{CI}}$
groups includes
$\left\lfloor \frac{T_{CI}}{G_{\text{CI}}} \right\rfloor$ symbols and
each of the remaining
$T_{\text{CI}} - \left\lfloor \frac{T_{\text{CI}}}{G_{\text{CI}}} \right\rfloor \cdot G_{\text{CI}}$
groups includes
$\left\lceil \frac{T_{\text{CI}}}{G_{\text{CI}}} \right\rceil$ symbols.
A UE determines a symbol duration with respect to a SCS configuration of
an active DL BWP where the UE monitors PDCCH for DCI format 2_4
detection.

For a group of symbols, $N_{BI} = \frac{N_{CI}}{G_{CI}}$ bits from MSB
of each set of bits have a one-to-one mapping with $N_{\text{BI}}$
groups of PRBs where each of the first
$N_{\text{BI}} - B_{\text{CI}} + \left\lfloor \frac{B_{\text{CI}}}{N_{\text{BI}}} \right\rfloor \cdot N_{\text{BI}}$
groups includes
$\left\lfloor \frac{B_{\text{CI}}}{N_{\text{BI}}} \right\rfloor$ PRBs
and each of the remaining
$B_{\text{CI}} - \left\lfloor \frac{B_{\text{CI}}}{N_{\text{BI}}} \right\rfloor \cdot N_{\text{BI}}$
groups includes
$\left\lceil \frac{B_{\text{CI}}}{N_{\text{BI}}} \right\rceil$ PRBs. A
UE determines a first PRB index as
${N_{RFR}^{start} = O}_{\text{carrier}} + {RB}_{start}$ and a number of
contiguous RBs as ${B_{CI} = L}_{RB}\ $ from *frequencyRegionforCI* that
indicates an offset ${RB}_{start}$ and a length $L_{\text{RB}}$ as RIV
according to \[6, TS 38.214\], and from *offsetToCarrier* in
*FrequencyInfoUL-SIB* or *FrequencyInfoUL* that indicates
$O_{\text{carrier}}$ for a SCS configuration of an active DL BWP where
the UE monitors PDCCH for DCI format 2_4 detection.

An indication by a DCI format 2_4 for a serving cell is applicable to a
PUSCH transmission or an SRS transmission on the serving cell. If the
PUSCH transmission or the SRS transmission is scheduled by a DCI format,
the indication by the DCI format 2_4 is applicable to the PUSCH
transmission or SRS transmission only if the last symbol of the PDCCH
reception providing the DCI format is earlier than the first symbol of
the PDCCH reception providing the DCI format 2_4.

For the serving cell, the UE determines the first symbol of the $T_{CI}$
symbols to be the first symbol that is after ${T'}_{proc,2}$ from the
end of a PDCCH reception where the UE detects the DCI format 2_4, where
${T'}_{proc,2}$ is obtained from $T_{proc,2}$ for PUSCH processing
capability 2 \[6, TS 38.214\] assuming
$d_{2,1} = d_{offset} \cdot \frac{2^{- \mu_{UL}}}{2^{- \mu}}$ where
$d_{offset}$ is provided by *delta_Offset*, $\mu$ being the smallest SCS
configuration between the SCS configuration of the PDCCH and the
smallest SCS configuration $\mu_{UL}$ provided in
*scs-SpecificCarrierList* of *FrequencyInfoUL* or *FrequencyInfoUL-SIB*.
The UE does not expect to cancel the PUSCH transmission or the SRS
transmission before a corresponding symbol that is $T_{proc,2}$ assuming
that $d_{2,1} = 0$ after a last symbol of the PDCCH reception where the
UE detects the DCI format 2_4.

A UE that detects a DCI format 2_4 for a serving cell cancels a PUSCH
transmission or an actual repetition of a PUSCH transmission \[6, TS
38.214\] if the PUSCH transmission is with repetition Type B, as
determined in clauses 9 and 9.2.5 or in clause 6.1 of \[6, TS 38.214\],
or an SRS transmission on the serving cell if, respectively,

\- the transmission is PUSCH with priority 0, if the UE is provided
*uplinkCancellationPriority*,

\- a group of symbols, from the $T_{\text{CI}}$ symbols, has at least
one bit value of \'1\' in the corresponding set of $N_{BI}$ bits in the
DCI format 2_4 and includes a symbol of the (repetition of the) PUSCH
transmission or of the SRS transmission, and

\- a group of PRBs, from the $B_{\text{CI}}$ PRBs, has a corresponding
bit value of \'1\' in the set of bits corresponding to the group of
symbols in the DCI format 2_4 and includes a PRB of the (repetition of
the) PUSCH transmission or of the SRS transmission,

where

\- the cancellation of the (repetition of the) PUSCH transmission
includes all symbols from the earliest symbol of the (repetition of the)
PUSCH transmission that is in a group of symbols having corresponding
bit values of \'1\' in the DCI format 2_4;

\- the cancellation of the SRS transmission includes only symbols that
are in one or more groups of symbols having corresponding bit values of
\'1\' in the DCI format 2_4.

If, based on an indication by a DCI format 2_4, a UE cancels a PUSCH
transmission or an SRS transmission, the UE does not expect to be
scheduled by a second DCI format to transmit a PUSCH or an SRS over
symbols that include symbols of the cancelled PUSCH transmission or SRS
transmission, where the last symbol of the PDCCH reception providing the
second DCI format is no earlier than the first symbol of the PDCCH
reception providing the DCI format 2_4.