### 7.3.1 DCI formats

The DCI formats defined in table 7.3.1-1 are supported.

Table 7.3.1-1: DCI formats

  -------------------------------------------------------------------------
  **DCI      **Usage**
  format**   
  ---------- --------------------------------------------------------------
  0_0        Scheduling of PUSCH in one cell

  0_1        Scheduling of one or multiple PUSCH in one cell, or indicating
             downlink feedback information for configured grant PUSCH
             (CG-DFI)

  0_2        Scheduling of PUSCH in one cell

  0_3        Scheduling of one PUSCH in one cell, or multiple PUSCHs in
             multiple cells with one PUSCH per cell

  1_0        Scheduling of PDSCH in one cell

  1_1        Scheduling of one or multiple PDSCH in one cell, and/or
             triggering one shot HARQ-ACK codebook feedback

  1_2        Scheduling of PDSCH in one cell

  1_3        Scheduling of one PDSCH in one cell, or multiple PDSCHs in
             multiple cells with one PDSCH per cell

  2_0        Notifying a group of UEs of the slot format, available RB
             sets, COT duration and search space set group switching

  2_1        Notifying a group of UEs of the PRB(s) and OFDM symbol(s)
             where UE may assume no transmission is intended for the UE

  2_2        Transmission of TPC commands for PUCCH and PUSCH

  2_3        Transmission of a group of TPC commands for SRS transmissions
             by one or more UEs

  2_4        Notifying a group of UEs of the PRB(s) and OFDM symbol(s)
             where UE cancels the corresponding UL transmission from the UE

  2_5        Notifying the availability of soft resources as defined in
             Clause 9.3.1 of \[10, TS 38.473\]

  2_6        Notifying the power saving information outside DRX Active Time
             for one or more UEs

  2_7        Notifying paging early indication and TRS availability
             indication for one or more UEs

  2_8        Notifying the aperiodic beam indication and associated time
             resources

  2_9        Activating or de-activating the cell DTX and/or DRX
             configuration of one or multiple serving cells for one or more
             UEs, and/or for providing NES-mode indication of the primary
             cell for one or more UEs

  3_0        Scheduling of NR sidelink in one cell

  3_1        Scheduling of LTE sidelink in one cell

  3_2        Scheduling of NR SL PRS in one cell

  4_0        Scheduling of PDSCH with CRC scrambled by MCCH-RNTI/G-RNTI for
             broadcast or by Multicast MCCH-RNTI for multicast in
             RRC_INACITIVE state

  4_1        Scheduling of PDSCH with CRC scrambled by G-RNTI/G-CS-RNTI for
             multicast in RRC_CONNECTED state or by G-RNTI for multicast in
             RRC_INACITIVE state

  4_2        Scheduling of PDSCH with CRC scrambled by G-RNTI/G-CS-RNTI for
             multicast in RRC_CONNECTED state
  -------------------------------------------------------------------------

The fields defined in the DCI formats below are mapped to the
information bits ![](media/image988.wmf) to ![](media/image989.wmf) as
follows.

Each field is mapped in the order in which it appears in the
description, including the zero-padding bit(s), if any, with the first
field mapped to the lowest order information bit ![](media/image990.wmf)
and each successive field mapped to higher order information bits. The
most significant bit of each field is mapped to the lowest order
information bit for that field, e.g. the most significant bit of the
first field is mapped to ![](media/image990.wmf).

If the number of information bits in a DCI format is less than 12 bits,
zeros shall be appended to the DCI format until the payload size equals
12.

The size of each DCI format except for DCI format 0_3/1_3 is determined
by the configuration of the corresponding active bandwidth part of the
scheduled cell and shall be adjusted as described in clause 7.3.1.0 if
necessary.

For a cell set configured by higher layer parameter
*mc-DCI-SetofCellsToAddModList*, the size of DCI format 0_3/1_3 is
determined as follows and shall be adjusted as described in Clause
7.3.1.0 if necessary:

\- If *scheduledCellComboListDCI-0-3* for the cell set is configured,
the size of DCI format 0_3 is determined by the configuration of the
corresponding active bandwidth part(s) of the scheduled cells in the
entry which results in the largest size among the entries in the higher
layer parameter *scheduledCellComboListDCI-0-3*; Otherwise, the size of
DCI format 0_3 is determined by the configuration of the corresponding
active bandwidth part(s) of the cells configured by higher layer
parameter *scheduledCellListDCI-0-3* for the cell set.

\- If *scheduledCellComboListDCI-1-3* for the cell set is configured,
the size of DCI format 1_3 is determined by the configuration of the
corresponding active bandwidth part(s) of the scheduled cells in the
entry which results in the largest size among the entries in the higher
layer parameter *scheduledCellComboListDCI-1-3*; Otherwise, the size of
DCI format 1_3 is determined by the configuration of the corresponding
active bandwidth part(s) of the cells configured by higher layer
parameter *scheduledCellListDCI-1-3* for the cell set.

If a UE is configured with *pdsch-HARQ-ACK-CodebookList-r16*,
*pdsch-HARQ-ACK-Codebook* is replaced by the relevant entry in
*pdsch-HARQ-ACK-CodebookList-r16* in this clause.

If a UE is configured with *pdsch-HARQ-ACK-CodebookListMulticast-r17*,
*pdsch-HARQ-ACK-Codebook* is replaced by the relevant entry in
*pdsch-HARQ-ACK-CodebookListMulticast-r17* in this clause.

For a cell detected in cell search procedure with synchronization raster
defined in Table 5.4.3.1-2 or Table 5.4.3.1-3 of \[13, TS 38.101-1\],
the size of CORESET 0 for the cell in this clause refers to the size of
punctured CORESET 0 as defined in clause 7.3.2.2 of \[4, TS 38.211\] if
any.