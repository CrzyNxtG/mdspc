## 10.4B Indication of TRS resources

A UE in RRC_IDLE state or RRC_INACTIVE state can be provided by
*trs-ResourceSetConfig* or by *trs-ResourceSetConfig-r18* a set of TRS
occasions \[6, TS 38.214\]. If *trs-ResourceSetConfig* or
*trs-ResourceSetConfig-r18* is provided, a DCI format 2_7, if
*pei-SearchSpace* is provided, and a DCI format 1_0 with CRC scrambled
by P-RNTI includes a TRS availability indication field \[4, TS 38.212\]
that provides a bitmap to groups of TRS resource sets where the
configuration of each TRS resource set includes an association to a bit
of the bitmap. For TRS occasions provided by *trs-ResourceSetConfig*,
the UE can be additionally provided a multiple, by *validityDuration*,
for a number of frames provided by *defaultPagingCycle* for TRS resource
sets with indicated presence; if *validityDuration* is not provided, the
multiple is equal to 2. For TRS occasions provided by
*trs-ResourceSetConfig-r18,* the UE can be additionally provided a
multiple, by *validityDuration-r18*, for a number of frames provided by
*defaultPagingCycle* for TRS resource sets with indicated presence; if
*validityDuration-r18* is not provided, the multiple is equal to 2.

A value of \'1\' for a bit of the bitmap indicates presence of
associated TRS resource sets for the multiple of the number of frames,
starting from a SFN determined from $(SFN + PF\_ offset)modT = 0$ \[17,
TS 38.304\] that corresponds to the frame within the DRX cycle that
includes the PDCCH providing the DCI format 2_7, or the DCI format 1_0
with CRC scrambled by P-RNTI, with the TRS availability indication field
indicating the TRS resource sets, where $T$ is provided by
*defaultPagingCycle*. A value of \'0\' for a bit of the bitmap indicates
no change to a current assumption for the availability or unavailability
of associated TRS resource sets.

A UE can receive first and second PDCCHs that provide DCI format 2_7 or
DCI format 1_0 with CRC scrambled by P-RNTI that indicate presence of
TRS resource sets for the multiple of the number of frames, where the
second PDCCH reception after the first PDCCH reception by a time that is
smaller than the multiple of the number of frames.