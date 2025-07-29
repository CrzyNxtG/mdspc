## 5.30 Handling of FR2 UL gap

During the FR2 UL gap configured by *ul-GapFR2-Config* as specified in
TS 38.331 \[5\], the MAC entity shall, on the Serving Cell(s) of FR2
single CC and intra-band CA, or on the Serving Cell(s) of FR2 inter-band
CA where UE does not support *tx-Support-UL-GapFR2*:

1\> only perform transmission of:

2\> PRACH preamble as specified in clause 5.1.2 and 5.1.2a;

2\> UL-SCH for Msg3 or the MSGA payload as specified in clause 5.4.2.2;

2\> UL-SCH for configured grant;

2\> the valid CSI report during SCell activation procedure where the
valid CSI report is valid CQI with non-zero CQI index defined in TS
38.214 \[7\], clause 5.2.2.1, when the time period between UL gap
colliding with CSI report of non-zero CQI and the slot where the SCell
activation MAC CE or CSI report activation command is received is no
less than 10 ms;

2\> the valid L1 RSRP report during SCell activation procedure, where
the valid L1 RSRP report is non lowest L1 RSRP defined in TS 38.133
\[11\], clause 10.1.6, when the time period between UL gap colliding
with L1 RSRP reporting and the slot where the SCell activation MAC CE or
CSI report activation command is received is no less than 10 ms;

2\> the PUCCH transmission for SR, and link recovery request (LRR)
defined in TS 38.133 \[11\], clause 8.5.