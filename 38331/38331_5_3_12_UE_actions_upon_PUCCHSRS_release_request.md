### 5.3.12 UE actions upon PUCCH/SRS release request

Upon receiving a PUCCH release request from lower layers, for all
bandwidth parts of an indicated serving cell the UE shall:

1\> release PUCCH-CSI-Resources configured in *CSI-ReportConfig*;

1\> release PUCCH-CSI-Resources configured in *LTM-CSI-ReportConfig*;

1\> release *SchedulingRequestResourceConfig* instances configured in
*PUCCH-Config*.

Upon receiving an SRS release request from lower layers, for all
bandwidth parts of an indicated serving cell the UE shall:

1\> release *SRS-Resource* instances configured in *SRS-Config*;

1\> release *SRS-PosResourceSetLinkedForAggBW*, if configured;

1\> release *ue-TxTEG-RequestUL-TDOA-Config*, if configured.

Upon receiving a positioning SRS configuration for RRC_INACTIVE release
request from lower layers, the UE shall:

1\> release the configured *srs-PosRRC-Inactive*;

1\> release *SRS-PosResourceSetLinkedForAggBW*, if configured.