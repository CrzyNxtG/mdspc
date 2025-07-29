## 5.24 Handling of PRS Processing Window

When PPW is activated and PRS has higher priority than DL channel and
signals, for the affected symbols within the PPW according to clause
5.1.6.5 in TS 38.214 \[7\], the MAC entity shall:

1\> if the *ra-ResponseWindow* or the *ra-ContentionResolutionTimer* or
the *msgB-ResponseWindow* is running:

2\> monitor the PDCCH as specified in clauses 5.1.4, 5.1.4a and 5.1.5.

1\> else:

2\> not receive DL-SCH;

2\> not receive PDCCH.