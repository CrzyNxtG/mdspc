## 10.2A PDCCH validation for SL configured grant Type 2

A UE validates, for scheduling activation or scheduling release, a SL
configured grant Type 2 PDCCH if

\- the CRC of a corresponding DCI format 3_0 is scrambled with a
SL-CS-RNTI provided by *sl-CS-RNTI*, and

\- the new data indicator field in the DCI format 3_0 for the enabled
transport block is set to \'0\'

Validation of the DCI format 3_0 is achieved if all fields for the DCI
format 3_0 are set according to Table 10.2A-1 or Table 10.2A-2.

If validation is achieved, the UE considers the information in the DCI
format 3_0 as a valid activation or valid release of SL configured grant
Type 2. If validation is not achieved, the UE discards all the
information in the DCI format 3_0.

Table 10.2A-1: Special fields for SL configured grant Type 2 scheduling
activation PDCCH validation

  ------------------------------------ ----------------------------------
                                       DCI format 3_0

  HARQ process number                  set to all \'0\'s
  ------------------------------------ ----------------------------------

Table 10.2A-2: Special fields for SL configured grant Type 2 scheduling
release PDCCH validation

  -------------------------------------- --------------------------------
                                         DCI format 3_0

  HARQ process number                    set to all \'1\'s

  Frequency resource assignment (if      set to all \'1\'s
  present)                               
  -------------------------------------- --------------------------------

A UE validates, for SL PRS activation or release, a SL configured grant
Type 2 PDCCH if

\- the CRC of a corresponding DCI format 3_2 is scrambled with a
SL-PRS-CS-RNTI provided by *sl-PRS-CS-RNTI*, and

\- the activation/release indication field in the DCI format 3_2 is set
to \'1\' for activation and to \'0\' for release.