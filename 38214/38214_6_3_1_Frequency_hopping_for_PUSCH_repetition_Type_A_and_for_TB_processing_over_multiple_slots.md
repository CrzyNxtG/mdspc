### 6.3.1 Frequency hopping for PUSCH repetition Type A and for TB processing over multiple slots

For PUSCH repetition Type A other than the PUSCH scheduled by RAR UL
grant or fallbackRAR UL grant or by DCI format 0_0 with CRC scrambled by
TC-RNTI and for TB processing over multiple slots (as determined
according to procedures defined in Clause 6.1.2.1 for scheduled PUSCH,
or Clause 6.1.2.3 for configured PUSCH), a UE is configured for
frequency hopping by the higher layer parameter
*frequencyHoppingDCI-0-2* in *pusch-Config* for PUSCH transmission
scheduled by DCI format 0_2, and by *frequencyHopping* provided in
*pusch-Config* for PUSCH transmission scheduled by a DCI format other
than 0_2*,* and by *frequencyHopping* provided in
*configuredGrantConfig* for configured PUSCH transmission. For PUSCH
repetition Type A scheduled by RAR UL grant or by DCI format 0_0 with
CRC scrambled by TC-RNTI, a UE is configured for frequency hopping by
the frequency hopping flag information field of the RAR UL grant, and by
the frequency hopping flag information field of DCI format 0_0 with CRC
scrambled by TC-RNTI, respectively. One of two frequency hopping modes
can be configured:

\- Intra-slot frequency hopping, applicable to single slot and
multi-slot configured PUSCH transmission, multi-slot PUSCH transmission
scheduled by DCI format 0_1, 0_2 or 0_3, each of multiple PUSCH
transmissions on a serving cell scheduled by a DCI if the higher layer
parameter *pusch-TimeDomainAllocationListForMultiPUSCH* is configured
and each of multiple configured grant PUSCH transmissions in a
configuration where the higher layer parameters *cg-nrofSlots* and
*cg-nrofPUSCH-InSlot* are provided.

\- Inter-slot frequency hopping, applicable to multi-slot PUSCH
transmission.

For operation with shared spectrum channel access in FR1, the UE does
not expect that two hops of a PUSCH transmission are in different RB
sets.

In case of resource allocation type 2, the UE transmits PUSCH without
frequency hopping.

In case of resource allocation type 1, whether or not transform
precoding is enabled for PUSCH transmission, the UE may perform PUSCH
frequency hopping, if the frequency hopping field in a corresponding
detected DCI format or in a random access response UL grant is set to 1,
or if for a Type 1 PUSCH transmission with a configured grant the higher
layer parameter *frequencyHoppingOffset* is provided, otherwise no PUSCH
frequency hopping is performed. When frequency hopping is enabled for
PUSCH, the RE mapping is defined in clause 6.3.1.6 of \[4, TS 38.211\].

For a PUSCH scheduled by RAR UL grant, fallbackRAR UL grant, or by DCI
format 0_0 with CRC scrambled by TC-RNTI, frequency offsets are obtained
as described in clause 8.3 of \[6, TS 38.213\]. Otherwise, for a PUSCH
scheduled by DCI format 0_0/0_1/0_3 or a PUSCH based on a Type2
configured UL grant activated by DCI format 0_0/0_1 and for resource
allocation type 1, frequency offsets are configured by higher layer
parameter *frequencyHoppingOffsetLists* in *pusch-Config*. For a PUSCH
scheduled by DCI format 0_2 or a PUSCH based on a Type2 configured UL
grant activated by DCI format 0_2 and for resource allocation type 1,
frequency offsets are configured by higher layer parameter
*frequencyHoppingOffsetListsDCI-0-2* in *pusch-Config*.

\- When the size of the active BWP is less than 50 PRBs, one of two
higher layer configured offsets is indicated in the UL grant.

\- When the size of the active BWP is equal to or greater than 50 PRBs,
one of four higher layer configured offsets is indicated in the UL
grant.

For PUSCH based on a Type1 configured UL grant the frequency offset is
provided by the higher layer parameter *frequencyHoppingOffset* in
*rrc-ConfiguredUplinkGrant*.

For a MsgA PUSCH the frequency offset is provided by the higher layer
parameter as described in \[6, TS 38.213\].

In case of intra-slot frequency hopping, the starting RB in each hop is
given by:

![](media/image791.wmf),

where *i*=0 and *i*=1 are the first hop and the second hop respectively,
and ![](media/image792.wmf) is the starting RB within the UL BWP, as
calculated from the resource block assignment information of resource
allocation type 1 (described in Clause 6.1.2.2.2) or as calculated from
the resource assignment for MsgA PUSCH (described in \[6, TS 38.213\])
and ![](media/image793.wmf)is the frequency offset in RBs between the
two frequency hops. The number of symbols in the first hop is given by
![](media/image794.wmf), the number of symbols in the second hop is
given by ![](media/image795.wmf), where $N_{symb}^{PUSCH,s}$ is the
length of the PUSCH transmission in OFDM symbols in one slot.

In case of inter-slot frequency hopping and when *pusch-DMRS-Bundling*
is not enabled, or for inter-slot frequency hopping for a PUSCH
scheduled by RAR UL grant or DCI format 0_0 with CRC scrambled by
TC-RNTI, the starting RB during slot ![](media/image796.wmf) is given
by:

![](media/image797.wmf),

where ![](media/image798.wmf) is the current slot number within a system
radio frame, where a multi-slot PUSCH transmission can take place,
![](media/image799.wmf) is the starting RB within the UL BWP, as
calculated from the resource block assignment information of resource
allocation type 1 (described in Clause 6.1.2.2.2) and
![](media/image800.wmf)is the frequency offset in RBs between the two
frequency hops.

In case of inter-slot frequency hopping and when *pusch-DMRS-Bundling*
is enabled, and when a PUSCH is not scheduled by RAR UL grant or DCI
format 0_0 with CRC scrambled by TC-RNTI, the starting RB during slot
![](media/image796.wmf) is given by:

${RB}_{start}\left( n_{s}^{\mu} \right) = \left\{ \begin{array}{r}
{RB}_{start} \\
\left( {RB}_{start} + {RB}_{offset} \right)modN_{BWP}^{size}
\end{array}\binom{\left\lfloor \frac{n_{s}^{\mu}}{N_{FH}} \right\rfloor\ mod\ 2 = 0}{\left\lfloor \frac{n_{s}^{\mu}}{N_{FH}} \right\rfloor\ mod\ 2 = 1} \right.\ $

where $n_{s}^{\mu}$ is the current slot number within a system radio
frame, $N_{FH}$ is the value of the higher layer parameter
*pusch-FrequencyHoppingInterval*, ![](media/image799.wmf) is the
starting RB within the UL BWP, as calculated from the resource block
assignment information of resource allocation type 1 (described in
Clause 6.1.2.2.2) and![](media/image800.wmf)is the frequency offset in
RBs between the two frequency hops.