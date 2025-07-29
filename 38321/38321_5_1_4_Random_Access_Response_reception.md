### 5.1.4 Random Access Response reception

Once the Random Access Preamble is transmitted and regardless of the
possible occurrence of a measurement gap, the MAC entity shall:

1\> if the contention-free Random Access Preamble for beam failure
recovery request was transmitted by the MAC entity:

2\> if the contention-free Random Access Preamble for beam failure
recovery request was transmitted on a non-terrestrial network:

3\> start the *ra-ResponseWindow* configured in
*BeamFailureRecoveryConfig* at the PDCCH occasion as specified in TS
38.213 \[6\].

2\> else:

3\> start the *ra-ResponseWindow* configured in
*BeamFailureRecoveryConfig* at the first PDCCH occasion as specified in
TS 38.213 \[6\] from the end of the Random Access Preamble transmission.

2\> monitor for a PDCCH transmission on the search space indicated by
*recoverySearchSpaceId* of the SpCell identified by the C-RNTI while
*ra-ResponseWindow* is running.

1\> else:

2\> if the Random Access Preamble was transmitted on a non-terrestrial
network:

3\> if the Random Access Preamble is transmitted with repetitions:

4\> start the *ra-ResponseWindow* configured in *RACH-ConfigCommon* at
the PDCCH occasion from the end of all repetitions of the Random Access
Preamble transmission as specified in TS 38.213 \[6\].

3\> else:

4\> start the *ra-ResponseWindow* configured in *RACH-ConfigCommon* at
the PDCCH occasion as specified in TS 38.213 \[6\].

2\> else if the Random Access Preamble is transmitted with repetitions:

3\> start the *ra-ResponseWindow* configured in *RACH-ConfigCommon* at
the first PDCCH occasion from the end of all repetitions of the Random
Access Preamble transmission as specified in TS 38.213 \[6\].

2\> else:

3\> start the *ra-ResponseWindow* configured in *RACH-ConfigCommon* at
the first PDCCH occasion as specified in TS 38.213 \[6\] from the end of
the Random Access Preamble transmission.

2\> monitor the PDCCH of the SpCell for Random Access Response(s)
identified by the RA-RNTI while the *ra-ResponseWindow* is running.

1\> if notification of a reception of a PDCCH transmission on the search
space indicated by *recoverySearchSpaceId* is received from lower layers
on the Serving Cell where the preamble was transmitted; and

1\> if PDCCH transmission is addressed to the C-RNTI; and

1\> if the contention-free Random Access Preamble for beam failure
recovery request was transmitted by the MAC entity:

2\> consider the Random Access procedure successfully completed.

1\> else if a valid (as specified in TS 38.213 \[6\]) downlink
assignment has been received on the PDCCH for the RA-RNTI and the
received TB is successfully decoded:

2\> if the Random Access Response contains a MAC subPDU with Backoff
Indicator:

3\> set the *PREAMBLE_BACKOFF* to value of the BI field of the MAC
subPDU using Table 7.2-1, multiplied with *SCALING_FACTOR_BI*.

2\> else:

3\> set the *PREAMBLE_BACKOFF* to 0 ms.

2\> if the Random Access Response contains a MAC subPDU with Random
Access Preamble identifier corresponding to the transmitted
*PREAMBLE_INDEX* (see clause 5.1.3):

3\> consider this Random Access Response reception successful.

2\> if the Random Access Response reception is considered successful:

3\> if the Random Access Response includes a MAC subPDU with RAPID only:

4\> consider this Random Access procedure successfully completed;

4\> indicate the reception of an acknowledgement for SI request to upper
layers.

3\> else:

4\> apply the following actions for the Serving Cell where the Random
Access Preamble was transmitted:

5\> process the received Timing Advance Command (see clause 5.2);

5\> indicate the *preambleReceivedTargetPower* and the amount of power
ramping applied to the latest Random Access Preamble transmission to
lower layers (i.e. (*PREAMBLE_POWER_RAMPING_COUNTER* -- 1) ×
*PREAMBLE_POWER_RAMPING_STEP +* *POWER_OFFSET_2STEP_RA*);

5\> if the Random Access procedure for an SCell is performed on uplink
carrier where *pusch-Config* is not configured:

6\> ignore the received UL grant.

5\> else:

6\> process the received UL grant value and indicate it to the lower
layers.

4\> if the Random Access Preamble was not selected by the MAC entity
among the contention-based Random Access Preamble(s):

5\> consider the Random Access procedure successfully completed.

4\> else:

5\> set the *TEMPORARY_C-RNTI* to the value received in the Random
Access Response;

5\> if this is the first successfully received Random Access Response
within this Random Access procedure:

6\> if the transmission is not being made for the CCCH logical channel:

7\> indicate to the Multiplexing and assembly entity to include a C-RNTI
MAC CE in the subsequent uplink transmission.

6\> if the Random Access procedure was initiated for SpCell beam failure
recovery and *spCell-BFR-CBRA* with value *true* is configured:

7\> if there is at least one Serving Cell of this MAC entity configured
with two BFD-RS sets:

8\> indicate to the Multiplexing and assembly entity to include an
Enhanced BFR MAC CE or a Truncated Enhanced BFR MAC CE in the subsequent
uplink transmission.

7\> else:

8\> indicate to the Multiplexing and assembly entity to include a BFR
MAC CE or a Truncated BFR MAC CE in the subsequent uplink transmission.

6\> else if the Random Access procedure was initiated for beam failure
recovery of both BFD-RS sets of SpCell:

7\> indicate to the Multiplexing and assembly entity to include an
Enhanced BFR MAC CE or a Truncated Enhanced BFR MAC CE in the subsequent
uplink transmission.

6\> obtain the MAC PDU to transmit from the Multiplexing and assembly
entity and store it in the Msg3 buffer.

NOTE 1: If within a Random Access procedure, an uplink grant provided in
the Random Access Response for the same group of contention-based Random
Access Preambles has a different size than the first uplink grant
allocated during that Random Access procedure, the UE behavior is not
defined.

1\> if *ra-ResponseWindow* configured in *BeamFailureRecoveryConfig*
expires and if a PDCCH transmission on the search space indicated by
*recoverySearchSpaceId* addressed to the C-RNTI has not been received on
the Serving Cell where the preamble was transmitted; or

1\> if *ra-ResponseWindow* configured in *RACH-ConfigCommon* expires,
and if the Random Access Response containing Random Access Preamble
identifiers that matches the transmitted *PREAMBLE_INDEX* has not been
received:

2\> consider the Random Access Response reception not successful;

2\> increment *PREAMBLE_TRANSMISSION_COUNTER* by 1;

2\> if *PREAMBLE_TRANSMISSION_COUNTER* = *preambleTransMax* + 1:

3\> if the Random Access Preamble is transmitted on the SpCell:

4\> indicate a Random Access problem to upper layers;

4\> if this Random Access procedure was triggered for SI request:

5\> consider the Random Access procedure unsuccessfully completed.

3\> else if the Random Access Preamble is transmitted on an SCell:

4\> consider the Random Access procedure unsuccessfully completed.

2\> if the Random Access procedure is not completed:

3\> if the Random Access Preamble is transmitted with repetitions and
neither contention-free Random Access Resources nor Random Access
resources for SI request have been provided for this Random Access
procedure:

4\> if *PREAMBLE_TRANSMISSION_COUNTER* =
\[*preambleTransMax-Msg1-Repetition*\] + 1; or

4\> if *PREAMBLE_TRANSMISSION_COUNTER* = 2 ×
\[*preambleTransMax-Msg1-Repetition*\] + 1:

5\> if set of Random Access resources configured with the same
*prach-ConfigurationIndex* and associated with a higher Msg1 repetition
number with the same feature or feature combination as the current set
of Random Access resources is available:

6\> select the set of Random Access resources associated with the next
higher Msg1 repetition number with the same feature or feature
combination for this Random Access procedure;

6\> initialize *startPreambleForThisPartition*,
*numberOfPreamblesPerSSB-ForThisPartition*, *numberOfRA-PreamblesGroupA*
and *msg1-RepetitionTimeOffsetROGroup* parameters for the Random Access
procedure according to the values configured by RRC for the selected set
of Random Access resources.

3\> select a random backoff time according to a uniform distribution
between 0 and the *PREAMBLE_BACKOFF*;

3\> if the criteria (as defined in clause 5.1.2) to select
contention-free Random Access Resources is met during the backoff time:

4\> perform the Random Access Resource selection procedure (see clause
5.1.2).

3\> else if the Random Access procedure for an SCell is performed on
uplink carrier where *pusch-Config* is not configured:

4\> delay the subsequent Random Access transmission until the Random
Access Procedure is triggered by a PDCCH order with the same
*ra-PreambleIndex*, *ra-ssb-OccasionMaskIndex*, and UL/SUL indicator TS
38.212 \[9\].

3\> else:

4\> perform the Random Access Resource selection procedure (see clause
5.1.2) after the backoff time.

The MAC entity may stop *ra-ResponseWindow* (and hence monitoring for
Random Access Response(s)) after successful reception of a Random Access
Response containing Random Access Preamble identifiers that matches the
transmitted *PREAMBLE_INDEX*.

HARQ operation is not applicable to the Random Access Response
reception.

NOTE 2: For the case that RAR PDSCH bandwidth is larger than the
bandwidth the eRedCap UE can receive or process per slot, and the UL
grant in RAR indicates that the time is not enough for Msg3
transmission, as specified in TS 38.213 \[6\], it is up to UE
implementation, e.g. either to consider the Random Access Response
reception not successful, or transmit Msg3.