### 5.18.19 Guard symbols for IAB

For IAB operation, the MAC entity on the IAB-DU or IAB-donor-DU reserves
a sufficient number of symbols at the beginning and/or the end of slots
where the child IAB-node switches operation from its IAB-DU to its
IAB-MT function and operation from its IAB-MT to its IAB-DU function.
The MAC entity on the IAB-DU or IAB-donor-DU informs the child node
about the number of guard symbols it provides via the Provided Guard
Symbols MAC CE. The IAB-MT on the child node may inform the parent
IAB-DU or IAB-donor-DU about the number of guard symbols desired via the
Desired Guard Symbols MAC CE. IAB-MT transmission timing modes are
specified in clause 14 of TS 38.213 \[6\].

Upon reception of a Provided Guard Symbols MAC CE the MAC entity shall:

\- indicate to lower layers the number of provided guard symbols and the
SCS configuration for the indicated Serving Cell.

The MAC entity may:

1\> if a Desired Guard Symbol query has not been triggered:

2\> trigger a Desired Guard Symbol query for this Serving Cell.

If the MAC entity has UL resources allocated for new transmission the
MAC entity shall:

1\> for each Desired Guard Symbol query that has been triggered and not
cancelled:

2\> if the allocated UL resources can accommodate a Desired Guard
Symbols MAC CE plus its subheader as a result of LCP as defined in
clause 5.4.3.1:

3\> instruct the Multiplexing and Assembly procedure to generate the
Desired Guard Symbols MAC CE;

3\> cancel this Desired Guard Symbol query.

For Case-1 timing mode, a separate value for the number of guard symbols
is specified for each of the following eight switching scenarios (see
Table 5.18.19-1).

Table 5.18.19-1: Switching scenarios and relevant guard symbols for
Case-1 timing mode

+-------------------------------------------------------+--------------------+
| Switching scenario                                    | Field for number   |
|                                                       | of guard symbols   |
|                                                       | in MAC CE          |
+==========================+============================+====================+
| IAB-MT operation to      | MT Rx to DU Tx             | NmbGS~1~           |
| IAB-DU operation         |                            |                    |
|                          +----------------------------+--------------------+
|                          | MT Rx to DU Rx             | NmbGS~2~           |
|                          +----------------------------+--------------------+
|                          | MT Tx to DU Tx             | NmbGS~3~           |
|                          +----------------------------+--------------------+
|                          | MT Tx to DU Rx             | NmbGS~4~           |
+--------------------------+----------------------------+--------------------+
| IAB-DU operation to      | DU Rx to MT Tx             | NmbGS~5~           |
| IAB-MT operation         |                            |                    |
|                          +----------------------------+--------------------+
|                          | DU Rx to MT Rx             | NmbGS~6~           |
|                          +----------------------------+--------------------+
|                          | DU Tx to MT Tx             | NmbGS~7~           |
|                          +----------------------------+--------------------+
|                          | DU Tx to MT Rx             | NmbGS~8~           |
+--------------------------+----------------------------+--------------------+

For Case-6 and Case-7 timing modes, a separate value for the number of
guard symbols is specified for each of the following eight switching
scenarios (see Table 5.18.19-2):

Table 5.18.19-2: Switching scenarios and relevant guard symbols for
Case-6 and Case-7 timing modes

+-------------------------------------------------------+--------------------+
| Switching scenario                                    | Field for number   |
|                                                       | of guard symbols   |
|                                                       | in MAC CE          |
+==========================+============================+====================+
| IAB-MT operation to      | MT Tx (Case-6) to DU Tx    | NmbGS~9~           |
| IAB-DU operation         | (Case-1)                   |                    |
|                          +----------------------------+--------------------+
|                          | MT Tx (Case-6) to DU Rx    | NmbGS~10~          |
|                          | (Case-1)                   |                    |
|                          +----------------------------+--------------------+
|                          | MT Tx (Case-7) to DU Tx    | NmbGS~11~          |
|                          | (Case-1)                   |                    |
|                          +----------------------------+--------------------+
|                          | MT Tx (Case-7) to DU Rx    | NmbGS~12~          |
|                          | (Case-1)                   |                    |
+--------------------------+----------------------------+--------------------+
| IAB-DU operation to      | DU Tx (Case-1) to MT Tx    | NmbGS~13~          |
| IAB-MT operation         | (Case-6)                   |                    |
|                          +----------------------------+--------------------+
|                          | DU Rx (Case-1) to MT Tx    | NmbGS~14~          |
|                          | (Case-6)                   |                    |
|                          +----------------------------+--------------------+
|                          | DU Tx (Case-1) to MT Tx    | NmbGS~15~          |
|                          | (Case-7)                   |                    |
|                          +----------------------------+--------------------+
|                          | DU Rx (Case-1) to MT Tx    | NmbGS~16~          |
|                          | (Case-7)                   |                    |
+--------------------------+----------------------------+--------------------+