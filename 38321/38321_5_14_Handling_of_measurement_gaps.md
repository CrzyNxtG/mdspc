## 5.14 Handling of measurement gaps

During an activated measurement gap, the MAC entity shall, on the
Serving Cell(s) in the corresponding frequency range of the measurement
gap configured by *measGapConfig* as specified in TS 38.331 \[5\]:

1\> not perform the transmission of HARQ feedback, SR, and CSI;

1\> not report SRS;

1\> not transmit on UL-SCH except for Msg3 or the MSGA payload as
specified in clause 5.4.2.2;

1\> if the *ra-ResponseWindow* or the *ra-ContentionResolutionTimer* or
the *msgB-ResponseWindow* is running, or if there is an ongoing
RACH-less LTM cell switch, or if there is an ongoing RACH-less handover:

2\> monitor the PDCCH as specified in clauses 5.1.4, 5.1.4a, 5.1.5, and
5.7.

1\> else:

2\> not monitor the PDCCH;

2\> not receive on DL-SCH.