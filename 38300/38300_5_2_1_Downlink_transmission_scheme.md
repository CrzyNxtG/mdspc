### 5.2.1 Downlink transmission scheme

Demodulation Reference Signal (DMRS) based spatial multiplexing is
supported for Physical Downlink Shared Channel (PDSCH). Up to 8, 12, 16
and 24 orthogonal DL DMRS ports are supported for type 1, type 2,
enhanced type 1, and enhanced type 2 DMRS respectively. Up to 8
orthogonal DL DMRS ports per UE are supported for SU-MIMO and up to 4
orthogonal DL DMRS ports per UE are supported for MU-MIMO. The number of
SU-MIMO code words is one for 1-4 layer transmissions and two for 5-8
layer transmissions.

The DMRS and corresponding PDSCH are transmitted using the same
precoding matrix and the UE does not need to know the precoding matrix
to demodulate the transmission. The transmitter may use different
precoder matrix for different parts of the transmission bandwidth,
resulting in frequency selective precoding. The UE may also assume that
the same precoding matrix is used across a set of Physical Resource
Blocks (PRBs) denoted Precoding Resource Block Group (PRG).

Transmission durations from 2 to 14 symbols in a slot is supported.

Aggregation of multiple slots with Transport Block (TB) repetition is
supported.