## 5.33 First PUSCH transmission of RACH-less handover

The first PUSCH uplink transmission of a RACH-less handover procedure
can be performed either using a dynamic uplink grant or a configured
uplink grant Type 1 preallocated by RRC, if configured.

When *rach-LessHO* is configured, the MAC entity shall:

1\> if *cg-RRC-Configuration* is configured:

2\> select a configured uplink grant for the first PUSCH transmission
according to clause 5.8.2;

2\> perform the first PUSCH transmission in the first available CG
occasion for RACH-less handover according to clause 5.8.2;

2\> monitor the PDCCH as specified in clause 5.7 and TS 38.213 \[6\].

1\> else:

2\> if *tci-StateID* is configured in *rach-LessHO*:

3\> indicate to lower layers the TCI state information included in
*tci-StateID*.

2\> else if *ssb-Index* is configured in *rach-LessHO*:

3\> indicate to lower layers the SSB index included in *ssb-Index*.

2\> monitor the PDCCH as specified in TS 38.213 \[6\].