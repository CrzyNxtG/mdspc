## 8.3 PUSCH scheduled by RAR UL grant

An active UL BWP with SCS configuration $\mu$, as described in clause 12
and in \[4, TS 38.211\], for a PUSCH transmission scheduled by a RAR UL
grant is indicated by higher layers.

If *useInterlacePUCCH-PUSCH* is not provided by *BWP-UplinkCommon* and
*BWP-UplinkDedicated*, for determining the frequency domain resource
allocation for the PUSCH transmission within the active UL BWP

\- if the active UL BWP and the initial UL BWP have same SCS and same CP
length and the active UL BWP includes all RBs of the initial UL BWP, or
the active UL BWP is the initial UL BWP, the initial UL BWP is used

\- else, the RB numbering starts from the first RB of the active UL BWP
and the maximum number of RBs for frequency domain resource allocation
equals the number of RBs in the initial UL BWP

The frequency domain resource allocation is by uplink resource
allocation type 1 \[6, TS 38.214\]. For an initial UL BWP size of
$N_{\text{BWP}}^{\text{size}}$ RBs, a UE processes the frequency domain
resource assignment field as follows

\- if $N_{\text{BWP}}^{\text{size}} \leq 180$, or for operation with
shared spectrum channel access in FR1 or for FR2-2 when
*ChannelAccessMode2-r17* is provided if
$N_{\text{BWP}}^{\text{size}} \leq 90$

\- truncate the frequency domain resource assignment field to its
$\left\lceil \text{log}_{2}\left( \frac{N_{\text{BWP}}^{\text{size}} \bullet \left( N_{\text{BWP}}^{\text{size}} + 1 \right)}{2} \right) \right\rceil$
least significant bits and interpret the truncated frequency resource
assignment field as for the frequency resource assignment field in DCI
format 0_0 as described in \[5, TS 38.212\]

\- else

\- insert

\-
$\left\lceil \text{log}_{2}\left( \frac{N_{\text{BWP}}^{\text{size}} \bullet \left( N_{\text{BWP}}^{\text{size}} + 1 \right)}{2} \right) \right\rceil - 12$
most significant bits, for operation with shared spectrum channel access
in FR1 or for FR2-2 when *ChannelAccessMode2-r17* is provided;

\-
$\left\lceil \text{log}_{2}\left( \frac{N_{\text{BWP}}^{\text{size}} \bullet \left( N_{\text{BWP}}^{\text{size}} + 1 \right)}{2} \right) \right\rceil - 14$
most significant bits, otherwise;

> with value set to \'0\' after the $N_{UL,hop}$ bits to the frequency
> domain resource assignment field, where $N_{UL,hop} = 0$ if the
> frequency hopping flag is set to \'0\' and $N_{UL,hop}$ is provided in
> Table 8.3-1 if the hopping flag bit is set to \'1\', and interpret the
> expanded frequency resource assignment field as for the frequency
> resource assignment field in DCI format 0_0 as described in \[5, TS
> 38.212\]

\- end if

If *useInterlacePUCCH-PUSCH* is provided by *BWP-UplinkCommon* or
*BWP-UplinkDedicated*, the frequency domain resource allocation is by
uplink resource allocation type 2 \[6, TS 38.214\]. A UE processes the
frequency domain resource assignment field as follows

\- truncate the frequency domain resource assignment field to the
$X = 6$ LSBs if $\mu = 0$, or to the $X = 5$ LSBs if $\mu = 1$

\- for interlace allocation of a PUSCH transmission, interpret the $X$
MSBs of the truncated frequency domain resource assignment field for the
active UL BWP as for the $X$ MSBs of the frequency domain resource
assignment field in DCI format 0_0 \[6, TS 38.214\]

\- for RB set allocation of a PUSCH transmission, the RB set of the
active UL BWP is the RB set of the PRACH transmission associated with
the RAR UL grant. The UE assumes that the RB set is defined as when the
UE is not provided *intraCellGuardBandsUL-List* \[6, TS 38.214\].

A UE determines whether or not to apply transform precoding as described
in \[6, TS 38.214\].

For a PUSCH transmission with frequency hopping scheduled by RAR UL
grant or for a Msg3 PUSCH retransmission, the frequency offset for the
second hop \[6, TS 38.214\] is given in Table 8.3-1.

Table 8.3-1: Frequency offset for second hop of PUSCH transmission with
frequency hopping scheduled by RAR UL grant or of Msg3 PUSCH
retransmission

+------------------------------------------+--------------------------------+-------------------------------------------------------------------------+
| Number of PRBs in initial UL BWP         | Value of                       | Frequency offset for 2^nd^ hop                                          |
|                                          | $\mathbf{N}_{\mathbf{UL,hop}}$ |                                                                         |
|                                          | Hopping Bits                   |                                                                         |
+==========================================+================================+=========================================================================+
| $$N_{\text{BWP}}^{\text{size}} < 50$$    | 0                              | $$\left\lfloor \frac{N_{\text{BWP}}^{\text{size}}}{2} \right\rfloor$$   |
|                                          +--------------------------------+-------------------------------------------------------------------------+
|                                          | 1                              | $$\left\lfloor \frac{N_{\text{BWP}}^{\text{size}}}{4} \right\rfloor$$   |
+------------------------------------------+--------------------------------+-------------------------------------------------------------------------+
| $$N_{\text{BWP}}^{\text{size}} \geq 50$$ | 00                             | $$\left\lfloor \frac{N_{\text{BWP}}^{\text{size}}}{2} \right\rfloor$$   |
|                                          +--------------------------------+-------------------------------------------------------------------------+
|                                          | 01                             | $$\left\lfloor \frac{N_{\text{BWP}}^{\text{size}}}{4} \right\rfloor$$   |
|                                          +--------------------------------+-------------------------------------------------------------------------+
|                                          | 10                             | $$- \left\lfloor \frac{N_{\text{BWP}}^{\text{size}}}{4} \right\rfloor$$ |
|                                          +--------------------------------+-------------------------------------------------------------------------+
|                                          | 11                             | Reserved                                                                |
+------------------------------------------+--------------------------------+-------------------------------------------------------------------------+

A SCS for the PUSCH transmission is provided by *subcarrierSpacing* in
*BWP-UplinkCommon*. A UE transmits PRACH and the PUSCH on a same uplink
carrier of a same serving cell.

A UE transmits a transport block in a PUSCH scheduled by a RAR UL grant
in a corresponding RAR message using redundancy version number 0, if the
PUSCH transmission is without repetitions. If a TC-RNTI is provided by
higher layers, the scrambling initialization of the PUSCH corresponding
to the RAR UL grant in clause 8.2 is by TC-RNTI. Otherwise, the
scrambling initialization of the PUSCH corresponding to the RAR UL grant
in clause 8.2 is by C-RNTI.

If a UE is provided *tag2-Id*, the UE transmits a transport block in a
PUSCH scheduled by a RAR UL grant in a corresponding RAR message with
timing advance corresponding to a TAG indicated by the RAR message.

Msg3 PUSCH retransmissions, if any, of the transport block, are
scheduled by a DCI format 0_0 with CRC scrambled by a TC-RNTI provided
in the corresponding RAR message \[11, TS 38.321\].

With reference to slots for a PUSCH transmission scheduled by a RAR UL
grant, if a UE receives a PDSCH with a RAR message ending in slot $n$
for a corresponding PRACH transmission from the UE, the UE transmits the
PUSCH in slot
$n + k_{2} + \mathrm{\Delta} + 2^{\mu} \bullet K_{cell,offset}$, where
$k_{2}$ and $\mathrm{\Delta}$ are provided in \[6, TS 38.214\] and
$K_{cell,offset}$ is provided by *cellSpecificKoffset*; otherwise, if
not provided, $K_{cell,offset} = 0$.

A UE can be provided in *BWP-UplinkCommon* a set of numbers of
repetitions for a PUSCH transmission with PUSCH repetition Type A that
is scheduled by a RAR UL grant or by a DCI format 0_0 with CRC scrambled
by a TC-RNTI. If the UE requests repetitions for the PUSCH transmission
\[11, TS 38.321\], the UE transmits the PUSCH over
$N_{\text{PUSCH}}^{\text{repeat}}$ slots, where
$N_{\text{PUSCH}}^{\text{repeat}}$ is indicated by the 2 MSBs of the MCS
field in the RAR UL grant or in the DCI format 0_0 from a set of four
values provided by *numberOfMsg3-RepetitionsList* or from {1, 2, 3, 4}
if *numberOfMsg3-RepetitionsList* is not provided. The UE determines an
MCS for the PUSCH transmission by the 2 LSBs of the MCS field in the RAR
UL grant or by the 3 LSBs of the MCS field in the DCI format 0_0, and
determines a redundancy version and RBs for each repetition as described
in \[6, TS 38.214\]. For unpaired spectrum operation, the UE determines
the $N_{\text{PUSCH}}^{\text{repeat}}$ slots as the first
$N_{\text{PUSCH}}^{\text{repeat}}$ slots starting from slot
$n + k_{2} + \mathrm{\Delta} + 2^{\mu} \bullet K_{cell,offset}$ where a
repetition of the PUSCH transmission does not include a symbol indicated
as downlink by *tdd-UL-DL-ConfigurationCommon* or indicated as a symbol
of an SS/PBCH block with index provided by *ssb-PositionsInBurst*, and
where $K_{cell,offset}$ is provided by *cellSpecificKoffset*; otherwise,
if not provided, $K_{cell,offset} = 0$. For paired spectrum operation,
the UE determines the $N_{\text{PUSCH}}^{\text{repeat}}$ slots as the
first $N_{\text{PUSCH}}^{\text{repeat}}$ slots starting from slot
$n + k_{2} + \mathrm{\Delta} + 2^{\mu} \bullet K_{cell,offset}$ where
$K_{cell,offset}$ is provided by *cellSpecificKoffset;* otherwise, if
not provided, $K_{cell,offset} = 0$.

The UE may assume a minimum time between the last symbol of a PDSCH
reception conveying a RAR message with a RAR UL grant and the first
symbol of a corresponding PUSCH transmission scheduled by the RAR UL
grant is equal to $N_{T,1} + N_{T,2} + 0.5$ msec, where $N_{T,1}$ is a
time duration of $N_{1}$ symbols corresponding to a PDSCH processing
time for UE processing capability 1 when additional PDSCH DM-RS is
configured, $N_{T,2}$ is a time duration of $N_{2}$ symbols
corresponding to a PUSCH preparation time for UE processing capability 1
\[6, TS 38.214\] and, for determining the minimum time, the UE considers
that $N_{1}$ and $N_{2}$ correspond to the smaller of the SCS
configurations for the PDSCH and the PUSCH. For $\mu = 0$, the UE
assumes $N_{1,0} = 14$ \[6, TS 38.214\].