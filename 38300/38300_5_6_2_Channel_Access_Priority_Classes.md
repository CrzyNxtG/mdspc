### 5.6.2 Channel Access Priority Classes

The Channel Access Priority Classes (CAPC) of radio bearers and MAC CEs
are either fixed or configurable for operation in FR1:

\- Fixed to the lowest priority for the padding BSR and recommended bit
rate MAC CEs;

\- Fixed to the highest priority for SRB0, SRB1, SRB3 and other MAC CEs;

\- Configured by the gNB for SRB2 and DRB.

When choosing the CAPC of a DRB, the gNB takes into account the 5QIs of
all the QoS flows multiplexed in that DRB while considering fairness
between different traffic types and transmissions. Table 5.6.2-1 below
shows which CAPC should be used for which standardized 5QIs i.e. which
CAPC to use for a given QoS flow.

NOTE: A QoS flow corresponding to a non-standardized 5QI (i.e. operator
specific 5QI) should use the CAPC of the standardized 5QI which best
matches the QoS characteristics of the non-standardized 5QI.

Table 5.6.2-1: Mapping between Channel Access Priority Classes and 5QI

+-------------------------------------+-------------------------------------------------------+
| CAPC                                | 5QI                                                   |
+=====================================+=======================================================+
| 1                                   | 1, 3, 5, 65, 66, 67, 69, 70, 79, 80, 82, 83, 84, 85   |
+-------------------------------------+-------------------------------------------------------+
| 2                                   | 2, 7, 71                                              |
+-------------------------------------+-------------------------------------------------------+
| 3                                   | 4, 6, 8, 9, 72, 73, 74, 76                            |
+-------------------------------------+-------------------------------------------------------+
| 4                                   | \-                                                    |
+-------------------------------------+-------------------------------------------------------+
| NOTE: lower CAPC value means higher priority                                                |
|                                                                                             |
| \-                                                                                          |
+---------------------------------------------------------------------------------------------+

When performing Type 1 LBT for the transmission of an uplink TB (see TS
37.213 \[37\], clause 4.2.1.1) and when the CAPC is not indicated in the
DCI, the UE shall select the CAPC as follows:

\- If only MAC CE(s) are included in the TB, the highest priority CAPC
of those MAC CE(s) is used; or

\- If CCCH SDU(s) are included in the TB, the highest priority CAPC is
used; or

\- If DCCH SDU(s) are included in the TB, the highest priority CAPC of
the DCCH(s) is used; or

\- The lowest priority CAPC of the logical channel(s) with MAC SDU
multiplexed in the TB is used otherwise.