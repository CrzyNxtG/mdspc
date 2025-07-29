### 5.3.4 Random access

Random access preamble sequences, of four different lengths are
supported. Sequence length 839 is applied with subcarrier spacings of
1.25 and 5 kHz, sequence length 139 is applied with subcarrier spacings
of 15, 30, 60, 120, 480, and 960 kHz, sequence length of 571 is applied
with subcarrier spacings of 30, 120, and 480 kHz, and sequence length
1151 is applied with subcarrier spacings of 15 and 120 kHz. Sequence
length 839 supports unrestricted sets and restricted sets of Type A and
Type B, while sequence lengths 139, 571, and 1151 support unrestricted
sets only. Sequence length 839 is only used for operation with licensed
channel access while sequence length 139 can be used for operation with
either licensed or shared spectrum channel access. For FR1, sequence
lengths of 571 and 1151 can be used only for operation with shared
spectrum channel access. For FR2-2, sequence lengths of 571 can be used
for operation with either licensed or shared spectrum channel access
only with subcarrier spacings of 120 kHz and 480 kHz and sequence
lengths of 1151 can be used for operation with either licensed or shared
spectrum channel access only with subcarrier spacings of 120 kHz.

Multiple PRACH preamble formats are defined with one or more PRACH OFDM
symbols, and different CP and guard time. The PRACH preamble
configuration to use is provided to the UE in the system information.

For IAB additional random access configurations are defined. These
configurations are obtained by extending the random access
configurations defined for UEs via scaling the periodicity and/or
offsetting the time domain position of the RACH occasions.

IAB-MTs can be provided with random access configurations (as defined
for UEs or after applying the aforementioned scaling/offsetting)
different from random access configurations provided to UEs.

The UE calculates the PRACH transmit power for the retransmission of the
preamble based on the most recent estimate pathloss and power ramping
counter.

The system information provides information for the UE to determine the
association between the SSB and the RACH resources. The RSRP threshold
for SSB selection for RACH resource association is configurable by
network.