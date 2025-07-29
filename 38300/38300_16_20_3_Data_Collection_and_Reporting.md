### 16.20.3 Data Collection and Reporting

The following information can be configured to be reported by an NG-RAN
node:

\- Predicted resource status information;

\- UE performance feedback;

\- Measured UE trajectory;

\- Energy Cost (EC).

The collection and reporting are configured through the Data Collection
Reporting Initiation procedure, while the actual reporting is performed
through the Data Collection Reporting procedure.

The collection of measured UE trajectory and UE performance feedback is
triggered at successful Handover.

Cell-based UE trajectory prediction, which can be used, e.g., for the
Mobility Optimization use case, is transferred to the target NG-RAN node
via the Handover Preparation procedure to provide information for, e.g.,
subsequent mobility decisions. Cell-based UE trajectory prediction is
limited to the first-hop target NG-RAN node.