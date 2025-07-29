## 8.6 UE PSSCH preparation procedure time

For sidelink dynamic grant and for SL configured grant type 2
activation, if the first sidelink symbol in the sidelink allocation for
a PSSCH for a transport block and the associated PSCCH, including the
DM-RS and the duplicated symbol, as defined by the slot offset $K_{SL}$
of the scheduling DCI for dynamic grant or the activating DCI for SL
configured grant type 2, is no earlier than at symbol *L*, where *L* is
defined as the next sidelink symbol with its CP starting
$T_{proc} = (N_{2} + d_{2,1})(2048 + 144) \cdot \kappa 2^{- \mu} \cdot T_{C} + T_{ext}$
after the end of the reception of the last symbol of the PDCCH carrying
the DCI scheduling the sidelink transmissions for dynamic grant or
activating the SL configured grant type 2, then the UE shall transmit
the PSSCH and the associated PSCCH.

*- N~2~* is based on *µ* of Table 8.6-1, where *µ* corresponds to the
one of (*µ~DL~*, *µ~SL~*) resulting with the largest *T~proc~*, where
the *µ~DL~* corresponds to the subcarrier spacing of the downlink with
which the PDCCH carrying the DCI scheduling the PSSCH for dynamic grant
or activating the SL configured grant type 2 was transmitted and *µ~SL~*
corresponds to the subcarrier spacing of the sidelink channel with which
the PSSCH and the associated PSCCH are to be transmitted, and *κ* is
defined in Clause 4.1 of \[4, TS 38.211\].

\- For operation with shared spectrum channel access in FR1, *T~ext~* is
calculated according to \[4, TS 38.211\] with the index *i* for *C~i~*
and *Δ~i~* set to'1' for *µ~SL~ = 0,* to '3' for *µ~SL~ = 1,* and to '2'
for *µ~SL~ = 2.* Otherwise, *T~ext~ = 0.*

\- *d~2,1\ ~*= 1.

Otherwise the UE may ignore the scheduling DCI for dynamic grant or the
activating DCI for SL configured grant type 2.

The value of $T_{proc}$ is used both in the case of normal and extended
cyclic prefix.

Table 8.6-1: PSSCH preparation time

  -------------------------------------------------------------------------------------
  ![](media/image805.wmf)   PSSCH preparation time *N~2~* \[symbols\]
  ------------------------- -----------------------------------------------------------
  0                         10

  1                         12

  2                         23

  3                         36
  -------------------------------------------------------------------------------------

For sidelink resource allocation mode 1, the UE does not expect that the
first sidelink symbol in the sidelink allocation for a PSSCH for
retransmission of a transport block and the associated PSCCH, including
the DM-RS and the duplicated symbol as defined by the \"Time resource
assignment\" field of the corresponding DCI for dynamic grant or for SL
configured grant type 2, or by *sl-TimeResourceCG-Type1* for configured
grant type 1 starts earlier than at symbol $L$ where $L$ is defined as
the next sidelink symbol with its CP starting $T_{prep} + \delta$ after
the end of the last symbol of the PSFCH occasion corresponding to the
most recent transmission of PSSCH for the same transport block if
*sl-NumPSFCH-Occasions* is not (pre-)configured, or after the end of the
last symbol of the last candidate PSFCH occasion corresponding to the
most recent transmission of PSSCH for the same transport block if
*sl-NumPSFCH-Occasions* is (pre-)configured, where $T_{prep}$ is defined
in Clause 16.5 of \[6, TS 38.213\] and
$\delta = {5 \bullet 10}^{- 4}\ s$. Otherwise the UE may skip the
retransmission of the PSSCH and the transmission of the corresponding
PSCCH.