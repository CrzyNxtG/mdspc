## 6.4 UE PUSCH preparation procedure time

If the first uplink symbol in the PUSCH allocation for up to two
transport blocks, including the DM-RS, as defined by the slot offset
*K~2~* and K~offset~, if configured, and the start *S* and length *L* of
the PUSCH allocation indicated by \'*Time domain resource assignment*\'
of the scheduling DCI and including the effect of the timing advance, is
no earlier than at symbol *L~2~*, where *L~2~* is defined as the next
uplink symbol with its CP starting
$T_{proc,2} = \max\left( (N_{2} + d_{2,1} + d_{2} + d_{3} + d_{4})(2048 + 144) \cdot \kappa 2^{- \mu} \cdot T_{C} + T_{ext} + T_{switch},d_{2,2} \right)$
after the end of the reception of the last symbol of the PDCCH carrying
the DCI scheduling the PUSCH, then the UE shall transmit the PUSCH. When
the PDCCH reception includes two PDCCH candidates from two respective
search space sets, as described in clause 10.1 of \[6, TS 38.213\], for
the purpose of determining the last symbol of the PDCCH carrying the DCI
scheduling the PUSCH, the PDCCH candidate that ends later in time is
used.

*- N~2~* is based on *µ* of Table 6.4-1 and Table 6.4-2 for UE
processing capability 1 and 2 respectively, where *µ* corresponds to the
one of (*µ~DL~*, *µ~UL~*) resulting with the largest *T~proc,2~*, where
the *µ~DL~* corresponds to the subcarrier spacing of the downlink with
which the PDCCH carrying the DCI scheduling the PUSCH was transmitted
and *µ~UL~* corresponds to the subcarrier spacing of the uplink channel
with which the PUSCH is to be transmitted, and *κ* is defined in clause
4.1 of \[4, TS 38.211\].

*-* For operation with shared spectrum channel access in FR1,
![](media/image696.wmf)is calculated according to \[4, TS 38.211\],
otherwise ![](media/image696.wmf)=0.

\- If the first symbol of the PUSCH allocation consists of DM-RS only,
then *d~2,1\ ~*= 0*,* otherwise *d~2,1\ ~*= 1.

\- If the UE is configured with multiple active component carriers, the
first uplink symbol in the PUSCH allocation further includes the effect
of timing difference between component carriers as given in \[11, TS
38.133\].

\- If the scheduling DCI triggered a switch of BWP, *d~2,2~* equals to
the switching time as defined in \[11, TS 38.133\], otherwise
*d~2,2~*=0.

\- If a PUSCH of a larger priority index would overlap with a PUCCH of a
smaller priority index and the PUCCH and PUSCH are not simultaneously
transmitted, and the UE is not provided *uci-MuxWithDiffPrio* for the
primary PUCCH group or *uci-MuxWithDiffPrioSecondaryPUCCHgroup* for the
secondary PUCCH group, *d~2~* for the PUSCH of a larger priority is set
as reported by the UE; otherwise *d~2~ = 0.*

\- For a UE that supports capability 2 on a given cell, the processing
time according to UE processing capability 2 is applied if the high
layer parameter *processingType2Enabled* in *PUSCH-ServingCellConfig* is
configured for the cell and set to \'enable\'.

\- If the PUSCH indicated by the DCI is overlapping with one or more
PUCCH channels, then the transport block(s) is(are) multiplexed
following the procedure in clause 9.2.5 of \[6, TS 38.213\], otherwise
the transport block(s) is(are) transmitted on the PUSCH indicated by the
DCI.

\- If uplink switching gap is triggered as defined in clause 6.1.6,
![](media/image802.wmf) equals to the switching gap duration and for the
UE configured with higher layer parameter *uplinkTxSwitchingOption* set
to \'dualUL\' for uplink carrier aggregation
*µ~UL~*=min(*µ~UL,carrier1,~ µ~UL,carrier2~*), otherwise
![](media/image803.wmf).

*- d~3~* is set as reported by UE if the UE is configured with
*sTx-2Panel* and the PUSCH associated with a value of *coresetPoolIndex*
is fully/partially overlapping in time domain and is
fully/partially/non-overlapping in frequency domain with another PUSCH
that is associated with a different value of *coresetPoolIndex* on a
same serving cell; otherwise *d~3~* = 0.

*- d~4~* is set as reported by UE if the number of transport blocks in
the PUSCH is 2; otherwise *d~4~* = 0.

Otherwise the UE may ignore the scheduling DCI.

The value of ![](media/image804.wmf) is used both in the case of normal
and extended cyclic prefix.

Table 6.4-1: PUSCH preparation time for PUSCH timing capability 1

  -------------------------------------------------------------------------------------
  ![](media/image805.wmf)   PUSCH preparation time *N~2~* \[symbols\]
  ------------------------- -----------------------------------------------------------
  0                         10

  1                         12

  2                         23

  3                         36

  5                         144

  6                         288
  -------------------------------------------------------------------------------------

Table 6.4-2: PUSCH preparation time for PUSCH timing capability 2

  -------------------------------------------------------------------------------------
  ![](media/image805.wmf)   PUSCH preparation time *N~2~* \[symbols\]
  ------------------------- -----------------------------------------------------------
  0                         5

  1                         5.5

  2                         11 for frequency range 1
  -------------------------------------------------------------------------------------