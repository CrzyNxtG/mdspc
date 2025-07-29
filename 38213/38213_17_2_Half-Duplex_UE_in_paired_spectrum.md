## 17.2 Half-Duplex UE in paired spectrum

A half-duplex UE (HD-UE) in paired spectrum is not capable of
simultaneous transmissions and receptions on a serving cell with paired
spectrum. This clause is applicable for communication of a HD-UE on a
serving cell with paired spectrum. Procedures for a HD-UE are same as
described for a UE in all other clauses of this document unless stated
otherwise.

A HD-UE does not expect to detect a DCI format scheduling a reception in
a set of symbols and detect a DCI format scheduling a transmission in
any symbol from the set of symbols.

When a PDCCH reception by a UE includes two PDCCH candidates from
corresponding search space sets, as described in clause 10.1, the end of
the PDCCH reception is the end of the PDCCH candidate that ends later.

If a HD-UE is configured by higher layers to receive a PDCCH, or PDSCH,
or CSI-RS, or DL PRS in a set of symbols, the HD-UE receives the PDCCH,
or PDSCH, or CSI-RS, or DL PRS if the HD-UE does not detect a DCI format
that indicates to the HD-UE to transmit a PUSCH, or PUCCH, or PRACH, or
SRS in at least one symbol of the set of symbols; otherwise, the HD-UE
does not receive the PDCCH, or PDSCH, or CSI-RS, or DL PRS in the set of
symbols.

If a HD-UE is configured by higher layers to transmit SRS, or PUCCH, or
PUSCH in a set of symbols and the UE detects a DCI format indicating to
the HD-UE to receive CSI-RS or PDSCH in a subset of symbols from the set
of symbols, then

\- the HD-UE does not expect to cancel the transmission of the PUCCH or
PUSCH in the set of symbols if the first symbol in the set occurs within
$T_{proc,2\ }$ relative to a last symbol of a PDCCH reception where the
HD-UE detects the DCI format; otherwise, the HD-UE cancels the PUCCH, or
the PUSCH, or an actual repetition of the PUSCH \[6, TS 38.214\],
determined from clauses 9 and 9.2.5 or clause 6.1 of \[6, TS 38.214\].

\- the HD-UE does not expect to cancel the transmission of SRS in
symbols from the subset of symbols that occur within $T_{proc,2}$
relative to a last symbol of a PDCCH reception where the HD-UE detects
the DCI format. The HD-UE cancels the SRS transmission in remaining
symbols from the subset of symbols.

$T_{proc,2}$ is the PUSCH preparation time for UE processing capability
1 \[6, TS 38.214\] assuming $d_{2,1} = 1$ and $\mu$ corresponds to the
smallest SCS configuration between the SCS configuration of the PDCCH
carrying the DCI format and the SCS configuration of the SRS, PUCCH,
PUSCH.

A HD-UE does not expect to receive both dedicated higher layer
parameters configuring transmission in a set of symbols and dedicated
higher layer parameters configuring reception in the set of symbols. A
HD-UE does not expect to receive both a Type-0/0A/0B/1/2-PDCCH CSS set
configuration for PDCCH reception in a set of symbols and dedicated
higher layer parameters configuring transmission in the set of symbols,
except a Type-2-PDCCH CSS set configuration for PDCCH reception in a set
of symbols and dedicated higher layer parameters configuring
configured-grant based PUSCH transmission as described in clause 19.1 in
the set of symbols for which case the UE follows the procedure as in
clause 5.1B.2.6 in \[10, TS 38.133\]. The UE expects to be configured
with a Type-2-PDCCH CSS set configuration for PDCCH reception such that
there is at least one paging occasion that does not overlap with
configured-grant based PUSCH transmission as described in clause 19.1
per SI modification period.

If a HD-UE would transmit a PUSCH, or PUCCH, or SRS based on a
configuration by higher layers and the HD-UE is indicated presence of
SS/PBCH blocks within the active DL BWP by *ssb-PositionsInBurst* in
*SIB1* or in *ServingCellConfigCommon* or by *NonCellDefiningSSB*, the
HD-UE does not transmit

\- PUSCH or PUCCH if a last symbol of the PUSCH or PUCCH transmission
would not be at least $N_{\text{Tx-Rx}} \cdot T_{\text{c}}$ \[4, TS
38.211\] prior to a first symbol of the next earliest SS/PBCH block

\- PUSCH or PUCCH if a first symbol of the PUSCH or PUCCH transmission
would not be at least $N_{\text{Rx-Tx}} \cdot T_{\text{c}}$ \[4, TS
38.211\] after a last symbol of the previous latest SS/PBCH block

\- SRS in symbols that would not be at least
$N_{\text{Tx-Rx}} \cdot T_{\text{c}}$ prior to a first symbol of the
next earliest SS/PBCH block

\- SRS in symbols that would not be at least
$N_{\text{Rx-Tx}} \cdot T_{\text{c}}$ after a last symbol of the
previous latest SS/PBCH block

If a HD-UE would transmit a PRACH based on a detected DCI format, or
PUSCH, or PUCCH, or SRS and the HD-UE is indicated presence of SS/PBCH
blocks within the active DL BWP by *ssb-PositionsInBurst* in *SIB1* or
in *ServingCellConfigCommon* or by *NonCellDefiningSSB* in a set of
symbols, the HD-UE does not transmit PUSCH or PUCCH or PRACH if a
transmission would overlap with any symbol from the set of symbols and
the HD-UE does not transmit SRS in the set of symbols.

If a HD-UE would transmit a PRACH or MsgA PUSCH triggered by higher
layers in a set of symbols and would receive a PDCCH, or a PDSCH, or a
CSI-RS, or a DL PRS, or is indicated presence of SS/PBCH blocks within
the active DL BWP by *ssb-PositionsInBurst* in *SIB1* or in
*ServingCellConfigCommon* or by *NonCellDefiningSSB* in symbols that
include any symbol from the set of symbols, the HD-UE can select based
on its implementation whether to either transmit the PRACH or the MsgA
PUSCH or receive the PDSCH, or the CSI-RS, or the PL RS, or the PDCCH,
or the SS/PBCH blocks.

If a HD-UE would receive a PDCCH, or a PDSCH, or a CSI-RS, or a DL PRS
based on a configuration by higher layers or is indicated presence of
SS/PBCH blocks within the active DL BWP by *ssb-PositionsInBurst* in
*SIB1* or in *ServingCellConfigCommon* or by *NonCellDefiningSSB* in a
set of symbols, and the HD-UE would transmit PRACH or MsgA PUSCH
triggered by higher layers starting or ending at a symbol that is
earlier or later than $N_{\text{Rx-Tx}} \cdot T_{\text{c}}$ or
$N_{\text{Tx-Rx}} \cdot T_{\text{c}}$, respectively, from the last or
first symbol in the set of symbols, the HD-UE can select based on its
implementation whether to either transmit the PRACH or the MsgA PUSCH or
receive the PDSCH, or the CSI-RS, or the DL PRS, or the PDCCH, or the
SS/PBCH blocks.