### 5.1.4 PDSCH resource mapping

When receiving the PDSCH scheduled with SI-RNTI and the system
information indicator in DCI is set to 0, the UE shall assume that no
SS/PBCH block, after puncturing if applicable, is transmitted in REs
used by the UE for a reception of the PDSCH.

When receiving the PDSCH scheduled with SI-RNTI and the system
information indicator in DCI is set to 1, RA-RNTI, MSGB-RNTI, P-RNTI or
TC-RNTI, the UE assumes SS/PBCH block transmission according to
*ssb-PositionsInBurst*, and if the PDSCH resource allocation overlaps
with PRBs containing SS/PBCH block transmission resources the UE shall
assume that the PRBs containing SS/PBCH block transmission resources,
after puncturing if applicable, are not available for PDSCH in the OFDM
symbols where SS/PBCH block is transmitted.

A UE expects a configuration provided by *ssb-PositionsInBurst* in
*ServingCellConfigCommon* to be same as a configuration provided by
*ssb-PositionsInBurst* in *SIB1*.

When receiving PDSCH scheduled by PDCCH with CRC scrambled by C-RNTI,
MCS-C-RNTI, CS-RNTI, G-RNTI, G-CS-RNTI, MCCH-RNTI, Multicast MCCH-RNTI
or PDSCHs with SPS, the REs corresponding to the configured or
dynamically indicated resources in Clauses 5.1.4.1, 5.1.4.2 are not
available for PDSCH. Furthermore, the UE assumes SS/PBCH block
transmission according to *ssb-PositionsInBurst* if the PDSCH resource
allocation overlaps with PRBs containing SS/PBCH block transmission
resources, after puncturing if applicable, and the UE shall assume that
the PRBs containing SS/PBCH block transmission resources, after
puncturing if applicable, are not available for PDSCH in the OFDM
symbols where SS/PBCH block associated with the same PCI is transmitted.

A UE is not expected to handle the case where PDSCH DM-RS REs are
overlapping, even partially, with any RE(s) not available for PDSCH*.*

For operation with shared spectrum channel access, SS/PBCH block
transmission according to *ssb-PositionsInBurst* represents all of the
candidate SS/PBCH blocks corresponding to SS/PBCH block indices provided
by *ssb-PositionsInBurst* as described in Clause 4.1 of \[6, TS
38.213\].