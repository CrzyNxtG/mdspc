### 8.2.1 CSI-RS transmission procedure

A UE transmits sidelink CSI-RS within a unicast PSSCH transmission if
the following conditions hold:

\- CSI reporting is enabled by higher layer parameter
*sl-CSI-Acquisition*; and

\- the \'*CSI request*\' field in the corresponding SCI format 2-A, 2-C
or 2-D is set to 1.

The following parameters for CSI-RS transmission are configured for each
CSI-RS configuration:

\- *sl-CSI-RS-FirstSymbol* indicates the first OFDM symbol in a PRB used
for SL CSI-RS

\- *sl-CSI-RS-FreqAllocation* indicates the number of antenna ports and
the frequency domain allocation for SL CSI-RS.

When the UE is configured with *Q~p~*={1,2} CSI-RS port(s) in sidelink
and the number of scheduled layers is $n_{layer}^{PSSCH}$,

\- The CSI-RS scaling factor $\beta_{CSIRS}$ specified in clause
8.4.1.5.3 of \[4, TS 38.211\] is given by
$\beta_{CSIRS} = \beta_{DMRS}^{PSSCH} \bullet \sqrt{\frac{n_{layer}^{PSSCH}}{Q_{p}}}\ $
where $\beta_{DMRS}^{PSSCH}$ is the scaling factor for the corresponding
PSSCH specified in clause 8.3.1.5 of \[4, TS 38.211\].