## 8.2A Random access response - Type-2 random access procedure

In response to a transmission of a PRACH and a PUSCH, or to a
transmission of only a PRACH if the PRACH preamble is mapped to a valid
PUSCH occasion, a UE attempts to detect a DCI format 1_0 with CRC
scrambled by a corresponding MsgB-RNTI during a window controlled by
higher layers \[11, TS 38.321\]. The window starts at the first symbol
of the earliest CORESET the UE is configured to receive PDCCH for
Type1-PDCCH CSS set, as defined in clause 10.1, that is at least one
symbol, after the last symbol of the PUSCH occasion corresponding to the
PRACH transmission, where the symbol duration corresponds to the SCS for
Type1-PDCCH CSS set. If $N_{\text{TA,adj}}^{\text{UE}}$ or
$N_{\text{TA,adj}}^{\text{common}}$, as defined in \[4, TS 38.211\], is
not zero, the window starts after an additional $T_{TA} + k_{mac}$ msec
where $T_{TA}$ is defined in \[4, TS 38.211\] and $k_{mac}$ is provided
by *kmac* or $k_{mac} = 0$ if *kmac* is not provided. The length of the
window in number of slots, based on the SCS for Type1-PDCCH CSS set, is
provided by *msgB-ResponseWindow*.

In response to a transmission of a PRACH, if the PRACH preamble is not
mapped to a valid PUSCH occasion, a UE attempts to detect a DCI format
1_0 with CRC scrambled by a corresponding MsgB-RNTI during a window
controlled by higher layers \[11, TS 38.321\]. The window starts at the
first symbol of the earliest CORESET the UE is configured to receive
PDCCH for Type1-PDCCH CSS set, as defined in clause 10.1, that is at
least one symbol, after the last symbol of the PRACH occasion
corresponding to the PRACH transmission, where the symbol duration
corresponds to the SCS for Type1-PDCCH CSS set. The length of the window
in number of slots, based on the SCS for Type1-PDCCH CSS set, is
provided by *msgB-ResponseWindow*.

If the UE detects the DCI format 1_0, with CRC scrambled by the
corresponding MsgB-RNTI and LSBs of a SFN field in the DCI format 1_0,
if applicable, are same as corresponding LSBs of the SFN where the UE
transmitted PRACH, and the UE receives a transport block in a
corresponding PDSCH within the window, the UE passes the transport block
to higher layers. The higher layers indicate to the physical layer

\- an uplink grant if the RAR message(s) is for fallbackRAR and a random
access preamble identity (RAPID) associated with the PRACH transmission
is identified, and the UE procedure continues as described in clauses
8.2, 8.3, and 8.4 when the UE detects a RAR UL grant, or

\- transmission of a PUCCH with HARQ-ACK information having ACK value if
the RAR message(s) is for successRAR, where

\- a PUCCH resource for the transmission of the PUCCH is indicated by
PUCCH resource indicator field of 4 bits in the successRAR from a PUCCH
resource set that is provided by *pucch-ResourceCommon*

\- a slot for the PUCCH transmission is indicated by a HARQ Feedback
Timing Indicator field of 3 bits in the successRAR having a value $k$
from {1, 2, 3, 4, 5, 6, 7, 8} for $\mu \leq 3$, from {7, 8, 12, 16, 20,
24, 28, 32} for $\mu = 5$, and from {13, 16, 24, 32, 40, 48, 56, 64} for
$\mu = 6$ and, with reference to slots for PUCCH transmission having
duration $T_{slot}$, the slot is determined as
$n + k + \mathrm{\Delta}{+ 2}^{\mu} \bullet K_{cell,offset}$, where $n$
is the last slot that overlaps with the DL slot for the PDSCH reception,
$\mathrm{\Delta}$ is as defined for PUSCH transmission in Table
6.1.2.1.1-5 of \[6, TS 38.214\], $\mu$ is the SCS configuration of the
active UL BWP, and $K_{cell,offset}$ is provided by
*cellSpecificKoffset*; otherwise, if not provided, $K_{cell,offset} = 0$

\- the UE does not expect the first symbol of the PUCCH transmission to
be after the last symbol of the PDSCH reception by a time smaller than
$N_{T,1} + 0.5$ msec where $N_{T,1}$ is the PDSCH processing time for UE
processing capability 1 \[6, TS 38.214\]

\- for operation with shared spectrum channel access in FR1, a channel
access type and CP extension \[15, TS 37.213\] for a PUCCH transmission
is indicated by a ChannelAccess-CPext field in the successRAR as defined
in Table 7.3.1.1.1-4 in \[5, TS 38.212\] or Table 7.3.1.1.1-4A in \[5,
TS 38.212\] if *channelAccessMode* = \"*semiStatic*\" is provided

\- for operation with shared spectrum channel access in FR2-2, a channel
access type \[15, TS 37.213\] for a PUCCH transmission is indicated by a
ChannelAccess-CPext field in the successRAR as defined in Table
7.3.1.1.1-4B in \[5, TS 38.212\] if *ChannelAccessMode2-r17* is provided

\- the PUCCH transmission is with a same spatial domain transmission
filter and in a same active UL BWP as a last PUSCH transmission

If the UE detects the DCI format 1_0 with CRC scrambled by a C-RNTI and
a transport block in a corresponding PDSCH within the window, the UE
transmits a PUCCH with HARQ-ACK information having ACK value if the UE
correctly detects the transport block or NACK value if the UE
incorrectly detects the transport block and the time alignment timer is
running \[11, TS 38.321\].

If the UE detects a DCI format 1_0 with CRC scrambled by the
corresponding MsgB-RNTI and receives a transport block within the window
in a corresponding PDSCH, the UE may assume same DM-RS antenna port
quasi co-location properties, as described in \[6, TS 38.214\], as for a
SS/PBCH block the UE used for PRACH association, as described in clause
8.1, regardless of whether or not the UE is provided *TCI-State* for the
CORESET where the UE receives the PDCCH with the DCI format 1_0.

The UE does not expect to be indicated to transmit the PUCCH with the
HARQ-ACK information at a time that is prior to a time when the UE
applies a TA command that is provided by the transport block. If the UE
does not detect the DCI format 1_0 with CRC scrambled by the
corresponding MsgB-RNTI within the window, or if the UE detects the DCI
format 1_0 with CRC scrambled by the corresponding MsgB-RNTI within the
window and LSBs of a SFN field in the DCI format 1_0, if applicable, are
not same as corresponding LSBs of the SFN where the UE transmitted the
PRACH, or if the UE does not correctly receive the transport block in
the corresponding PDSCH within the window, or if the higher layers do
not identify the RAPID associated with the PRACH transmission from the
UE, the higher layers can indicate to the physical layer to transmit
only PRACH according to Type-1 random access procedure or to transmit
both PRACH and PUSCH according to Type-2 random access procedure \[11,
TS 38.321\]. If requested by higher layers, the UE shall be ready to
transmit a PRACH no later than $N_{\text{T,1}} + 0.75$ msec after the
last symbol of the window, or the last symbol of the PDSCH reception,
where $N_{\text{T,1}}$ is a time duration of $N_{1}$ symbols
corresponding to a PDSCH processing time for UE processing capability 1
when additional PDSCH DM-RS is configured. For $\mu = 0$, the UE assumes
$N_{\text{1,0}} = 14$ \[6, TS 38.214\].

Unless the UE is configured a SCS, the UE receives subsequent PDSCH
using same SCS as for the PDSCH reception providing the RAR message.

If the UE does not detect the DCI format 1_0 with CRC scrambled by the
corresponding MsgB-RNTI within the window, or if the UE detects the 1_0
with CRC scrambled by the corresponding MsgB-RNTI within the window and
LSBs of a SFN field in the DCI format 1_0, if applicable, are not same
as corresponding LSBs of the SFN where the UE transmitted the PRACH, or
the UE does not correctly receive a corresponding transport block within
the window, the UE procedure is as described in \[11, TS 38.321\].