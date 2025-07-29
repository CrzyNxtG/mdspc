### 5.1.4a MSGB reception and contention resolution for 2-step RA type

Once the MSGA preamble is transmitted, regardless of the possible
occurrence of a measurement gap, the MAC entity shall:

1\> start the *msgB-ResponseWindow* at the PDCCH occasion as specified
in TS 38.213 \[6\], clause 8.2A;

1\> monitor the PDCCH of the SpCell for a Random Access Response
identified by MSGB-RNTI while the *msgB-ResponseWindow* is running;

1\> if C-RNTI MAC CE was included in the MSGA:

2\> monitor the PDCCH of the SpCell for Random Access Response
identified by the C-RNTI while the *msgB-ResponseWindow* is running.

1\> if notification of a reception of a PDCCH transmission of the SpCell
is received from lower layers:

2\> if the C-RNTI MAC CE was included in MSGA:

3\> if the Random Access procedure was initiated for SpCell beam failure
recovery or for beam failure recovery of both BFD-RS sets of SpCell (as
specified in clause 5.17) and the PDCCH transmission is addressed to the
C-RNTI; or

3\> if the Random Access procedure was initiated for SDT beam failure
recovery (as specified in clause 5.27.1) and the PDCCH transmission is
addressed to the C-RNTI:

4\> consider this Random Access Response reception successful;

4\> stop the *msgB-ResponseWindow*;

4\> consider this Random Access procedure successfully completed.

3\> else if the *timeAlignmentTimer* associated with at least one PTAG
is running; or

3\> if CG-SDT procedure is ongoing and *cg-SDT-TimeAlignmentTimer* is
running:

4\> if the PDCCH transmission is addressed to the C-RNTI and contains a
UL grant for a new transmission:

5\> consider this Random Access Response reception successful;

5\> stop the *msgB-ResponseWindow*;

5\> consider this Random Access procedure successfully completed.

3\> else:

4\> if a downlink assignment has been received on the PDCCH for the
C-RNTI and the received TB is successfully decoded:

5\> if the MAC PDU contains the Absolute Timing Advance Command MAC CE:

6\> process the received Timing Advance Command (see clause 5.2);

6\> consider this Random Access Response reception successful;

6\> stop the *msgB-ResponseWindow*;

6\> consider this Random Access procedure successfully completed and
finish the disassembly and demultiplexing of the MAC PDU.

2\> if a valid (as specified in TS 38.213 \[6\]) downlink assignment has
been received on the PDCCH for the MSGB-RNTI and the received TB is
successfully decoded:

3\> if the MSGB contains a MAC subPDU with Backoff Indicator:

4\> set the *PREAMBLE_BACKOFF* to value of the BI field of the MAC
subPDU using Table 7.2-1, multiplied with *SCALING_FACTOR_BI*.

3\> else:

4\> set the *PREAMBLE_BACKOFF* to 0 ms.

3\> if the MSGB contains a fallbackRAR MAC subPDU; and

3\> if the Random Access Preamble identifier in the MAC subPDU matches
the transmitted *PREAMBLE_INDEX* (see clause 5.1.3a):

4\> consider this Random Access Response reception successful;

4\> apply the following actions for the SpCell:

5\> process the received Timing Advance Command (see clause 5.2);

5\> indicate the *msgA-PreambleReceivedTargetPower* and the amount of
power ramping applied to the latest Random Access Preamble transmission
to lower layers (i.e. (*PREAMBLE_POWER_RAMPING_COUNTER* -- 1) ×
*PREAMBLE_POWER_RAMPING_STEP*);

5\> if the Random Access Preamble was not selected by the MAC entity
among the contention-based Random Access Preamble(s):

6\> consider the Random Access procedure successfully completed;

6\> process the received UL grant value and indicate it to the lower
layers.

5\> else:

6\> set the *TEMPORARY_C-RNTI* to the value received in the Random
Access Response;

6\> if the Msg3 buffer is empty:

7\> obtain the MAC PDU to transmit from the MSGA buffer and store it in
the Msg3 buffer;

6\> process the received UL grant value and indicate it to the lower
layers and proceed with Msg3 transmission.

NOTE: If within a 2-step RA type procedure, an uplink grant provided in
the fallback RAR has a different size than the MSGA payload, the UE
behavior is not defined.

3\> else if the MSGB contains a successRAR MAC subPDU; and

3\> if the CCCH SDU was included in the MSGA and the UE Contention
Resolution Identity in the MAC subPDU matches the CCCH SDU:

4\> stop *msgB-ResponseWindow*;

4\> if this Random Access procedure was initiated for SI request:

5\> indicate the reception of an acknowledgement for SI request to upper
layers.

4\> else:

5\> set the C-RNTI to the value received in the *successRAR*;

5\> apply the following actions for the SpCell:

6\> process the received Timing Advance Command (see clause 5.2);

6\> indicate the *msgA-PreambleReceivedTargetPower* and the amount of
power ramping applied to the latest Random Access Preamble transmission
to lower layers (i.e. (*PREAMBLE_POWER_RAMPING_COUNTER* -- 1) ×
*PREAMBLE_POWER_RAMPING_STEP*).

4\> deliver the *TPC*, *PUCCH resource Indicator*, *ChannelAccess-CPext*
(if indicated), and *HARQ feedback Timing Indicator* received in
successRAR to lower layers.

4\> consider this Random Access Response reception successful;

4\> consider this Random Access procedure successfully completed;

4\> finish the disassembly and demultiplexing of the MAC PDU.

1\> if *msgB-ResponseWindow* expires, and the Random Access Response
Reception has not been considered as successful based on descriptions
above:

2\> increment *PREAMBLE_TRANSMISSION_COUNTER* by 1;

2\> if *PREAMBLE_TRANSMISSION_COUNTER* = *preambleTransMax* + 1:

3\> indicate a Random Access problem to upper layers;

3\> if this Random Access procedure was triggered for SI request:

4\> consider this Random Access procedure unsuccessfully completed.

2\> if the Random Access procedure is not completed:

3\> if *msgA-TransMax* is applied (see clause 5.1.1a) and
*PREAMBLE_TRANSMISSION_COUNTER* = *msgA-TransMax* + 1:

4\> set the *RA_TYPE* to *4-stepRA*;

4\> perform initialization of variables specific to Random Access type
as specified in clause 5.1.1a;

4\> if the Msg3 buffer is empty:

5\> obtain the MAC PDU to transmit from the MSGA buffer and store it in
the Msg3 buffer;

4\> flush HARQ buffer used for the transmission of MAC PDU in the MSGA
buffer;

4\> discard explicitly signalled contention-free 2-step RA type Random
Access Resources, if any;

4\> perform the Random Access Resource selection procedure as specified
in clause 5.1.2.

3\> else:

4\> select a random backoff time according to a uniform distribution
between 0 and the *PREAMBLE_BACKOFF*;

4\> if the criteria (as defined in clause 5.1.2a) to select
contention-free Random Access Resources is met during the backoff time:

5\> perform the Random Access Resource selection procedure for 2-step RA
type Random Access (see clause 5.1.2a).

4\> else:

5\> perform the Random Access Resource selection procedure for 2-step RA
type Random Access (see clause 5.1.2a) after the backoff time.

Upon receiving a fallbackRAR, the MAC entity may stop
*msgB-ResponseWindow* once the Random Access Response reception is
considered as successful.