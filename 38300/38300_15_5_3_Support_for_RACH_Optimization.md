### 15.5.3 Support for RACH Optimization

RACH optimization is supported by UE reported information made available
at the NG RAN node as specified in TS 38.331 \[12\] and by PRACH
parameters exchange between NG RAN nodes.

The contents of the RA Report comprise of the following:

\- Contention detection indication per RACH attempt;

\- Indexes of the SSBs and number of RACH preambles sent on each tried
SSB listed in chronological order of attempts;

\- Indication whether the selected SSB is above or below the configured
RSRP threshold per RACH attempt;

\- 2-step RACH information as specified in clause 5.7.10.4 of TS 38.331
\[12\];

\- Indication of LBT failures detected during the random access.

**SN RA Reports**

The UE may also support collection of SN RA Reports.

The SN RA report retrieval and forwarding is specified in TS 37.340
\[21\].