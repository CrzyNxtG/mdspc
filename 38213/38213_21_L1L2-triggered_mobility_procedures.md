# 21 L1/L2-triggered mobility procedures

A UE can be indicated, by *LTM-Config*, candidate cells and SS/PBCH
blocks per candidate cell for the UE to obtain synchronization and
measure corresponding L1-RSRPs \[10, TS 38.133\]. A Candidate Cell TCI
States Activation/Deactivation MAC CE can activate TCI states, provided
by *CandidateTCI-State* or/and *CandidateTCI-UL-State*, associated with
SS/PBCH blocks or TRS of corresponding candidate cells \[11, TS
38.321\]. The RS index for obtaining the candidate cell downlink
pathloss estimate is provided by *pathlossReferenceRS-Id* in the
*CandidateTCI-State* or *CandidateTCI-UL-State.* If the Candidate Cell
TCI States Activation/Deactivation MAC CE activates TCI states, an LTM
Cell Switch Command MAC CE can indicate a TCI state from the activated
TCI states; otherwise, the LTM Cell Switch Command MAC CE can activate
and indicate a TCI state, provided by *CandidateTCI-State* or/and
*CandidateTCI-UL-State*. After reception of the LTM Cell Switch Command
MAC CE, activated TCI states that are not indicated by the MAC CE are
deactivated. The UE is provided configurations by
*ltm-CSI-ReportConfigToAddModList* for reporting L1-RSRP measurements
\[6, TS 38.214\] that include a number of candidate cells and a number
of SS/PBCH blocks per candidate cell from the number of candidate cells.

If *ltm-UE-MeasuredTA-ID* of a candidate cell and
*ltm-ServingCellUE-MeasuredTA-ID* of the serving cell are provided to a
UE and have same value, the UE estimates based on the UE implementation
a timing advance to apply from a first transmission on the candidate
cell that is after the reception of a cell switch command for the
candidate cell when the condition defined in clause 5.18.35 of \[11, TS
38.321\] is satisfied.

A UE can be provided configurations, by *EarlyUL-SyncConfig*, for PRACH
transmission parameters for each of the candidate cells. The UE can be
triggered a PRACH transmission on a candidate cell by a PDCCH order that
the UE receives on a serving cell and includes an indication of the
candidate cell for the PRACH transmission \[4, TS 38.212\]. If the
serving cell and the candidate cell operate in a same frequency range
and the UE would have transmissions that overlap in time, or that are in
a same slot with respect to the smallest SCS configuration between the
SCS configuration for the UL BWP with the PRACH and the SCS
configuration for the UL BWP with the PUSCH/PUCCH/SRS transmissions when
the serving cell and the candidate cell operate in a same frequency
band, or when a gap between a first or last symbol of a PRACH
transmission to the candidate cell is less than 𝑁 symbols from a last or
first symbol, respectively, of an UL transmission to the serving cell,
where $N$ is defined in Clause 8.1, the UE

\- drops the transmissions on the serving cell when the UE does not
support transmissions that overlap in time, or are in the same slot when
the serving cell and the candidate cell operate in a same frequency
band, or are separated by less than the gap on the serving cell and the
candidate cell and the UL transmission to the serving cell is other than
a RACH Msg 1, Msg A, or Msg 3 transmission.

\- prioritizes power allocation to the PRACH transmission on the
candidate cell in clause 7.5 when the UE supports transmissions that
overlap in time or are separated by less than the gap, and a total UE
transmit power in the frequency range would exceed
${\widehat{P}}_{CMAX}$.

The UE transmits the PRACH on the candidate cell as described in Clause
8.1 with a power determined as described in Clause 7.4.

A UE can be provided by a LTM Cell Switch Command MAC CE in a PDSCH
reception on the serving cell \[11, TS 38.321\] a TCI state ID and/or an
UL TCI state ID indicating a *CandidateTCI-State* and/or
*CandidateTCI-UL-State* from *ltm-DL-OrJointTCI-StateToAddModList*
and/or *ltm-UL-TCI-StateToAddModList* \[6, TS 38.214\] for applicable
receptions or transmissions on a candidate cell from the number of
candidate cells. The UE may assume that DM-RS antenna ports for PDCCH
receptions and for PDSCH receptions are quasi co-located with the
SS/PBCH block or the TRS in the TCI state with respect to quasi
co-location \'typeA\' and \'typeD\' properties, when applicable. The UE
does not expect to be indicated quasi co-location \'typeA\' properties
when a SS/PBCH block is configured as a source RS of the TCI state. The
UE applies the *CandidateTCI-State* and/or *CandidateTCI-UL-State,* if
indicated by the MAC CE, no later than
$T_{LTM - RRC - processing} + T_{LTM - processing} + T_{first - RS} + T_{RS - proc} + 3\ msec$
after the last symbol of a PUCCH or PUSCH with HARQ-ACK information for
the PDSCH providing the MAC CE, where $T_{LTM - RRC - processing}$,
$T_{LTM - processing}$, $T_{first - RS}$ and $T_{RS - proc}$ are defined
in \[10, TS 38.133\]*.* For RACH-based LTM cell switch \[19, TS
38.300\], the UE applies the *CandidateTCI-State* for receptions on the
candidate cell, and applies a spatial domain filter corresponding to the
*CandidateTCI-State* or the *CandidateTCI-UL-State* for transmissions on
the candidate cell, that are after the completion of the random access
procedure associated with the PRACH transmission on the candidate cell
and before a new TCI state is applied for the candidate cell. For
RACH-less LTM cell switch \[19, TS 38.300\], the UE applies the
*CandidateTCI-State* for receptions on the candidate cell and applies a
spatial domain filter corresponding to the *CandidateTCI-State* or the
*CandidateTCI-UL-State* for transmissions on the candidate cell before a
new TCI state is applied for the candidate cell.