### 5.2.3 Physical downlink control channels

The Physical Downlink Control Channel (PDCCH) can be used to schedule DL
transmissions on PDSCH and UL transmissions on PUSCH, where the Downlink
Control Information (DCI) on PDCCH includes:

\- Downlink assignments containing at least modulation and coding
format, resource allocation, and hybrid-ARQ information related to
DL-SCH;

\- Uplink scheduling grants containing at least modulation and coding
format, resource allocation, and hybrid-ARQ information related to
UL-SCH.

In addition to scheduling, PDCCH can be used to for:

\- Activation and deactivation of configured PUSCH transmission with
configured grant;

\- Activation and deactivation of PDSCH semi-persistent transmission;

\- Notifying one or more UEs of the slot format;

\- Notifying one or more UEs of the PRB(s) and OFDM symbol(s) where the
UE may assume no transmission is intended for the UE;

\- Transmission of TPC commands for PUCCH and PUSCH;

\- Transmission of one or more TPC commands for SRS transmissions by one
or more UEs;

\- Switching a UE\'s active bandwidth part;

\- Initiating a random access procedure;

\- Indicating the UE(s) to monitor the PDCCH during the next occurrence
of the DRX on-duration;

\- In IAB context, indicating the availability for soft symbols of an
IAB-DU;

\- Triggering one shot HARQ-ACK codebook feedback;

\- For operation with shared spectrum channel access:

\- Triggering search space set group switching;

\- Indicating one or more UEs about the available RB sets and channel
occupancy time duration;

\- Indicating downlink feedback information for configured grant PUSCH
(CG-DFI).

A UE monitors a set of PDCCH candidates in the configured monitoring
occasions in one or more configured COntrol REsource SETs (CORESETs)
according to the corresponding search space configurations.

A CORESET consists of a set of PRBs with a time duration of 1 to 3 OFDM
symbols. The resource units Resource Element Groups (REGs) and Control
Channel Elements (CCEs) are defined within a CORESET with each CCE
consisting a set of REGs. Control channels are formed by aggregation of
CCE. Different code rates for the control channels are realized by
aggregating different number of CCE. Interleaved and non-interleaved
CCE-to-REG mapping are supported in a CORESET.

The PDCCH repetition is operated by using two search spaces which are
explicitly linked by configuration provided by the RRC layer, and are
associated with corresponding CORESETs. For PDCCH repetition, two linked
search spaces are configured with the same number of candidates, and two
PDCCH candidates in two search spaces are linked with the same candidate
index. When PDCCH repetition is scheduled to a UE, an intra-slot
repetition is allowed and each repetition has the same number of CCEs
and coded bits, and corresponds to the same DCI payload.

Polar coding is used for PDCCH.

Each resource element group carrying PDCCH carries its own DMRS.

QPSK modulation is used for PDCCH.