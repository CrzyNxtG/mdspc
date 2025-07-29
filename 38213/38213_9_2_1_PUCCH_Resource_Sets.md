### 9.2.1 PUCCH Resource Sets

If a UE does not have dedicated PUCCH resource configuration, provided
by *PUCCH-ResourceSet* in *PUCCH-Config*, a PUCCH resource set is
provided by *pucch-ResourceCommon* through an index to a row of Table
9.2.1-1 for transmission of HARQ-ACK information on PUCCH in an initial
UL BWP of $N_{\text{BWP}}^{\text{size}}$ PRBs. For operation in FR2-2,
*nrofPRBs* provided in *PUCCH-ConfigCommon* can also provide a number of
$N_{RB}$ RBs for the PUCCH resource set; otherwise $N_{RB} = 1$.

The PUCCH resource set includes sixteen resources, each corresponding to
a PUCCH format, a first symbol, a duration, a PRB offset
${RB}_{\text{BWP}}^{\text{offset}}$, and a cyclic shift index set for a
PUCCH transmission.

The UE transmits a PUCCH using frequency hopping if not provided
*useInterlacePUCCH-PUSCH* in *BWP-UplinkCommon*; otherwise, the UE
transmits a PUCCH without frequency hopping.

An orthogonal cover code with index 0 is used for a PUCCH resource with
PUCCH format 1 in Table 9.2.1-1 except when index 3, 7, or 11 is
indicated by *pucch-ResourceCommon* and *useInterlacePUCCH-PUSCH* in
*BWP-UplinkCommon* is provided.

The UE transmits the PUCCH using the same spatial domain transmission
filter as for a PUSCH transmission scheduled by a RAR UL grant as
described in clause 8.3.

If a UE is not provided any of *pdsch-HARQ-ACK-Codebook*,
*pdsch-HARQ-ACK-Codebook-r16*, or *pdsch-HARQ-ACK-OneShotFeedback*, the
UE generates at most one HARQ-ACK information bit.

If the UE provides HARQ-ACK information in a PUCCH transmission in
response to detecting a DCI format scheduling a PDSCH reception or
having associated HARQ-ACK information without scheduling a PDSCH
reception, the UE determines a PUCCH resource with index $r_{PUCCH}$,
$0{\leq r}_{PUCCH} \leq 15$, as
$r_{PUCCH} = \left\lfloor \frac{2{\cdot n}_{CCE,0}}{N_{CCE}} \right\rfloor + 2 \cdot \mathrm{\Delta}_{PRI}$,
where $N_{CCE}$ is a number of CCEs in a CORESET of a PDCCH reception
with the DCI format, as described in clause 10.1, $n_{CCE,0}$ is the
index of a first CCE for the PDCCH reception, and
$\mathrm{\Delta}_{PRI}$ is a value of the PUCCH resource indicator field
in the DCI format.

When the PDCCH reception by a UE includes first and second PDCCH
candidates from respective first and second search space sets, as
described in clause 10.1, the CORESET and $n_{CCE,0}$ are associated
with the search space set having the smaller index. If

\- the first search space set has larger index than the second search
space set and includes the first PDCCH candidate and a third PDCCH
candidate that have same first CCE index and CCE aggregation levels 8
and 16, or 16 and 8, respectively,

\- the second search space set includes the second PDCCH candidate that
has same index and same CCE aggregation level as the first PDCCH
candidate, and a fourth PDCCH candidate that has same index and same CCE
aggregation level as the third PDCCH candidate,

\- the CORESET associated with the first search space set has
*cce-REG-MappingType* = \'*nonInterleaved*\' and has duration of one
symbol, and

\- the second PDCCH candidate has different first CCE index than the
fourth PDCCH candidate

the UE determines $n_{CCE,0}$ from the PDCCH candidate with CCE
aggregation level 16 among the second PDCCH candidate and the fourth
PDCCH candidate.

If $\left\lfloor \frac{r_{\text{PUCCH}}}{8} \right\rfloor = 0$ and a UE
is provided a PUCCH resource by *pucch-ResourceCommon* and is not
provided *useInterlacePUCCH-PUSCH* in *BWP-UplinkCommon*

\- the UE determines the lowest PRB index of the PUCCH transmission in
the first hop as
${RB}_{\text{BWP}}^{\text{offset}} \cdot N_{RB} + \left\lfloor \frac{r_{\text{PUCCH}}}{N_{CS}} \right\rfloor \bullet N_{RB}$
and the lowest PRB index of the PUCCH transmission in the second hop as
${N_{\text{BWP}}^{\text{size}} - RB}_{\text{BWP}}^{\text{offset}} \bullet N_{RB} - \left( 1 + \left\lfloor \frac{r_{\text{PUCCH}}}{N_{CS}} \right\rfloor \right) \bullet N_{RB}$,
where $N_{CS}$ is the total number of initial cyclic shift indexes in
the set of initial cyclic shift indexes

\- the UE determines the initial cyclic shift index in the set of
initial cyclic shift indexes as $r_{\text{PUCCH}}\text{mod}N_{CS}$

If $\left\lfloor \frac{r_{\text{PUCCH}}}{8} \right\rfloor = 1$ and a UE
is provided a PUCCH resource by *pucch-ResourceCommon* and is not
provided *useInterlacePUCCH-PUSCH* in *BWP-UplinkCommon*

\- the UE determines the lowest PRB index of the PUCCH transmission in
the first hop as
${N_{\text{BWP}}^{\text{size}} - RB}_{\text{BWP}}^{\text{offset}} \bullet N_{RB} - \left( 1 + \left\lfloor \frac{\left( r_{\text{PUCCH}} - 8 \right)}{N_{CS}} \right\rfloor \right) \bullet N_{RB}$
and the lowest PRB index of the PUCCH transmission in the second hop as
${RB}_{\text{BWP}}^{\text{offset}} \bullet N_{RB} + \left\lfloor \frac{\left( r_{\text{PUCCH}} - 8 \right)}{N_{CS}} \right\rfloor \bullet N_{RB}$

\- the UE determines the initial cyclic shift index in the set of
initial cyclic shift indexes as
![](media/image65.wmf){width="1.1041666666666667in" height="0.21875in"}

If a UE is provided a PUCCH resource by *pucch-ResourceCommon* and is
provided *useInterlacePUCCH-PUSCH* in *BWP-UplinkCommon*

\- the UE determines for the PUCCH resource an interlace index $m$ as
$m = \left( m_{0} + \left\lfloor \frac{r_{\text{PUCCH}}}{N_{\text{CS}}} \right\rfloor \right)\text{mod}M$
where $M$ is a number of interlaces \[4, TS 38.211\] and
$m_{0} = {RB}_{\text{BWP}}^{\text{offset}}$ is an interlace index offset
and ${RB}_{\text{BWP}}^{\text{offset}}$ is as given in Table 9.2.1-1

\- the UE determines an initial cyclic shift index in a set of initial
cyclic shift indexes as $r_{\text{PUCCH}}\text{mod}N_{\text{CS}}$, where
$N_{\text{CS}}$ is the total number of initial cyclic shifts indexes in
the set of initial cyclic shift indexes in Table 9.2.1-1

\- if *pucch-ResourceCommon* indicates

\- index 0: the first symbol is 9 for a PUCCH resource with PUCCH format
0 if $r_{\text{PUCCH}} \geq 10$

\- index 1 or 2: the first symbol is 9 for a PUCCH resource with PUCCH
format 0 if $r_{\text{PUCCH}} = 15$

\- index 3, 7, or 11: an orthogonal cover code with index 1 is used for
a PUCCH resource with PUCCH format 1 if $r_{\text{PUCCH}} \geq 10$;
otherwise, an orthogonal cover code with index 0 is used for a PUCCH
resource with PUCCH format 1

\- the UE does not expect *pucch-ResourceCommon* to indicate index 15

Table 9.2.1-1: PUCCH resource sets before dedicated PUCCH resource
configuration

  --------------------------------------------------------------------------------------------------------------------------------------
  Index     **PUCCH      **First     **Number of              **PRB offset** ${RB}_{\text{BWP}}^{\text{offset}}$              **Set of
            format**    symbol**      symbols**                                                                              initial CS
                                                                                                                             indexes**
  ------- ------------ ----------- ---------------- ----------------------------------------------------------------------- ------------
  0            0           12             2                                            0                                       {0, 3}

  1            0           12             2                                            0                                     {0, 4, 8}

  2            0           12             2                                            3                                     {0, 4, 8}

  3            1           10             4                                            0                                       {0, 6}

  4            1           10             4                                            0                                    {0, 3, 6, 9}

  5            1           10             4                                            2                                    {0, 3, 6, 9}

  6            1           10             4                                            4                                    {0, 3, 6, 9}

  7            1            4             10                                           0                                       {0, 6}

  8            1            4             10                                           0                                    {0, 3, 6, 9}

  9            1            4             10                                           2                                    {0, 3, 6, 9}

  10           1            4             10                                           4                                    {0, 3, 6, 9}

  11           1            0             14                                           0                                       {0, 6}

  12           1            0             14                                           0                                    {0, 3, 6, 9}

  13           1            0             14                                           2                                    {0, 3, 6, 9}

  14           1            0             14                                           4                                    {0, 3, 6, 9}

  15           1            0             14         $$\left\lfloor \frac{N_{\text{BWP}}^{\text{size}}}{4} \right\rfloor$$  {0, 3, 6, 9}
  --------------------------------------------------------------------------------------------------------------------------------------

If a UE has dedicated PUCCH resource configuration, the UE is provided
by higher layers with one or more PUCCH resources.

A PUCCH resource includes the following parameters:

\- a PUCCH resource index provided by *pucch-ResourceId*

\- an index of the first PRB prior to frequency hopping or for no
frequency hopping by *startingPRB*, if a UE is not provided
*useInterlacePUCCH-PUSCH* in *BWP-UplinkDedicated*

\- an index of the first PRB after frequency hopping by *secondHopPRB*,
if a UE is not provided *useInterlacePUCCH-PUSCH* in
*BWP-UplinkDedicated*

\- an indication for intra-slot frequency hopping by
*intraSlotFrequencyHopping*, if a UE is not provided
*useInterlacePUCCH-PUSCH* in *BWP-UplinkDedicated*

\- an index of a first interlace by *interlace0*, if a UE is provided
*useInterlacePUCCH-PUSCH* in *BWP-UplinkDedicated*

\- if provided, an index of a second interlace by *interlace1*, if a UE
is provided *useInterlacePUCCH-PUSCH* in *BWP-UplinkDedicated*

\- an index of an RB set by *rb-SetIndex*, if a UE is provided
*useInterlacePUCCH-PUSCH* in *BWP-UplinkDedicated*

\- an indication for applying one or both of *TCI-State* or
*TCI-UL-State* by *applyIndicatedTCI-State*, if provided

\- a configuration for a PUCCH format provided by *format*

For operation with shared spectrum channel access, the UE does not
expect that two hops of a PUCCH transmission are in different RB sets.

The UE expects that *useInterlacePUCCH-PUSCH* in *BWP-UplinkCommon* and
*useInterlacePUCCH-PUSCH* in *BWP-UplinkDedicated* are provided either
in all UL BWPs or in none of the UL BWPs for a serving cell.

If a UE is provided *useInterlacePUCCH-PUSCH* in *BWP-UplinkDedicated*,
the UE determines available RBs for PUCCH transmissions within the
active UL BWP as the intersection of RBs corresponding to an interlace
index provided by *interlace0* and, if provided, *interlace1*, and RBs
of an RB set provided by *rb-SetIndex*. The intersection results in
$M_{\text{interlace,0}}^{\text{PUCCH}}$ RBs in the first interlace and
the UE expects that $M_{\text{interlace,0}}^{\text{PUCCH}}$ is either 10
or 11. If *interlace1* is provided, the intersection results in
$M_{\text{interlace,1}}^{\text{PUCCH}}$ RBs in the second interlace and
the UE expects that $M_{\text{interlace,1}}^{\text{PUCCH}}$ is either 10
or 11.

If the *format* indicates *PUCCH-format0*, the PUCCH format configured
for a PUCCH resource is PUCCH format 0, where the PUCCH resource also
includes an index for an initial cyclic shift provided by
*initialCyclicShift*, a number of symbols for a PUCCH transmission
provided by *nrofSymbols*, a first symbol for the PUCCH transmission
provided by *startingSymbolIndex*. For PUCCH transmission in FR2-2, the
PUCCH resource can also include a number of PRBs
$M_{\text{RB}}^{\text{PUCCH,}0}$ provided by *nrofPRBs*; otherwise,
$M_{\text{RB}}^{\text{PUCCH,}0} = 1$*.*

If the *format* indicates *PUCCH-format1*, the PUCCH format configured
for a PUCCH resource is PUCCH format 1, where the PUCCH resource also
includes an index for an initial cyclic shift provided by
*initialCyclicShift*, a number of symbols for a PUCCH transmission
provided by *nrofSymbols*, a first symbol for the PUCCH transmission
provided by *startingSymbolIndex*, and an index for an orthogonal cover
code by *timeDomainOCC*. For PUCCH transmission in FR2-2, the PUCCH
resource can also include a number of PRBs
$M_{\text{RB}}^{\text{PUCCH,}1}$ provided by *nrofPRBs*; otherwise,
$M_{\text{RB}}^{\text{PUCCH,}1} = 1$*.*

If the *format* indicates *PUCCH-format2* or *PUCCH-format3*, the PUCCH
format configured for a PUCCH resource is PUCCH format 2 or PUCCH format
3, respectively, where the PUCCH resource also includes a number of PRBs
provided by *nrofPRBs*, a number of symbols for a PUCCH transmission
provided by *nrofSymbols*, and a first symbol for the PUCCH transmission
provided by *startingSymbolIndex*. If a UE is provided by
*useInterlacePUCCH-PUSCH* in *BWP-UplinkDedicated,* and the *format*
indicates *PUCCH-format2* or *PUCCH-format3* and *PUCCH-ResourceExt* is
provided, the PUCCH resource also includes an index of a second
interlace by *interlace1*, if provided; otherwise, if *interlace1* is
not provided, the PUCCH resource also includes, if provided, an
orthogonal cover code length by *occ-Length* and an orthogonal cover
code index by *occ-Index*. If the *format* indicates *PUCCH-format3* and
*PUCCH-ResourceExt* is provided, the UE assumes that the
$M_{\text{RB}}^{\text{PUCCH,}3}$ \[4, TS 38.211\] PRBs with the lowest
indexes within the first, and if configured, second interlace are used
for PUCCH transmission.

If the *format* indicates *PUCCH-format4*, the PUCCH format configured
for a PUCCH resource is PUCCH format 4, where the PUCCH resource also
includes a number of symbols for a PUCCH transmission provided by
*nrofSymbols*, an orthogonal cover code length by *occ-Length*, an
orthogonal cover code index by *occ-Index*, and a first symbol for the
PUCCH transmission provided by *startingSymbolIndex*. For PUCCH
transmission in FR2-2, the PUCCH resource can also include a number of
PRBs $M_{\text{RB}}^{\text{PUCCH,}4}$ provided by *nrofPRBs*; otherwise,
$M_{\text{RB}}^{\text{PUCCH,}4} = 1$*.*

If a UE is provided *subslotLengthForPUCCH* in a *PUCCH-Config*, the
first symbol of a PUCCH resource provided by *PUCCH-ResourceSet* or
*SPS-PUCCH-AN-List* in *PUCCH-Config* or by *n1PUCCH-AN* in SPS-Config
for multiplexing HARQ-ACK in a PUCCH transmission is relative to the
first symbol of the *subslotLengthForPUCCH* symbols \[12, TS 38.331\].
For the remaining cases, the first symbol of a PUCCH resource is
relative to the first symbol of a slot with
$N_{\text{sym}}^{\text{slot}}$ symbols \[4, TS 38.211\].

A UE can be configured up to four sets of PUCCH resources in a
*PUCCH-Config*. A PUCCH resource set is provided by *PUCCH-ResourceSet*
and is associated with a PUCCH resource set index provided by
*pucch-ResourceSetId*, with a set of PUCCH resource indexes provided by
*resourceList* that provides a set of *pucch-ResourceId* used in the
PUCCH resource set, and with a maximum number of UCI information bits
the UE can transmit using a PUCCH resource in the PUCCH resource set
provided by *maxPayloadSize*. For the first PUCCH resource set, the
maximum number of UCI information bits is 2. A maximum number of PUCCH
resource indexes for a set of PUCCH resources is provided by
*maxNrofPUCCH-ResourcesPerSet*. The maximum number of PUCCH resources in
the first PUCCH resource set is 32 and the maximum number of PUCCH
resources in the other PUCCH resource sets is 8.

If the UE transmits $O_{\text{UCI}}$ UCI information bits, that include
HARQ-ACK information bits, the UE determines a PUCCH resource set to be

\- a first set of PUCCH resources with *pucch-ResourceSetId* = 0 if
$O_{\text{UCI}} \leq 2$ including 1 or 2 HARQ-ACK information bits and a
positive or negative SR on one SR transmission occasion if transmission
of HARQ-ACK information and SR occurs simultaneously, or

\- a second set of PUCCH resources with *pucch-ResourceSetId* = 1, if
provided by higher layers, if ${2 < O}_{\text{UCI}} \leq N_{2}$ where
$N_{2}$ is equal to *maxPayloadSize* if *maxPayloadSize* is provided for
the PUCCH resource set with *pucch-ResourceSetId* = 1; otherwise $N_{2}$
is equal to 1706, or

\- a third set of PUCCH resources with *pucch-ResourceSetId* = 2, if
provided by higher layers, if ${N_{2} < O}_{\text{UCI}} \leq N_{3}$
where $N_{3}$ is equal to *maxPayloadSize* if *maxPayloadSize* is
provided for the PUCCH resource set with *pucch-ResourceSetId* = 2;
otherwise $N_{3}$ is equal to 1706, or

\- a fourth set of PUCCH resources with *pucch-ResourceSetId* = 3, if
provided by higher layers, if ${N_{3} < O}_{\text{UCI}} \leq 1706$.

If the UE is provided *SPS-PUCCH-AN-List* and transmits $O_{\text{UCI}}$
UCI information bits that include only HARQ-ACK information bits in
response to one or more SPS PDSCH receptions and SR, if any, the UE
determines a PUCCH resource to be

\- a PUCCH resource provided by *sps-PUCCH-AN-ResourceID* obtained from
the first entry in *sps-PUCCH-AN-List* if $O_{\text{UCI}} \leq 2$
including 1 or 2 HARQ-ACK information bits and a positive or negative SR
on one SR transmission occasion if transmission of HARQ-ACK information
and SR occurs simultaneously, or

\- a PUCCH resource provided by *sps-PUCCH-AN-ResourceID* obtained from
the second entry in *sps-PUCCH-AN-List*, if provided, if
$2 < O_{\text{UCI}} \leq N_{1,SPS}$ where $N_{1,SPS}$ is either provided
by *maxPayloadSize* obtained from the second entry in
*sps-PUCCH-AN-List* or is otherwise equal to 1706, or

\- a PUCCH resource provided by *sps-PUCCH-AN-ResourceID* obtained from
the third entry in *sps-PUCCH-AN-List*, if provided, if
$N_{1,SPS} < O_{\text{UCI}} \leq N_{2,SPS}$ where $N_{2,SPS}$ is either
provided by *maxPayloadSize* obtained from the third entry in
*sps-PUCCH-AN-List* or is otherwise equal to 1706, or

\- a PUCCH resource provided by *sps-PUCCH-AN-ResourceID* obtained from
the fourth entry in *sps-PUCCH-AN-List*, if provided, if
$N_{2,SPS} < O_{\text{UCI}} \leq N_{3,SPS}$ where $N_{3,SPS}$ is equal
to 1706.