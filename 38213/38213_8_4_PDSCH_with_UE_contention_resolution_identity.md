## 8.4 PDSCH with UE contention resolution identity

In response to a PUSCH transmission scheduled by a RAR UL grant when a
UE has not been provided a C-RNTI, the UE attempts to detect a DCI
format 1_0 with CRC scrambled by a corresponding TC-RNTI scheduling a
PDSCH that includes a UE contention resolution identity \[11, TS
38.321\]. In response to the PDSCH reception with the UE contention
resolution identity, the UE transmits HARQ-ACK information in a PUCCH.
The PUCCH transmission is within a same active UL BWP as the PUSCH
transmission. A minimum time between the last symbol of the PDSCH
reception and the first symbol of the corresponding PUCCH transmission
with the HARQ-ACK information is equal to $N_{T,1} + 0.5$ msec.
$N_{T,1}$ is a time duration of $N_{1}$ symbols corresponding to a PDSCH
processing time for UE processing capability 1 when additional PDSCH
DM-RS is configured. For $\mu = 0$, the UE assumes $N_{1,0} = 14$ \[6,
TS 38.214\].

When detecting a DCI format in response to a PUSCH transmission
scheduled by a RAR UL grant, as described in \[11, TS 38.321\], or
corresponding PUSCH retransmission scheduled by a DCI format 0_0 with
CRC scrambled by a TC-RNTI provided in the corresponding RAR message
\[11, TS 38.321\], the UE may assume the PDCCH carrying the DCI format
has the same DM-RS antenna port quasi co-location properties, as
described in \[6, TS 38.214\], as for a SS/PBCH block the UE used for
PRACH association, as described in clause 8.1, regardless of whether or
not the UE is provided TCI-State for the CORESET where the UE receives
the PDCCH with the DCI format.