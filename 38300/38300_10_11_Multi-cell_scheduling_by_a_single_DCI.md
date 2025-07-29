## 10.11 Multi-cell scheduling by a single DCI

Multi-cell scheduling by a single DCI allows the PDCCH of a serving cell
to schedule PDSCH(s)/PUSCH(s) on one or more serving cells with the
single DCI but with the following restrictions:

\- When a serving cell is configured with a PDCCH which schedules
PDSCH(s)/PUSCH(s) on a cell set, the PUSCH/PDSCH on serving cells in the
cell set is always scheduled by a PDCCH on the serving cell;

\- When SpCell is configured with a PDCCH which schedules
PDSCH(s)/PUSCH(s) on serving cells in a cell set, that SpCell\'s PDSCH
and PUSCH cannot be scheduled by a PDCCH on an SCell;

\- When an SCell is configured with a PDCCH which schedules
PDSCH(s)/PUSCH(s) on serving cells in a cell set, SpCell is not included
in the cell set;

\- The scheduling PDCCH and the scheduled PDSCH(s)/PUSCH(s) can use the
same or different numerologies;

\- The co-scheduled PDSCH(s) with a PDCCH use the same numerology;

\- The co-scheduled PUSCH(s) with a PDCCH use the same numerology.