## 5.5 UE PDSCH reception preparation time with different subcarrier spacings for PDCCH and PDSCH in different cells

This clause applies only if the PDCCH carrying the scheduling DCI is
received on one carrier with one OFDM subcarrier spacing (µ~PDCCH~), and
the PDSCH scheduled to be received by the DCI is on another carrier with
another OFDM subcarrier spacing (µ~PDSCH~).

If the µ~PDCCH~ \< µ~PDSCH~, the UE is expected to receive the scheduled
PDSCH, if the first symbol in the PDSCH allocation, including the DM-RS,
as defined by the slot offset *K~0~* and the start and length indicator
*SLIV* of the scheduling DCI starts no earlier than the first symbol of
the slot of the PDSCH reception starting at least *N~pdsch~* PDCCH
symbols after the end of the PDCCH scheduling the PDSCH, not taking into
account the effect of receive timing difference between the scheduling
cell and the scheduled cell.

If the µ~PDCCH~ \> µ~PDSCH~, the UE is expected to receive the scheduled
PDSCH, if the first symbol in the PDSCH allocation, including the DM-RS,
as defined by the slot offset *K~0~* and the start and length indicator
*SLIV* of the scheduling DCI starts no earlier than *N~pdsch~* PDCCH
symbols after the end of the PDCCH scheduling the PDSCH, not taking into
account the effect of receive timing difference between the scheduling
cell and the scheduled cell.

When the PDCCH reception includes two PDCCH candidates from two
respective search space sets, as described in clause 10.1 of \[6, TS
38.213\], for the purpose of determining *N~pdsch~*, the PDCCH candidate
that ends later in time is used.

Table 5.5-1: *N~pdsch~* as a function of the subcarrier spacing of the
scheduling PDCCH

  -----------------------------------------------------------------------
  ***µ~PDCCH~***                      ***N~pdsch~* \[symbols\]**
  ----------------------------------- -----------------------------------
  0                                   4

  1                                   5

  2                                   10

  3                                   14

  5                                   56

  6                                   112
  -----------------------------------------------------------------------