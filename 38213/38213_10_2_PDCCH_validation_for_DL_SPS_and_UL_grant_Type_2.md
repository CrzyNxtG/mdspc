## 10.2 PDCCH validation for DL SPS and UL grant Type 2

A UE validates, for scheduling activation or scheduling release, a DL
SPS assignment PDCCH or a configured UL grant Type 2 PDCCH if

\- the CRC of a corresponding DCI format is scrambled with a CS-RNTI
provided by *cs-RNTI* or a G-CS-RNTI provided by g-cs-RNTI, and

\- the new data indicator field in the DCI format for the enabled
transport block is set to \'0\', and

\- the DFI flag field, if present, in the DCI format is set to \'0\',
and

\- the time domain resource assignment field in the DCI format indicates
a row with single SLIV, and

\- if validation is for scheduling activation and if the
PDSCH-to-HARQ_feedback timing indicator field in the DCI format is
present, the PDSCH-to-HARQ_feedback timing indicator field does not
provide an inapplicable value from *dl-DataToUL-ACK-r16* or
*dl-DataToUL-ACK-r17*.

If a UE is provided a single configuration for UL grant Type 2 PUSCH or
for SPS PDSCH, validation of the DCI format is achieved if all fields
for the DCI format are set according to Table 10.2-1 or Table 10.2-2.

If a UE is provided more than one configuration for UL grant Type 2
PUSCH or for SPS PDSCH, a value of the HARQ process number field in a
DCI format indicates an activation for a corresponding UL grant Type 2
PUSCH or for a SPS PDSCH configuration with a same value as provided by
*ConfiguredGrantConfigIndex* or by *sps-ConfigIndex*, respectively.
Validation of the DCI format is achieved if the RV field for the DCI
format is set as in Table 10.2-3.

If a UE is provided more than one configuration for UL grant Type 2
PUSCH or for SPS PDSCH

\- if the UE is provided
*ConfiguredGrantConfigType2DeactivationStateList* or
*sps-ConfigDeactivationStateList*, a value of the HARQ process number
field in a DCI format indicates a corresponding entry for scheduling
release of one or more UL grant Type 2 PUSCH or SPS PDSCH configurations

\- if the UE is not provided
*ConfiguredGrantConfigType2DeactivationStateList* or
*sps-ConfigDeactivationStateList*, a value of the HARQ process number
field in a DCI format indicates a release for a corresponding UL grant
Type 2 PUSCH or for a SPS PDSCH configuration with a same value as
provided by *ConfiguredGrantConfigIndex* or by *sps-ConfigIndex*,
respectively

The UE does not expect to receive a multicast DCI format that releases
either a unicast SPS PDSCH configuration or more than one SPS PDSCH
configurations.

Validation of the DCI format is achieved if all fields for the DCI
format are set according to Table 10.2-4.

If validation is achieved, the UE considers the information in the DCI
format as a valid activation or valid release of DL SPS or configured UL
grant Type 2. If validation is not achieved, the UE discards all the
information in the DCI format.

Table 10.2-1: Special fields for single DL SPS or single UL grant Type 2
scheduling activation PDCCH validation when a UE is provided a single
SPS PDSCH or UL grant Type 2 configuration in the active DL/UL BWP of
the scheduled cell

+-------------+-------------+-----------+-------------+---------------+
|             | DCI format  | DCI       | DCI format  | DCI format    |
|             | 0_0/0_2     | format    | 1_0/1_2/4_1 | 1_1/4_2       |
|             |             | 0_1       |             |               |
+-------------+-------------+-----------+-------------+---------------+
| HARQ        | set to all  | set to    | set to all  | set to all    |
| process     | \'0\'s      | all       | \'0\'s      | \'0\'s        |
| number      |             | \'0\'s    |             |               |
|             |             |           |             |               |
| (if         |             |           |             |               |
| present)    |             |           |             |               |
+-------------+-------------+-----------+-------------+---------------+
| Redundancy  | set to all  | For the   | set to all  | For the       |
| version     | \'0\'s      | enabled   | \'0\'s      | enabled       |
|             |             | transport |             | transport     |
| (if         |             | block:    |             | block: set to |
| present)    |             | set to    |             | all \'0\'s    |
|             |             | all       |             |               |
|             |             | \'0\'s    |             |               |
+-------------+-------------+-----------+-------------+---------------+

Table 10.2-2: Special fields for single DL SPS or single UL grant Type 2
scheduling release PDCCH validation when a UE is provided a single SPS
PDSCH or UL grant Type 2 configuration in the active DL/UL BWP of the
scheduled cell

+--------------------------+---------------------+---------------------+
|                          | DCI format          | DCI format          |
|                          | 0_0/0_1/0_2         | 1_0/1_1/1_2/4_1/4_2 |
+--------------------------+---------------------+---------------------+
| HARQ process number      | set to all \'0\'s   | set to all \'0\'s   |
|                          |                     |                     |
| (if present)             |                     |                     |
+--------------------------+---------------------+---------------------+
| Redundancy version       | set to all \'0\'s   | set to all \'0\'s   |
|                          |                     |                     |
| (if present)             |                     |                     |
+--------------------------+---------------------+---------------------+
| Modulation and coding    | set to all \'1\'s   | set to all \'1\'s   |
| scheme                   |                     |                     |
+--------------------------+---------------------+---------------------+
| Frequency domain         | set to all \'0\'s   | set to all \'0\'s   |
| resource assignment      | for FDRA Type 2     | for FDRA Type 0 or  |
|                          | with $\mu = 1$      | for *dynamicSwitch* |
|                          |                     |                     |
|                          | set to all \'1\'s,  | set to all \'1\'s   |
|                          | otherwise           | for FDRA Type 1     |
+--------------------------+---------------------+---------------------+

Table 10.2-3: Special fields for a single DL SPS or single UL grant Type
2 scheduling activation PDCCH validation when a UE is provided multiple
DL SPS or UL grant Type 2 configurations in the active DL/UL BWP of the
scheduled cell

+-------------+-------------+-----------+-------------+---------------+
|             | DCI format  | DCI       | DCI format  | DCI format    |
|             | 0_0/0_2     | format    | 1_0/1_2/4_1 | 1_1/4_2       |
|             |             | 0_1       |             |               |
+-------------+-------------+-----------+-------------+---------------+
| Redundancy  | set to all  | For the   | set to all  | For the       |
| version     | \'0\'s      | enabled   | \'0\'s      | enabled       |
|             |             | transport |             | transport     |
| (if         |             | block:    |             | block: set to |
| present)    |             | set to    |             | all \'0\'s    |
|             |             | all       |             |               |
|             |             | \'0\'s    |             |               |
+-------------+-------------+-----------+-------------+---------------+

Table 10.2-4: Special fields for a single or multiple DL SPS and UL
grant Type 2 scheduling release PDCCH validation when a UE is provided
multiple DL SPS or UL grant Type 2 configurations in the active DL/UL
BWP of the scheduled cell

+----------------------------+-----------------+----------------------+
|                            | DCI format      | DCI format           |
|                            | 0_0/0_1/0_2     | 1_0/1_1/1_2/4_1/4_2  |
+----------------------------+-----------------+----------------------+
| Redundancy version         | set to all      | set to all \'0\'s    |
|                            | \'0\'s          |                      |
| (if present)               |                 |                      |
+----------------------------+-----------------+----------------------+
| Modulation and coding      | set to all      | set to all \'1\'s    |
| scheme                     | \'1\'s          |                      |
+----------------------------+-----------------+----------------------+
| Frequency domain resource  | set to all      | set to all \'0\'s    |
| assignment                 | \'0\'s for FDRA | for FDRA Type 0 or   |
|                            | Type 2 with     | for *dynamicSwitch*  |
|                            | $\mu = 1$       |                      |
|                            |                 | set to all \'1\'s    |
|                            | set to all      | for FDRA Type 1      |
|                            | \'1\'s,         |                      |
|                            | otherwise       |                      |
+----------------------------+-----------------+----------------------+

A UE is expected to provide HARQ-ACK information in response to a SPS
PDSCH release after $N$ symbols from the last symbol of a PDCCH
providing the SPS PDSCH release. If *processingType2Enabled* of
*PDSCH-ServingCellConfig* is set to *enable* for the serving cell with
the PDCCH providing the SPS PDSCH release, $N = 5$ for $\mu = 0$,
$N = 5.5$ for $\mu = 1$, and $N = 11$ for $\mu = 2$, otherwise, $N = 10$
for $\mu = 0$, $N = 12$ for $\mu = 1$, $N = 22$ for $\mu = 2$, $N = 25$
for $\mu = 3$, $N = 100$ for $\mu = 5$, and $N = 200$ for $\mu = 6$,
wherein $\mu$ corresponds to the smallest SCS configuration between the
SCS configuration of the PDCCH providing the SPS PDSCH release and the
SCS configuration of a PUCCH carrying the HARQ-ACK information in
response to a SPS PDSCH release.