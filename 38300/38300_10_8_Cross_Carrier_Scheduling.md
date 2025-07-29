## 10.8 Cross Carrier Scheduling

Cross-carrier scheduling with the Carrier Indicator Field (CIF) allows
the PDCCH of a serving cell to schedule resources on another serving
cell but with the following restrictions:

\- When cross-carrier scheduling from an SCell to SpCell is not
configured, SpCell can only be scheduled via its PDCCH;

\- When cross-carrier scheduling from an SCell to SpCell is configured:

\- PDCCH on that SCell can schedule SpCell\'s PDSCH and PUSCH;

\- PDCCH on the SpCell can schedule SpCell\'s PDSCH and PUSCH but cannot
schedule PDSCH and PUSCH on any other cell;

\- Only one SCell can be configured to be used for cross-carrier
scheduling to SpCell.

\- When an SCell is configured with a PDCCH, that cell\'s PDSCH and
PUSCH are always scheduled by the PDCCH on this SCell;

\- When an SCell is not configured with a PDCCH, that SCell\'s PDSCH and
PUSCH are always scheduled by a PDCCH on another serving cell;

\- The scheduling PDCCH and the scheduled PDSCH/PUSCH can use the same
or different numerologies.