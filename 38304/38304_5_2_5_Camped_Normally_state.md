### 5.2.5 Camped Normally state

This state is applicable for RRC_IDLE and RRC_INACTIVE state.

When camped normally, the UE shall perform the following tasks:

\- monitor the paging channel of the cell as specified in clause 7
according to information broadcast in *SIB1*;

\- monitor Short Messages transmitted with P-RNTI over DCI as specified
in clause 6.5 in TS 38.331 \[3\];

\- monitor relevant System Information as specified in TS 38.331 \[3\];

\- perform necessary measurements for the cell reselection evaluation
procedure;

\- execute the cell reselection evaluation process on the following
occasions/triggers:

1\) UE internal triggers, so as to meet performance as specified in TS
38.133 \[8\];

2\) When information on the BCCH used for the cell reselection
evaluation procedure has been modified.

3\) When the network slice(s) and/or NSAG information received from NAS
changes.