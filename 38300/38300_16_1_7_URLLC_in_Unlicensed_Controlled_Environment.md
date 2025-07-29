### 16.1.7 URLLC in Unlicensed Controlled Environment

URLLC services can be supported in shared spectrum where LBT failures
are assumed to be not frequent. In this case, a channel access procedure
for semi-static channel occupancy can be initiated by the gNB or the UE,
or the gNB operates in dynamic channel access mode, as described in TS
37.213 \[37\]. To handle potential LBT failures on configured grants
(CG), the CG retransmission timer can be optionally configured to enable
autonomous retransmissions, and it may be configured simultaneously with
enhanced intra-UE overlapping resource prioritization mechanisms. When
the CG retransmission timer is configured, the UE shall select the HARQ
process for each CG resource by itself. If the enhanced intra-UE
overlapping resource prioritization mechanisms is also configured, the
UE may be further configured to select the HARQ process for a CG
resource based on logical channel priority.