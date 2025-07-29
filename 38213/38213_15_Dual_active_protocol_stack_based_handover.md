# 15 Dual active protocol stack based handover

If a UE indicates a capability for dual active protocol stack based
handover (DAPS HO), the UE can be provided with a source MCG and a
target MCG.

If a UE is configured with a target MCG using NR radio access in FR1 or
in FR2 and with a source MCG using NR radio access in FR2 or in FR1,
respectively, the UE performs transmission power control independently
per cell group as described in clauses 7.1 through 7.5.

When a PDCCH reception by a UE includes two PDCCH candidates from
corresponding search space sets, as described in clause 10.1, the end of
the PDCCH reception is the end of the PDCCH candidate that ends later.

If a UE is configured with a target MCG using NR radio access in FR1 and
a source MCG using NR radio access in FR1, the UE is configured a
maximum power $P_{MCG}$ for transmissions on the target MCG by
*p-DAPS-Target* and a maximum power $P_{SCG}$ for transmissions on the
source MCG by *p-DAPS-Source* and with an inter-CG power sharing mode by
*uplinkPowerSharingDAPS-Mode*. The UE determines a transmission power on
the target MCG and a transmission power on the source MCG per frequency
range.

If the UE indicates support for semi-static power sharing mode1 and is
provided *uplinkPowerSharingDAPS-Mode* = *Semi-static-mode1*, the UE
determines a transmission power for the target MCG or for the source MCG
as described in clause 7.6.2 for *nrdc-PCmode-FR1* = *Semi-static-mode1*
by considering the target MCG as the MCG and the source MCG as the SCG.

If the UE indicates support for semi-static power sharing mode2 and is
provided *uplinkPowerSharingDAPS-Mode* = *Semi-static-mode2*, the UE
determines a transmission power for the target MCG or for the source SCG
as described in clause 7.6.2 for *nrdc-PCmode-FR1* = *Semi-static-mode2*
by considering the target MCG as the MCG and the source MCG as the SCG.
The UE expects to be provided *uplinkPowerSharingDAPS-Mode* =
*Semi-static-mode2* only for synchronous DAPS HO operation \[10, TS
38.133\].

If the UE indicates support for dynamic power sharing and is provided
*uplinkPowerSharingDAPS-Mode* = *Dynamic*, the UE determines a
transmission power for the target MCG or for the source MCG as described
in clause 7.6.2 for *nrdc-PCmode-FR1* = *Dynamic* by considering the
target MCG as the MCG and the source MCG as the SCG.

Intra-frequency DAPS handover is described in clause 6.1.3.2 of \[10, TS
38.133\].

For DAPS handover that is not intra-frequency, if

\- the UE does not indicate support of
*interFreqUL-TransCancellationDAPS-r16*, and

\- UE does not indicate a capability for power sharing between source
and target MCG in DAPS handover or the UE is not provided with
*uplinkPowerSharingDAPS-Mode*,

the UE does not expect transmissions on the target and source cell in
overlapping time resources.

For DAPS handover that is not intra-frequency, if

\- the UE indicates support of *interFreqUL-TransCancellationDAPS-r16*,
and

\- UE does not indicate a capability for power sharing between source
and target MCG in DAPS handover or the UE is not provided with
*uplinkPowerSharingDAPS-Mode*, and

\- UE transmissions on the target cell and the source cell are in
overlapping time resources,

the UE transmits only on the target cell, and cancels the transmission
to source cell.

For intra-frequency DAPS handover, if

\- UE transmissions on the target cell and the source cell are in
overlapping time resources,

the UE transmits only on the target cell and cancels the transmission on
the source cell.

The UE does not expect to cancel a transmission on the source cell if a
first symbol of the transmission on the source cell is less than
$T_{\text{proc,2}} + d$ after a last symbol of a PDCCH reception where
the UE receives a PDCCH providing a DCI format scheduling a transmission
on the target cell. $T_{\text{proc,2}}$ is the PUSCH preparation time
for the corresponding PUSCH processing capability \[6, TS 38.214\]
assuming $d_{\text{2,1}} = 1$, $d$ is a time duration corresponding to 2
symbols for SCS configuration $\mu$, and $\mu$ is the smallest SCS
configuration between the SCS configuration of the PDCCH providing the
DCI format and the SCS configuration for the transmission on the source
cell. If the UE transmits PRACH using 1.25 kHz or 5 kHz SCS on the
source cell, the UE determines $T_{\text{proc,2}}$ assuming SCS
configuration $\mu = 0$.

A UE does not expect to cancel a transmission on the source cell if the
first symbol of the source cell transmission occurs, relative to a last
symbol of a PDSCH reception conveying a RAR message with a RAR UL grant
on the target cell, after a number of symbols that is smaller than
$N_{\text{T,1}} + N_{\text{T,2}} + 0.5$ msec, where $N_{\text{T,1}}$ is
a time duration of $N_{\text{1}}$ symbols corresponding to a PDSCH
processing time for UE processing capability 1 when additional PDSCH
DM-RS is configured, $N_{\text{T,2}}$ is a time duration of
$N_{\text{2}}$ symbols corresponding to a PUSCH preparation time for UE
processing capability 1 \[6, TS 38.214\] and the UE considers that
$N_{\text{1}}$ and $N_{2}$ correspond to the smaller of the SCS
configurations for the PDSCH on the target cell and the transmission on
the source cell. For $\mu = 0$, the UE assumes $N_{\text{1,0}} = 14$
\[6, TS 38.214\].

For intra-frequency DAPS handover operation, the UE expects that an
active DL BWP and an active UL BWP on the target cell are within an
active DL BWP and an active UL BWP on the source cell, respectively.

If a UE is provided search space sets on both the target MCG and the
source MCG, in any slot the UE does not expect to have USS sets on both
the target MCG and the source MCG that result in the number of monitored
PDCCH candidates and the total number of non-overlapped CCEs in both
cells that each exceed the corresponding maximum numbers per slot
defined in Table 10.1-2 and Table 10.1-3.

For DAPS operation in a same frequency band, a UE does not transmit
PUSCH/PUCCH/SRS to the source MCG in a slot overlapping in time with a
PRACH transmission to the target MCG or when a gap between a first or
last symbol of a PRACH transmission to the target MCG in a first slot
would be separated by less than $N$ symbols from a last or first symbol,
respectively, of the PUSCH/PUCCH/SRS transmission to the source MCG in a
second slot. For DAPS operation in a same frequency band, a UE does not
transmit PRACH on the source MCG in a slot overlapping in time with a
PUSCH/PUCCH/SRS transmission on the target MCG or when a gap between the
first or last symbol of a PUSCH/PUCCH/SRS transmission on the target MCG
is separated by less than $N$ symbols from a last or a first symbol,
respectively, of a PRACH transmission on the source MCG. $N = 2$ for
$\mu = 0$ or $\mu = 1$, $N = 4$ for $\mu = 2$ or $\mu = 3$, and $\mu$ is
the SCS configuration of the active UL BWP for the PUSCH/PUCCH/SRS
transmission. The PUSCH processing capability is the processing
capability of source cell.