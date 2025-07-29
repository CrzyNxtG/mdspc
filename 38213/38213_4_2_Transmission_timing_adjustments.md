## 4.2 Transmission timing adjustments

A UE can be provided a value $N_{TA,offset}$ of a timing advance offset
for a serving cell by *n-TimingAdvanceOffset* for the serving cell. If
for a serving cell the UE is provided two *coresetPoolIndex* values 0
and 1 for first and second CORESETs, or is not provided
*coresetPoolIndex* value for first CORESETs and is provided
*coresetPoolIndex* value of 1 for second CORESETs, the UE can be
provided first and second $N_{TA,offset}$ values by
*n-TimingAdvanceOffset* and *n-TimingAdvanceOffset2* for transmissions
with first and second spatial filters associated with first and second
TCI states for the first and second CORESETs, respectively. A UE can be
provided a second $N_{TA,offset}$ value for transmissions with second
spatial domain filters corresponding to second TCI states or to second
SS/PBCH block receptions associated with *physCellId* different from
*physCellId* for the serving cell in addition to a first $N_{TA,offset}$
value for transmissions with first spatial domain filters corresponding
to first TCI states or to first SS/PBCH block receptions associated with
*physCellId* for the serving cell. The first and second $N_{TA,offset}$
values correspond to first and second TAGs indicated in respective MAC
RARs or in an absolute timing advance command MAC CE \[11, TS 38.321\]
having an association indicated by *tag-Id-ptr* with first and second
joint TCI states provided by *dl-OrJointTCI-StateList* or first and
second UL TCI states provided by *ul*-*TCI-State-List*. If the UE is not
provided *n-TimingAdvanceOffset* for a serving cell, the UE determines a
default value $N_{TA,offset}$ of the timing advance offset for the
serving cell as described in \[10, TS 38.133\].

If a UE is configured with two UL carriers for a serving cell, a same
timing advance offset value $N_{TA,offset}$ applies to both carriers for
transmissions on the serving cell that are associated with a same TAG.
The UE does not expect to apply two $N_{TA,offset}$ values for
transmissions on the SUL carrier.

Upon reception of a timing advance command for a TAG, the UE adjusts
uplink timing for PUSCH/SRS/PUCCH transmission on all the serving cells
in the TAG based on a value $N_{TA,offset}$ that the UE expects to be
same for all the serving cells in the TAG and based on the received
timing advance command where the uplink timing for PUSCH/SRS/PUCCH
transmissions is the same for all the serving cells in the TAG.

For a band with synchronous contiguous intra-band EN-DC in a band
combination with non-applicable maximum transmit timing difference
requirements as described in Note 1 of Table 7.5.3-1 of \[10, TS
38.133\], if the UE indicates *ul-TimingAlignmentEUTRA-NR* as
\'required\' and uplink transmission timing based on timing adjustment
indication for a TAG from MCG and a TAG from SCG are determined to be
different by the UE, the UE adjusts the transmission timing for
PUSCH/SRS/PUCCH transmission on all serving cells part of the band with
the synchronous contiguous intra-band EN-DC based on timing adjustment
indication for a TAG from a serving cell in MCG in the band. The UE is
not expected to transmit a PUSCH/SRS/PUCCH in one CG when the
PUSCH/SRS/PUCCH is overlapping in time, even partially, with random
access preamble transmitted in another CG.

For a SCS of $2^{\mu} \bullet 15$ kHz, the timing advance command for a
TAG indicates the change of the uplink timing relative to the current
uplink timing for the TAG in multiples of
$16 \bullet \frac{64 \bullet T_{c}}{2^{\mu}}$. The start timing of the
random access preamble is described in \[4, TS 38.211\].

A timing advance command \[11, TS 38.321\] in case of random access
response or in an absolute timing advance command MAC CE or in a cell
switch command, $T_{A}$, for a TAG indicates $N_{TA}$ values by index
values of $T_{A}$ = 0, 1, 2, \..., 3846, where an amount of the time
alignment for the TAG with SCS of $2^{\mu} \bullet 15$ kHz is
$N_{TA} = T_{A} \bullet 16 \bullet \frac{64}{2^{\mu}}$. $N_{TA}$ is
defined in \[4, TS 38.211\] and is relative to the SCS of the first
uplink transmission from the UE after the reception of the random access
response or absolute timing advance command MAC CE or the cell switch
command.

In other cases, a timing advance command \[11, TS 38.321\], $T_{A}$, for
a TAG indicates adjustment of a current $N_{TA}$ value, $N_{TA\_ old}$,
to the new $N_{TA}$ value, $N_{TA\_ new}$, by index values of $T_{A}$ =
0, 1, 2,\..., 63, where for a SCS of $2^{\mu} \bullet 15$ kHz,
$N_{TA\_ new} = N_{TA\_ old} + \left( T_{A} - 31 \right) \bullet 16 \bullet \frac{64}{2^{\mu}}$.

If a UE has multiple active UL BWPs, as described in clause 12, in a
same TAG, including UL BWPs in two UL carriers of a serving cell, the
timing advance command value is relative to the largest SCS of the
multiple active UL BWPs. The applicable $N_{TA\_ new}$ value for an UL
BWP with lower SCS may be rounded to align with the timing advance
granularity for the UL BWP with the lower SCS while satisfying the
timing advance accuracy requirements in \[10, TS 38.133\].

Adjustment of an $N_{TA}$ value by a positive or a negative amount
indicates advancing or delaying the uplink transmission timing for the
TAG by a corresponding amount, respectively.

For a timing advance command received on uplink slot $n$, except for a
timing advance command received in a cell switch command, and for a
transmission other than a PUSCH scheduled by a RAR UL grant or a
fallbackRAR UL grant as described in clause 8.2A or 8.3, or a PUCCH with
HARQ-ACK information in response to a successRAR as described in clause
8.2A, the corresponding adjustment of the uplink transmission timing
applies from the beginning of uplink slot
$n + k + 1{+ 2}^{\mu} \bullet K_{offset}$ where
$k = \left\lceil N_{slot}^{subframe,\ \ \mu} \bullet \frac{\left( N_{T,1} + N_{T,2} + N_{TA,max} + 0.5 \right)}{T_{sf}} \right\rceil$,
$N_{T,1}$ is a time duration in msec of $N_{1}$ symbols corresponding to
a PDSCH processing time for UE processing capability 1 when additional
PDSCH DM-RS is configured, $N_{T,2}$ is a time duration in msec of
$N_{2}$ symbols corresponding to a PUSCH preparation time for UE
processing capability 1 \[6, TS 38.214\], $N_{TA,max}$ is the maximum
timing advance value in msec that can be provided by a TA command field
of 12 bits, $N_{slot}^{subframe,\ \ \mu}$ is the number of slots per
subframe, $T_{sf}$ is the subframe duration of 1 msec, and
$K_{offset} = K_{cell,offset} - K_{UE,offset}$, where $K_{cell,offset}$
is provided by *cellSpecificKoffset* and $K_{UE,offset}$ is provided by
a Differential Koffset MAC CE command \[11, TS 38.321\]; otherwise, if
not respectively provided, $K_{cell,offset} = 0$ or $K_{UE,offset} = 0$.
$N_{1}$ and $N_{2}$ are determined with respect to the minimum SCS among
the SCSs of all configured UL BWPs for all uplink carriers in the TAG
and of all configured DL BWPs for the corresponding downlink carriers.
For $\mu = 0$, the UE assumes $N_{1,0} = 14$ \[6, TS 38.214\]. Slot $n$
and $N_{slot}^{subframe,\ \ \mu}$ are determined with respect to the
minimum SCS among the SCSs of all configured UL BWPs for all uplink
carriers in the TAG. $N_{TA,max}$ is determined with respect to the
minimum SCS among the SCSs of all configured UL BWPs for all uplink
carriers in the TAG and for all configured initial UL BWPs provided by
*initialUplinkBWP*. The uplink slot $n$ is the last slot among uplink
slot(s) overlapping with the slot(s) of PDSCH reception assuming
$T_{TA} = 0$, where the PDSCH provides the timing advance command and
$T_{TA}$ is defined in \[4, TS 38.211\].

If a UE changes an active UL BWP between a time of a timing advance
command reception and a time of applying a corresponding adjustment for
the uplink transmission timing, the UE determines the timing advance
command value based on the SCS of the new active UL BWP. If the UE
changes an active UL BWP after applying an adjustment for the uplink
transmission timing, the UE assumes a same absolute timing advance
command value before and after the active UL BWP change.

If the received downlink timing changes and is not compensated or is
only partly compensated by the uplink timing adjustment without timing
advance command as described in \[10, TS 38.133\], the UE changes
$N_{TA}$ accordingly. If a UE operates with two TAGs on an active UL BWP
of a serving cell, the UE expects that a difference between a first
downlink timing associated with a first TAG and a second downlink timing
associated with a second TAG is not larger than the CP length for the
active UL BWP unless the UE indicates *rxTimingDiff*. If a UE indicates
*posUE-TA-AutoAdjustment*, and transmits SRS based on a configuration by
*SRS-PosResourceSet* in *SRS-PosRRC-InactiveValidityAreaConfig* in
RRC_INACTIVE state,

\- if the UE is provided *autonomousTA-AdjustmentEnabled*, the UE may
autonomously update $N_{TA}$ at cell reselection as described in \[10,
TS 38.133\]

\- if the UE is not provided *autonomousTA-AdjustmentEnabled*, the UE
maintains the $N_{TA}$ of a last serving cell prior to the release of a
dedicated RRC connection \[11, TS 38.321\].

For operation with single TAG on a serving cell, if two adjacent slots
overlap due to a TA command or due to update of
$N_{\text{TA,adj}}^{\text{UE}}$ or $N_{\text{TA,adj}}^{\text{common}}$,
when applicable, the latter slot is reduced in duration relative to the
former slot. The UE does not change $N_{TA}$ during an actual time
domain window for a PUSCH or a PUCCH transmission \[6, TS 38.214\]. If
the UE is not provided *sTx-2Panel* and operates with two TAGs on a
serving cell, the UE does not expect transmissions associated with
different TAGs to overlap unless the UE indicates
*overlapUL-TransReduction*; if the UE indicates
*overlapUL-TransReduction*, the UE reduces in duration a latter
transmission using a first TAG to avoid overlapping with a former
transmission using a second TAG.

Using higher-layer ephemeris parameters for a serving satellite or
*atg-gNB-Location* for ATG, if provided, a UE pre-compensates the
two-way transmission delay on the service link or on the link between
gNB and UE for ATG based on $N_{\text{TA,adj}}^{\text{UE}}$ that the UE
determines using the serving satellite position or gNB location for ATG
and its own position. To pre-compensate the two-way transmission delay
between the uplink time synchronization reference point and the serving
satellite, the UE determines $N_{\text{TA,adj}}^{\text{common}}\ $\[4,
TS 38.211\] based on one-way propagation delay ${Delay}_{common}(t)$
that the UE determines as:

> $${Delay}_{common}(t) = \ \frac{{TA}_{Common}}{2} + \ \frac{{TA}_{CommonDrift}}{2} \times \left( t - t_{epoch} \right) + \frac{{TA}_{CommonDriftVariant}}{2} \times \left( t - t_{epoch} \right)^{2}\ $$

where ${TA}_{Common}$, ${TA}_{CommonDrift}$, and
${TA}_{CommonDriftVariant}$ are respectively provided by *ta-Common*,
*ta-CommonDrift*, and *ta-CommonDriftVariant* and $t_{epoch}$ is
provided by *epochTime* which is the epoch time of *ta-Common*,
*ta-CommonDrift*, and *ta-CommonDriftVariant* \[12, TS 38.331\].
${Delay}_{common}(t)$ provides a distance at time $t$ between the
serving satellite and the uplink time synchronization reference point
divided by the speed of light. The uplink time synchronization reference
point is the point where DL and UL are frame aligned with an offset
given by $N_{TA,offset}$.