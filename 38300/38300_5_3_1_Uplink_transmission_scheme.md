### 5.3.1 Uplink transmission scheme

Two transmission schemes are supported for PUSCH: codebook based
transmission and non-codebook based transmission.

For codebook based transmission, the gNB provides the UE with a transmit
precoding matrix indication in the DCI. The UE uses the indication to
select the PUSCH transmit precoder from the codebook. For non-codebook
based transmission, the UE determines its PUSCH precoder based on
wideband SRI field from the DCI.

DMRS based spatial multiplexing is supported for PUSCH. Up to 8, 12, 16,
and 24 orthogonal UL DMRS ports are supported for type 1, type 2,
enhanced type 1, and enhanced type 2 DMRS respectively. For a given UE,
up to 4 or up to 8 layer transmissions are supported. The number of code
words is one for 1 to 4 layer transmission and two for 5 to 8 layer
transmission. When transform precoding is used, only a single MIMO layer
transmission is supported.

Transmission durations from 1 to 14 symbols in a slot is supported.

Aggregation of multiple slots with TB repetition is supported.

Two types of frequency hopping are supported, intra-slot frequency
hopping, and in case of slot aggregation, inter-slot frequency hopping.
Intra-slot and inter-slot frequency hopping are not supported when PRB
interlace uplink transmission waveform is used.

PUSCH may be scheduled with DCI on PDCCH, or a semi-static configured
grant may be provided over RRC, where two types of operation are
supported:

\- The first PUSCH is triggered with a DCI, with subsequent PUSCH
transmissions following the RRC configuration and scheduling received on
the DCI, or

\- The PUSCH is triggered by data arrival to the UE\'s transmit buffer
and the PUSCH transmissions follow the RRC configuration.