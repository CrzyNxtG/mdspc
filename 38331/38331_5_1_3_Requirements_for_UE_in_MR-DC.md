### 5.1.3 Requirements for UE in MR-DC

In this specification, the UE considers itself to be in:

\- EN-DC, if and only if it is configured with
*nr-SecondaryCellGroupConfig* according to TS 36.331\[10\], and it is
connected to EPC,

\- NGEN-DC, if and only if it is configured with
*nr-SecondaryCellGroupConfig* according to TS 36.331\[10\], and it is
connected to 5GC,

\- NE-DC, if and only if it is configured with *mrdc-SecondaryCellGroup*
set to *eutra-SCG*,

\- NR-DC, if and only if it is configured with *mrdc-SecondaryCellGroup*
set to *nr-SCG*,

\- MR-DC, if and only if it is in (NG)EN-DC, NE-DC or NR-DC.

NOTE: This use of these terms deviates from the definition in TS 37.340
\[41\] and other specifications. In TS 37.340, these terms include also
the case where the UE is configured with E-UTRA or NR MCG only (i.e. no
NR or E-UTRA SCG) but with one or more bearers terminated in a secondary
node (i.e. using NR PDCP).

The UE in (NG)EN-DC only executes a subclause of clause 5 in this
specification when the subclause:

\- is referred to from a subclause under execution, either in this
specification or in TS 36.331 \[10\]; or

\- applies to a message received on SRB3 (if SRB3 is established); or

\- applies to field(s), IE(s), UE variable(s) or timer(s) in this
specification that the UE is configured with.

When executing a subclause of clause 5 in this specification, the UE
follows the requirements in clause 5.1.2 and in all subclauses of this
specification applicable to the messages (including processing time
requirements), fields, IEs, timers and UE variables indicated in the
subclause under execution.