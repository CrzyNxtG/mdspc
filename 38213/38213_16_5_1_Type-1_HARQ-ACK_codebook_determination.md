### 16.5.1 Type-1 HARQ-ACK codebook determination

This clause applies if the UE is configured with
*pdsch-HARQ-ACK-Codebook = semi-static*.

If a UE is configured a SL configured grant Type 1, and the UE is
configured a SL configured grant Type 2 or to monitor PDCCH for
detection of DCI format 3_0 with CRC scrambled by SL-RNTI or SL-CS-RNTI,
and the UE is provided a set of slot timing values $K_{1}$ associated
with a SL BWP by *sl-PSFCH-ToPUCCH* and *sl-PSFCH-ToPUCCH-CG-Type1*, the
*sl-PSFCH-ToPUCCH-CG-Type1* is one of *sl-PSFCH-ToPUCCH*.

A UE reports HARQ-ACK information for PSSCH transmissions with
corresponding PSFCH reception occasions in slot $n$ only in a HARQ-ACK
codebook that the UE includes in a PUCCH or PUSCH transmission in slot
$n + k$, where $k$ is a number of slots indicated by the PSFCH-to-HARQ
feedback timing indicator field in a DCI format 3_0 scheduling the PSSCH
transmissions, or by a value of PSFCH-to-HARQ feedback timing indicator
field in a DCI format 3_0 activating a SL configured grant Type-2
transmission, or by a value of *sl-PSFCH-ToPUCCH-CG-Type1* for a SL
configured grant Type-1. If the UE reports HARQ-ACK information for the
PSSCH transmissions with corresponding PSFCH reception occasions in a
slot other than slot $n + k$, the UE sets a value for each corresponding
HARQ-ACK information bit to NACK.

If a UE reports HARQ-ACK information in a PUCCH only for

\- PSFCH reception occasions associated with PSSCH transmissions
scheduled by a DCI format 3_0 with counter SAI field value of 1, or

\- PSFCH reception occasions associated with PSSCH transmissions
corresponding to a SL configured grant

within a set $M_{A}$ of occasions for candidate PSSCH transmissions with
corresponding PSFCH reception occasions as determined in clause
16.5.1.1, the UE determines a HARQ-ACK codebook only for the PSFCH
reception occasion associated with PSSCH transmissions scheduled by DCI
format 3_0 or only for the PSFCH reception occasion associated with
PSSCH transmissions corresponding to a SL configured grant according to
corresponding set $M_{A}$ of occasions, where a value of a counter SAI
in DCI format 3_0 is according to Table 16.5.2.1-1. Otherwise, the
procedures in clause 16.5.1.1 and in clause 16.5.1.2 for a HARQ-ACK
codebook determination apply.