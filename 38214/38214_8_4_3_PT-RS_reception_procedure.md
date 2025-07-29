### 8.4.3 PT-RS reception procedure

Reception of PT-RS is only supported in frequency range 2.

The UE PT-RS reception procedure specified in clause 5.1.6.3 applies for
derivation of the PT-RS parameters *L~PT-RS~* and *K~PT-RS\ ~*and for
determination of PT-RS presence, with the following changes:

\- *timeDensity* and f*requencyDensity* in *PTRS-DownlinkConfig* are
replaced by *sl-PTRS-TimeDensity* and *sl-PTRS-FreqDensity* in
*SL-PTRS-Config* respectively, and *SL-PTRS-Config* is (pre)configured
per resource pool;

\- the number of antenna ports is the same as the number of PSSCH DM-RS
antenna ports and the association between a PT-RS antenna port and a
PSSCH DM-RS antenna port is fixed.