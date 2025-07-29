### 5.1.3 Random Access Preamble transmission

The MAC entity shall, for each Random Access Preamble:

1\> if *PREAMBLE_TRANSMISSION_COUNTER* is greater than one; and

1\> if the notification of suspending power ramping counter has not been
received from lower layers; and

1\> if LBT failure indication was not received from lower layers for the
last Random Access Preamble transmission; and

1\> if SSB or CSI-RS selected is not changed from the selection in the
last Random Access Preamble transmission; and

1\> if the Random Access procedure is not initiated by the PDCCH order
for an LTM candidate cell:

2\> increment *PREAMBLE_POWER_RAMPING_COUNTER* by 1.

1\> if the Random Access procedure is initiated by the PDCCH order for
an LTM candidate cell as preamble re-transmission; and

1\> if the PDCCH order indicates the same LTM candidate cell and the
same SSB as the last Random Access Preamble transmission:

2\> increment *PREAMBLE_POWER_RAMPING_COUNTER* by 1.

1\> select the value of *DELTA_PREAMBLE* according to clause 7.3;

1\> set *PREAMBLE_RECEIVED_TARGET_POWER* to
*preambleReceivedTargetPower* + *DELTA_PREAMBLE* +
(*PREAMBLE_POWER_RAMPING_COUNTER* -- 1) × *PREAMBLE_POWER_RAMPING_STEP*
*+* *POWER_OFFSET_2STEP_RA*;

1\> except for contention-free Random Access Preamble for beam failure
recovery request and contention-free Random Access Preamble triggered by
a PDCCH order for an LTM candidate cell, compute the RA-RNTI associated
with the PRACH occasion in which the Random Access Preamble is
transmitted;

1\> instruct the physical layer to transmit the Random Access Preamble
using the selected PRACH occasion, corresponding RA-RNTI (if available),
*PREAMBLE_INDEX*, and *PREAMBLE_RECEIVED_TARGET_POWER*.

1\> if the Random Access Procedure is triggered by a PDCCH order for an
LTM candidate cell:

2\> consider this Random Access procedure completed.

1\> if LBT failure indication is received from lower layers for this
Random Access Preamble transmission:

2\> if *lbt-FailureRecoveryConfig* is configured:

3\> perform the Random Access Resource selection procedure (see clause
5.1.2).

2\> else:

3\> increment *PREAMBLE_TRANSMISSION_COUNTER* by 1;

3\> if *PREAMBLE_TRANSMISSION_COUNTER* = *preambleTransMax* + 1:

4\> if the Random Access Preamble is transmitted on the SpCell:

5\> indicate a Random Access problem to upper layers;

5\> if this Random Access procedure was triggered for SI request:

6\> consider the Random Access procedure unsuccessfully completed.

4\> else if the Random Access Preamble is transmitted on an SCell:

5\> consider the Random Access procedure unsuccessfully completed.

3\> if the Random Access procedure is not completed:

4\> perform the Random Access Resource selection procedure (see clause
5.1.2).

The RA-RNTI associated with the PRACH occasion in which the Random
Access Preamble is transmitted or the RA-RNTI associated with the last
valid PRACH occasion in the set of PRACH occasions (as specified in TS
38.213 \[6\]) for Msg1 repetition, is computed as:

RA-RNTI = 1 + s_id + 14 × t_id + 14 × 80 × f_id + 14 × 80 × 8 ×
ul_carrier_id

where s_id is the index of the first OFDM symbol of the PRACH occasion
(0 ≤ s_id \< 14), t_id is the index of the first slot of the PRACH
occasion in a system frame (0 ≤ t_id \< 80), where the subcarrier
spacing to determine t_id is based on the value of μ specified in clause
5.3.2 in TS 38.211 \[8\] for μ = {0, 1, 2, 3}, and for μ = {5, 6}, t_id
is the index of the 120 kHz slot in a system frame that contains the
PRACH occasion (0 ≤ t_id \< 80), f_id is the index of the PRACH occasion
in the frequency domain (0 ≤ f_id \< 8), and ul_carrier_id is the UL
carrier used for Random Access Preamble transmission (0 for NUL carrier,
and 1 for SUL carrier).