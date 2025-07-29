### 5.1.3a MSGA transmission

The MAC entity shall, for each MSGA:

1\> if *PREAMBLE_TRANSMISSION_COUNTER* is greater than one; and

1\> if the notification of suspending power ramping counter has not been
received from lower layers; and

1\> if LBT failure indication was not received from lower layers for the
last MSGA Random Access Preamble transmission; and

1\> if SSB selected is not changed from the selection in the last Random
Access Preamble transmission:

2\> increment *PREAMBLE_POWER_RAMPING_COUNTER* by 1.

1\> select the value of *DELTA_PREAMBLE* according to clause 7.3;

1\> set *PREAMBLE_RECEIVED_TARGET_POWER* to
*msgA-PreambleReceivedTargetPower* + *DELTA_PREAMBLE* +
(*PREAMBLE_POWER_RAMPING_COUNTER* -- 1) × *PREAMBLE_POWER_RAMPING_STEP*;

1\> if this is the first MSGA transmission within this Random Access
procedure:

2\> if the transmission is not being made for the CCCH logical channel:

3\> indicate to the Multiplexing and assembly entity to include a C-RNTI
MAC CE in the subsequent uplink transmission.

2\> if the Random Access procedure was initiated for SpCell beam failure
recovery and *spCell-BFR-CBRA* with value *true* is configured:

3\> if there is at least one Serving Cell of this MAC entity configured
with two BFD-RS sets:

4\> indicate to the Multiplexing and assembly entity to include an
Enhanced BFR MAC CE or a Truncated Enhanced BFR MAC CE in the subsequent
uplink transmission.

3\> else:

4\> indicate to the Multiplexing and assembly entity to include a BFR
MAC CE or a Truncated BFR MAC CE in the subsequent uplink transmission.

2\> else if the Random Access procedure was initiated for beam failure
recovery of both BFD-RS sets of SpCell:

3\> indicate to the Multiplexing and assembly entity to include an
Enhanced BFR MAC CE or a Truncated Enhanced BFR MAC CE in the subsequent
uplink transmission.

2\> obtain the MAC PDU to transmit from the Multiplexing and assembly
entity according to the HARQ information determined for the MSGA payload
(see clause 5.1.2a) and store it in the MSGA buffer.

1\> compute the MSGB-RNTI associated with the PRACH occasion in which
the Random Access Preamble is transmitted;

1\> instruct the physical layer to transmit the MSGA using the selected
PRACH occasion and the associated PUSCH resource of MSGA (if the
selected preamble and PRACH occasion is mapped to a valid PUSCH
occasion), using the corresponding RA-RNTI, MSGB-RNTI, *PREAMBLE_INDEX*,
*PREAMBLE_RECEIVED_TARGET_POWER*, *msgA-PreambleReceivedTargetPower*,
and the amount of power ramping applied to the latest MSGA preamble
transmission (i.e. (*PREAMBLE_POWER_RAMPING_COUNTER* -- 1) ×
*PREAMBLE_POWER_RAMPING_STEP*);

1\> if LBT failure indication is received from lower layers for the
transmission of this MSGA Random Access Preamble:

2\> instruct the physical layer to cancel the transmission of the MSGA
payload on the associated PUSCH resource;

2\> if *lbt-FailureRecoveryConfig* is configured:

3\> perform the Random Access Resource selection procedure for 2-step RA
type (see clause 5.1.2a).

2\> else:

3\> increment *PREAMBLE_TRANSMISSION_COUNTER* by 1;

3\> if *PREAMBLE_TRANSMISSION_COUNTE*R = *preambleTransMax* + 1:

4\> indicate a Random Access problem to upper layers;

4\> if this Random Access procedure was triggered for SI request:

5\> consider this Random Access procedure unsuccessfully completed.

3\> if the Random Access procedure is not completed:

4\> if *msgA-TransMax* is applied (see clause 5.1.1a) and
*PREAMBLE_TRANSMISSION_COUNTER* = *msgA-TransMax* + 1:

5\> set the *RA_TYPE* to *4-stepRA*;

5\> perform initialization of variables specific to Random Access type
as specified in clause 5.1.1a;

5\> if the Msg3 buffer is empty:

6\> obtain the MAC PDU to transmit from the MSGA buffer and store it in
the Msg3 buffer;

5\> flush HARQ buffer used for the transmission of MAC PDU in the MSGA
buffer;

5\> discard explicitly signalled contention-free 2-step RA type Random
Access Resources, if any;

5\> perform the Random Access Resource selection procedure as specified
in clause 5.1.2.

4\> else:

5\> perform the Random Access Resource selection procedure for 2-step RA
type (see clause 5.1.2a).

NOTE: The MSGA transmission includes the transmission of the PRACH
Preamble as well as the contents of the MSGA buffer in the PUSCH
resource corresponding to the selected PRACH occasion and
*PREAMBLE_INDEX* (see TS 38.213 \[6\])

The MSGB-RNTI associated with the PRACH occasion in which the Random
Access Preamble is transmitted, is computed as:

MSGB-RNTI = 1 + s_id + 14 × t_id + 14 × 80 × f_id + 14 × 80 × 8 ×
ul_carrier_id + 14 × 80 × 8 × 2

where s_id is the index of the first OFDM symbol of the PRACH occasion
(0 ≤ s_id \< 14), t_id is the index of the first slot of the PRACH
occasion in a system frame (0 ≤ t_id \< 80), where the subcarrier
spacing to determine t_id is based on the value of μ specified in clause
5.3.2 in TS 38.211 \[8\] for μ = {0, 1, 2, 3}, and for μ = {5, 6}, t_id
is the index of the 120 kHz slot in a system frame that contains the
PRACH occasion (0 ≤ t_id \< 80), f_id is the index of the PRACH occasion
in the frequency domain (0 ≤ f_id \< 8), and ul_carrier_id is the UL
carrier used for Random Access Preamble transmission (0 for NUL carrier,
and 1 for SUL carrier). The RA-RNTI is calculated as specified in clause
5.1.3.