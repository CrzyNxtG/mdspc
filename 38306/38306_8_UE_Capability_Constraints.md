# 8 UE Capability Constraints

The following table lists constraints indicating the UE capabilities
that the UE shall support.

+---------------------------------------+--------------------------------+-------------------------+
| Parameter                             | Description                    | Value                   |
+=======================================+================================+=========================+
| #DRBs                                 | The number of DRBs that a UE   | 8 per UE, for (e)RedCap |
|                                       | shall support.                 | UEs.                    |
|                                       |                                |                         |
|                                       |                                | 16 per UE, otherwise.   |
|                                       |                                |                         |
|                                       |                                | NOTE 1                  |
|                                       |                                |                         |
|                                       |                                | NOTE 3                  |
|                                       |                                |                         |
|                                       |                                | NOTE 4                  |
+---------------------------------------+--------------------------------+-------------------------+
| #minCellperMeasObjectNR               | The minimum number of          | 32                      |
|                                       | neighbour cells (excluding     |                         |
|                                       | exclude-list cells) that a UE  | NOTE 2                  |
|                                       | shall be able to store         |                         |
|                                       | associated with a              |                         |
|                                       | MeasObjectNR.                  |                         |
+---------------------------------------+--------------------------------+-------------------------+
| #minExcludedCellRangesperMeasObjectNR | The minimum number of          | 8                       |
|                                       | exclude-list cell PCI ranges   |                         |
|                                       | that a UE shall be able to     |                         |
|                                       | store associated with a        |                         |
|                                       | MeasObjectNR.                  |                         |
+---------------------------------------+--------------------------------+-------------------------+
| #minExcludedCellperMeasObjectEUTRA    | The minimum number of          | 32                      |
|                                       | exclude-list cells that a UE   |                         |
|                                       | shall be able to store         |                         |
|                                       | associated with a              |                         |
|                                       | MeasObjectEUTRA.               |                         |
+---------------------------------------+--------------------------------+-------------------------+
| #minCellperMeasObjectEUTRA            | The minimum number of          | 32                      |
|                                       | neighbour cells that a UE      |                         |
|                                       | shall be able to store         | NOTE 2                  |
|                                       | associated with a              |                         |
|                                       | MeasObjectEUTRA.               |                         |
+---------------------------------------+--------------------------------+-------------------------+
| #minCellTotal                         | The minimum number of          | 256 with counting       |
|                                       | neighbour cells (excluding     | CSI-RS and SSB as 2.    |
|                                       | exclude-list cells) that UE    |                         |
|                                       | shall be able to store in      |                         |
|                                       | total from all measurement     |                         |
|                                       | objects configured.            |                         |
+---------------------------------------+--------------------------------+-------------------------+
| #maxDeprioritisationFreq              | The UE shall be able to store  | 8                       |
|                                       | a depriotisation request for   |                         |
|                                       | up to 8 frequencies            |                         |
|                                       | (applicable when receiving     |                         |
|                                       | another frequency specific     |                         |
|                                       | deprioritisation request via   |                         |
|                                       | *RRCRelease* before T325       |                         |
|                                       | expiry).                       |                         |
+---------------------------------------+--------------------------------+-------------------------+
| #minCellperMeasObjectUTRA-FDD         | The minimum number of          | 32                      |
|                                       | neighbour cells that a UE      |                         |
|                                       | shall be able to store         |                         |
|                                       | associated with a              |                         |
|                                       | MeasObjectUTRA-FDD.            |                         |
+---------------------------------------+--------------------------------+-------------------------+
| NOTE 1: For one MAC entity, the maximum number of DRBs configured with PDCP duplication and with |
| RLC entity(ies) associated with this MAC entity is 8.                                            |
|                                                                                                  |
| NOTE 2: In case of CGI reporting, the limit regarding the cells configured includes the cell for |
| which the UE is requested to report CGI i.e. the amount of neighbour cells that can be included  |
| is at most (# minCellperMeasObjectRAT - 1), where RAT represents NR and EUTRA.                   |
|                                                                                                  |
| NOTE 3: This requirement is applicable in NR SA, NR-DC and NE-DC.                                |
|                                                                                                  |
| NOTE 4: The value of parameter #DRBs defines the total number of multicast MRBs and DRBs, and    |
| each multicast MRB associated with two RLC entities is counted as two RBs.                       |
+--------------------------------------------------------------------------------------------------+