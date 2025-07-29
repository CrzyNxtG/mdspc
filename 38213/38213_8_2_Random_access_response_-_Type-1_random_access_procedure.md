## 8.2 Random access response - Type-1 random access procedure

In response to a PRACH transmission, a UE attempts to detect a DCI
format 1_0 with CRC scrambled by a corresponding RA-RNTI during a window
controlled by higher layers \[11, TS 38.321\] if the PRACH transmission
is not triggered by a PDCCH order that includes a Cell Indicator field
with non-zero value; otherwise, the UE does not attempt to detect the
DCI format 1_0. The window starts at the first symbol of the earliest
CORESET the UE is configured to receive PDCCH for Type1-PDCCH CSS set,
as defined in clause 10.1, that is at least one symbol, after the last
symbol of the last PRACH occasion corresponding to the PRACH
transmission, where the symbol duration corresponds to the SCS for
Type1-PDCCH CSS set as defined in clause 10.1. If
$N_{\text{TA,adj}}^{\text{UE}}$ or $N_{\text{TA,adj}}^{\text{common}}$,
as defined in \[4, TS 38.211\], is not zero, the window starts after an
additional $T_{TA} + k_{mac}$ msec where $T_{TA}$ is defined in \[4, TS
38.211\] and $k_{mac}$ is provided by *kmac* or $k_{mac} = 0$ if *kmac*
is not provided. The length of the window in number of slots, based on
the SCS for Type1-PDCCH CSS set, is provided by *ra-ResponseWindow*.

If the UE detects the DCI format 1_0 with CRC scrambled by the
corresponding RA-RNTI and LSBs of a SFN field in the DCI format 1_0, if
included and applicable, are same as corresponding LSBs of the SFN where
the UE transmitted PRACH, and the UE receives a transport block in a
corresponding PDSCH within the window, the UE passes the transport block
to higher layers. The higher layers parse the transport block for a
random access preamble identity (RAPID) associated with the PRACH
transmission. If the higher layers identify the RAPID in RAR message(s)
of the transport block, the higher layers indicate an uplink grant to
the physical layer. This is referred to as random access response (RAR)
UL grant in the physical layer.

If the UE does not detect the DCI format 1_0 with CRC scrambled by the
corresponding RA-RNTI within the window, or if the UE detects the DCI
format 1_0 with CRC scrambled by the corresponding RA-RNTI within the
window and LSBs of a SFN field in the DCI format 1_0, if included and
applicable, are not same as corresponding LSBs of the SFN where the UE
transmitted PRACH, or if the UE does not correctly receive the transport
block in the corresponding PDSCH within the window, or if the higher
layers do not identify the RAPID associated with the PRACH transmission
from the UE, the higher layers can indicate to the physical layer to
transmit a PRACH. If requested by higher layers, the UE shall be ready
to transmit a PRACH no later than $N_{T,1} + 0.75$ msec after the last
symbol of the window, or the last symbol of the PDSCH reception, where
$N_{T,1}$ is a time duration of $N_{1}$ symbols corresponding to a PDSCH
processing time for UE processing capability 1 assuming $\mu$
corresponds to the smallest SCS configuration among the SCS
configurations for the PDCCH carrying the DCI format 1_0, the
corresponding PDSCH when additional PDSCH DM-RS is configured, and the
corresponding PRACH. For $\mu = 0$, the UE assumes $N_{1,0} = 14$ \[6,
TS 38.214\]. For a PRACH transmission using 1.25 kHz or 5 kHz SCS, the
UE determines $N_{1}$ assuming SCS configuration $\mu = 0$.

If the UE detects a DCI format 1_0 with CRC scrambled by the
corresponding RA-RNTI and LSBs of a SFN field in the DCI format 1_0, if
included and applicable, are same as corresponding LSBs of the SFN where
the UE transmitted the PRACH, and the UE receives a transport block in a
corresponding PDSCH, the UE may assume same DM-RS antenna port quasi
co-location properties, as described in \[6, TS 38.214\], as for a
SS/PBCH block or a CSI-RS resource the UE used for PRACH association, as
described in clause 8.1, regardless of whether or not the UE is provided
*TCI-State* for the CORESET where the UE receives the PDCCH with the DCI
format 1_0.

For the CFRA procedure triggered by LTM Cell Switch Command MAC CE, if
the UE detects a DCI format 1_0 with CRC scrambled by the corresponding
RA-RNTI and the UE receives a transport block in a corresponding PDSCH,
the UE may assume same DM-RS antenna port quasi co-location properties,
as described in \[6, TS 38.214\], as for a SS/PBCH block the UE used for
PRACH association, as described in clause 8.1.

If the UE attempts to detect the DCI format 1_0 with CRC scrambled by
the corresponding RA-RNTI in response to a PRACH transmission initiated
by a PDCCH order that triggers a contention-free random access procedure
for the SpCell \[11, TS 38.321\], the UE may assume that the PDCCH that
includes the DCI format 1_0 and the PDCCH order have same DM-RS antenna
port quasi co-location properties. If the UE attempts to detect the DCI
format 1_0 with CRC scrambled by the corresponding RA-RNTI in response
to a PRACH transmission initiated by a PDCCH order that triggers a
contention-free random access procedure for a secondary cell, or if the
UE is configured with *tag2-Id* for the SpCell and the CORESET where the
UE receives the PDCCH order that triggers a contention-free random
access procedure for the SpCell is not associated with the physical cell
ID for the serving cell, the UE may assume the DM-RS antenna port quasi
co-location properties of the CORESET associated with the Type1-PDCCH
CSS set for receiving the PDCCH that includes the DCI format 1_0 and the
PDSCH scheduled by the DCI format 1_0.

A RAR UL grant schedules a PUSCH transmission from the UE. The contents
of the RAR UL grant, starting with the MSB and ending with the LSB, are
given in Table 8.2-1.

If the value of the frequency hopping flag is 0, the UE transmits the
PUSCH without frequency hopping; otherwise, the UE transmits the PUSCH
with frequency hopping.

The UE determines the MCS of the PUSCH transmission from the first
sixteen indexes of the applicable MCS index table for PUSCH as described
in \[6, TS 38.214\].

The TPC command value $\delta_{msg2,b,f,c}$ is used for setting the
power of the PUSCH transmission, as described in clause 7.1.1, and is
interpreted according to Table 8.2-2.

The CSI request field is reserved.

The ChannelAccess-CPext field indicates a channel access type and CP
extension for operation with shared spectrum channel access \[15, TS
37.213\] in FR1 as defined in Table 7.3.1.1.1-4 in \[5, TS 38.212\] or
Table 7.3.1.1.1-4A in \[5, TS 38.212\] if *channelAccessMode* =
\"*semiStatic*\" is provided. The ChannelAccess-CPext field indicates a
channel access type for operation with shared spectrum channel access
\[15, TS 37.213\] in FR2-2 as defined in Table 7.3.1.1.1-4B in \[5, TS
38.212\] if *ChannelAccessMode2-r17* is provided.

Table 8.2-1: Random Access Response Grant Content field size

+---------------------------+------------------------------------------+
| RAR grant field           | Number of bits                           |
+:==========================+==========================================+
| Frequency hopping flag    | 1                                        |
+---------------------------+------------------------------------------+
| PUSCH frequency resource  | 12, for operation with shared spectrum   |
| allocation                | channel access in FR1 or for FR2-2 when  |
|                           | *ChannelAccessMode2-r17* is provided     |
|                           |                                          |
|                           | 14, otherwise                            |
+---------------------------+------------------------------------------+
| PUSCH time resource       | 4                                        |
| allocation                |                                          |
+---------------------------+------------------------------------------+
| MCS                       | 4                                        |
+---------------------------+------------------------------------------+
| TPC command for PUSCH     | 3                                        |
+---------------------------+------------------------------------------+
| CSI request               | 1                                        |
+---------------------------+------------------------------------------+
| ChannelAccess-CPext       | 2, for operation with shared spectrum    |
|                           | channel access in FR1 or for FR2-2 when  |
|                           | *ChannelAccessMode2-r17* is provided     |
|                           |                                          |
|                           | 0, otherwise                             |
+---------------------------+------------------------------------------+

Table 8.2-2: TPC Command
$\mathbf{\delta}_{\mathbf{msg2}\mathbf{,b,f,c}}$ for PUSCH

  -----------------------------------------------------------------------
  TPC Command                           Value (in dB)
  ------------------------------------- ---------------------------------
  0                                     -6

  1                                     -4

  2                                     -2

  3                                     0

  4                                     2

  5                                     4

  6                                     6

  7                                     8
  -----------------------------------------------------------------------

Unless the UE is configured a SCS, the UE receives subsequent PDSCH
using same SCS as for the PDSCH reception providing the RAR message.

If the UE does not detect the DCI format 1_0 with CRC scrambled by the
corresponding RA-RNTI within the window, or if the UE detects the DCI
format 1_0 with CRC scrambled by the corresponding RA-RNTI within the
window and the LSBs of a SFN field in the DCI format 1_0, if included
and applicable, are not same as corresponding LSBs of the SFN where the
UE transmitted the PRACH, or the UE does not correctly receive a
corresponding transport block within the window, the UE procedure is as
described in \[11, TS 38.321\].