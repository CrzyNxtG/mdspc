## 7.1 Physical uplink shared channel

For a PUSCH transmission on active UL BWP $b$, as described in clause
12, of carrier $f$ of serving cell $c$, a UE first calculates a linear
value ${\widehat{P}}_{\text{PUSCH},b,f,c}(i,j,q_{d},l)$ of the transmit
power $P_{\text{PUSCH},b,f,c}(i,j,q_{d},l)$, with parameters as defined
in clause 7.1.1. For a PUSCH transmission scheduled by a DCI format
other than DCI format 0_0, or configured by *ConfiguredGrantConfig* or
*semiPersistentOnPUSCH*, if *txConfig* in *PUSCH-Config* is set to
\'codebook\',

\- if *ul-FullPowerTransmission* in *PUSCH-Config* is provided, the UE
scales ${\widehat{P}}_{\text{PUSCH},b,f,c}(i,j,q_{d},l)$ by $s$ where:

\- if *ul-FullPowerTransmission* in *PUSCH-Config* is set to
*fullpowerMode1*, and each SRS resource in the *SRS-ResourceSet* with
*usage* set to \'codebook\' has more than one SRS port, $s$ is the ratio
of a number of antenna ports with non-zero PUSCH transmission power over
the maximum number of SRS ports supported by the UE in one SRS resource

\- if *ul-FullPowerTransmission* in *PUSCH-Config* is set to
*fullpowerMode2*,

> \- $s = 1$ for full power TPMIs reported by the UE \[18, TS 38.306\],
> and $s$ is the ratio of a number of antenna ports with non-zero PUSCH
> transmission power over a number of SRS ports for remaining TPMIs,
> where the number of SRS ports is associated with an SRS resource
> indicated by an SRI field in a DCI format scheduling the PUSCH
> transmission if more than one SRS resource is configured in the
> *SRS-ResourceSet* with *usage* set to \'codebook\', or indicated by
> Type 1 configured grant, or the number of SRS ports is associated with
> the SRS resource if only one SRS resource is configured in the
> *SRS-ResourceSet* with *usage* set to \'codebook\',
>
> \- $s = 1$, if an SRS resource with a single port is indicated by an
> SRI field in a DCI format scheduling the PUSCH transmission when more
> than one SRS resource is provided in the *SRS-ResourceSet* with
> *usage* set to \'codebook\', or indicated by Type 1 configured grant,
> or if only one SRS resource with a single port is provided in the
> *SRS-ResourceSet* with *usage* set to \'codebook\', and

\- if *ul-FullPowerTransmission* in *PUSCH-Config* is set to
*fullpower*, $s = 1$

\- else, if each SRS resource in the *SRS-ResourceSet* with *usage* set
to \'codebook\' has more than one SRS port, the UE scales the linear
value by the ratio of the number of antenna ports with a non-zero PUSCH
transmission power to the maximum number of SRS ports supported by the
UE in one SRS resource.

The UE splits the power equally across the antenna ports on which the UE
transmits the PUSCH with non-zero power.