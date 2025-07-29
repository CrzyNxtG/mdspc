### 5.1.5 Contention Resolution

Once Msg3 is transmitted the MAC entity shall:

1\> if the Msg3 transmission (i.e. initial transmission or HARQ
retransmission) is scheduled with PUSCH repetition Type A:

2\> if Msg3 is transmitted on a non-terrestrial network:

3\> start or restart the *ra-ContentionResolutionTimer* in the first
symbol after the end of all repetitions of the Msg3 transmission plus
the UE-gNB RTT.

2\> else:

3\> start or restart the *ra-ContentionResolutionTimer* in the first
symbol after the end of all repetitions of the Msg3 transmission.

1\> else if Msg3 transmission (i.e. initial transmission or HARQ
retransmission) is transmitted on a non-terrestrial network:

2\> start or restart the *ra-ContentionResolutionTimer* in the first
symbol after the end of the Msg3 transmission plus the UE-gNB RTT.

1\> else:

2\> start or restart the *ra-ContentionResolutionTimer* in the first
symbol after the end of the Msg3 transmission.

1\> monitor the PDCCH while the *ra-ContentionResolutionTimer* is
running regardless of the possible occurrence of a measurement gap;

1\> if notification of a reception of a PDCCH transmission of the SpCell
is received from lower layers:

2\> if the C-RNTI MAC CE was included in Msg3:

3\> if the Random Access procedure was initiated for SpCell beam failure
recovery or for beam failure recovery of both BFD-RS sets of SpCell (as
specified in clause 5.17) and the PDCCH transmission is addressed to the
C-RNTI; or

3\> if the Random Access procedure was initiated by a PDCCH order and
the PDCCH transmission is addressed to the C-RNTI; or

3\> if the Random Access procedure was initiated for SDT beam failure
recovery (as specified in clause 5.27.1) and the PDCCH transmission is
addressed to the C-RNTI; or

3\> if the Random Access procedure was initiated by the MAC sublayer
itself or by the RRC sublayer and the PDCCH transmission is addressed to
the C-RNTI and contains a UL grant for a new transmission:

4\> consider this Contention Resolution successful;

4\> stop *ra-ContentionResolutionTimer*;

4\> discard the *TEMPORARY_C-RNTI*;

4\> consider this Random Access procedure successfully completed.

2\> else if the CCCH SDU was included in Msg3 and the PDCCH transmission
is addressed to its *TEMPORARY_C-RNTI*:

3\> if the MAC PDU is successfully decoded:

4\> stop *ra-ContentionResolutionTimer*;

4\> if the MAC PDU contains a UE Contention Resolution Identity MAC CE;
and

4\> if the UE Contention Resolution Identity in the MAC CE matches the
CCCH SDU transmitted in Msg3:

5\> consider this Contention Resolution successful and finish the
disassembly and demultiplexing of the MAC PDU;

5\> if this Random Access procedure was initiated for SI request:

6\> indicate the reception of an acknowledgement for SI request to upper
layers.

5\> else:

6\> set the C-RNTI to the value of the *TEMPORARY_C-RNTI*;

5\> discard the *TEMPORARY_C-RNTI*;

5\> consider this Random Access procedure successfully completed.

4\> else:

5\> discard the *TEMPORARY_C-RNTI*;

5\> consider this Contention Resolution not successful and discard the
successfully decoded MAC PDU.

3\> else, for eRedCap UE, if lower layer detects that PDSCH transmission
scheduled by PDCCH has a larger bandwidth than UE can receive or process
per slot:

4\> stop *ra-ContentionResolutionTimer*;

4\> discard the *TEMPORARY_C-RNTI*;

4\> consider this Contention Resolution not successful.

1\> if *ra-ContentionResolutionTimer* expires:

2\> if Msg3 transmission was transmitted on a non-terrestrial network:

3\> if no PDCCH addressed to TC-RNTI indicating uplink grant for a Msg3
retransmission is received after the start of the
*ra-ContentionResolutionTimer*:

4\> discard the *TEMPORARY_C-RNTI*;

4\> consider the Contention Resolution not successful.

2\> else:

3\> discard the *TEMPORARY_C-RNTI*;

3\> consider the Contention Resolution not successful.

1\> if the Contention Resolution is considered not successful:

2\> flush the HARQ buffer used for transmission of the MAC PDU in the
Msg3 buffer;

2\> increment *PREAMBLE_TRANSMISSION_COUNTER* by 1;

2\> if *PREAMBLE_TRANSMISSION_COUNTER* = *preambleTransMax* + 1:

3\> indicate a Random Access problem to upper layers.

3\> if this Random Access procedure was triggered for SI request:

4\> consider the Random Access procedure unsuccessfully completed.

2\> if the Random Access procedure is not completed:

3\> if the *RA_TYPE* is set to *4-stepRA*:

4\> if the Random Access Preamble is transmitted with repetitions and
contention-free Random Access Resources have not been provided for this
Random Access procedure:

5\> if *PREAMBLE_TRANSMISSION_COUNTER* =
\[*preambleTransMax-Msg1-Repetition*\] + 1; or

5\> if *PREAMBLE_TRANSMISSION_COUNTER* = 2 ×
\[*preambleTransMax-Msg1-Repetition*\] + 1:

6\> if set of Random Access resources configured with the same
*prach-ConfigurationIndex* and associated with a higher Msg1 repetition
number with the same feature or feature combination as the current set
of Random Access resources is available:

7\> select the set of Random Access resources associated with the next
higher Msg1 repetition number with the same feature or feature
combination for this Random Access procedure;

7\> initialize *startPreambleForThisPartition*,
*numberOfPreamblesPerSSB-ForThisPartition*, *numberOfRA-PreamblesGroupA*
and *msg1-RepetitionTimeOffsetROGroup* parameters for the Random Access
procedure according to the values configured by RRC for the selected set
of Random Access resources.

4\> select a random backoff time according to a uniform distribution
between 0 and the *PREAMBLE_BACKOFF*;

4\> if the criteria (as defined in clause 5.1.2) to select
contention-free Random Access Resources is met during the backoff time:

5\> perform the Random Access Resource selection procedure (see clause
5.1.2);

4\> else:

5\> perform the Random Access Resource selection procedure (see clause
5.1.2) after the backoff time.

3\> else (i.e. the *RA_TYPE* is set to *2-stepRA*):

4\> if *msgA-TransMax* is applied (see clause 5.1.1a) and
*PREAMBLE_TRANSMISSION_COUNTER* = *msgA-TransMax* + 1:

5\> set the *RA_TYPE* to *4-stepRA*;

5\> perform initialization of variables specific to Random Access type
as specified in clause 5.1.1a;

5\> flush HARQ buffer used for the transmission of MAC PDU in the MSGA
buffer;

5\> discard explicitly signalled contention-free 2-step RA type Random
Access Resources, if any;

5\> perform the Random Access Resource selection as specified in clause
5.1.2.

4\> else:

5\> select a random backoff time according to a uniform distribution
between 0 and the *PREAMBLE_BACKOFF*;

5\> if the criteria (as defined in clause 5.1.2a) to select
contention-free Random Access Resources is met during the backoff time:

6\> perform the Random Access Resource selection procedure for 2-step RA
type as specified in clause 5.1.2a.

5\> else:

6\> perform the Random Access Resource selection for 2-step RA type
procedure (see clause 5.1.2a) after the backoff time.