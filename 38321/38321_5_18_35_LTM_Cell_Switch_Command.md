### 5.18.35 LTM Cell Switch Command

The network may instruct the UE to perform LTM cell switch procedure by
sending the LTM Cell Switch Command MAC CE described in clause 6.1.3.75.

The MAC entity shall:

1\> if the MAC entity receives an LTM Cell Switch Command MAC CE on a
Serving Cell:

2\> indicate to upper layers that the LTM cell switch procedure is
triggered and the Target Configuration ID included in the LTM Cell
Switch Command MAC CE;

2\> if the MAC reset operation as specified in clause 5.12 is performed,
as requested by upper layers:

3\> if Timing Advance Command value (hexa-decimal) is not set as FFF:

4\> process the received Timing Advance Command (see clause 5.2);

4\> consider the RACH-less LTM cell switch to be ongoing;

4\> if the MAC entity is associated with the SCG:

5\> indicate to upper layers to skip the Random Access procedure for
this LTM cell switch.

3\> else if the UE is configured with UE-based Timing Advance
measurement as specified in TS 38.331 \[5\] and the UE has successfully
measured the Timing Advance for the SpCell of the indicated LTM target
configuration:

4\> process the measured Timing Advance (see clause 5.2);

4\> consider the RACH-less LTM cell switch to be ongoing.

4\> if the MAC entity is associated with the SCG:

5\> indicate to upper layers to skip the Random Access procedure for
this LTM cell switch.

3\> indicate to lower layers the information regarding the TCI state
information included in the LTM Cell Switch Command MAC CE.