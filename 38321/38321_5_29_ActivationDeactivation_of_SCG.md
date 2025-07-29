## 5.29 Activation/Deactivation of SCG

The network may activate and deactivate the configured SCG.

The MAC entity shall for the configured SCG:

1\> if upper layers indicate that SCG is activated:

2\> if *BFI_COUNTER* \>= *beamFailureInstanceMaxCount* for the PSCell or
the *timeAlignmentTimer* associated with PTAG is not running:

3\> indicate to upper layers that a Random Access Procedure (as
specified in clause 5.1.1) is needed for SCG activation.

2\> activate the SCG according to the timing defined in TS 38.133
\[11\].

2\> (re-)initialize any suspended configured uplink grants of configured
grant Type 1 associated with this PSCell according to the stored
configuration, if any, and to start in the symbol according to rules in
clause 5.8.2.2;

2\> apply normal SCG operation including:

3\> SRS transmissions on the PSCell;

3\> CSI reporting for the PSCell;

3\> PDCCH monitoring on the PSCell;

3\> PUCCH transmissions on the PSCell;

3\> transmit on RACH on the PSCell;

3\> initialize *Bj* for each logical channel to zero.

1\> else if upper layers indicate that the SCG is deactivated:

2\> deactivate all the SCells of the SCG according to clause 5.9;

2\> deactivate SCG according to the timing defined in TS 38.133 \[11\];

2\> clear any configured downlink assignment and any configured uplink
grant Type 2 associated with the PSCell respectively;

2\> suspend any configured uplink grant Type 1 associated with the
PSCell;

2\> reset MAC according to clause 5.12;

2\> flush all HARQ buffers associated with the PSCell.

1\> if the SCG is deactivated:

2\> not transmit SRS on the PSCell;

2\> not report CSI for the PSCell;

2\> not transmit on UL-SCH on the PSCell;

2\> not transmit PUCCH on the PSCell;

2\> not transmit on RACH on the PSCell;

2\> not monitor the PDCCH on the PSCell.