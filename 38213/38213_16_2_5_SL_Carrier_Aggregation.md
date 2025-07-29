### 16.2.5 SL Carrier Aggregation

If a UE is configured for sidelink operation on multiple carriers, the
UE applies the synchronization procedures in Clause 16.1 on each of the
multiple carriers \[12, TS 38.331\].

If a UE would transmit S-SS/PSBCH blocks on multiple carriers, the UE
determines a power for each S-SS/PSBCH block transmission as described
in Clause 16.2.0. If the UE would transmit S-SS/PSBCH blocks that would
overlap in time on respective carriers and a total power for the
transmissions of the S-SS/PSBCH blocks would exceed $P_{\text{CMAX}}$
\[8-1, TS 38.101-1\], the UE autonomously reduces a power for one or
more of the S-SS/PSBCH blocks transmissions so that a resulting total
power would not exceed $P_{\text{CMAX}}$.

If a UE would transmit PSCCHs/PSSCHs on multiple carriers, the UE
determines a power for each PSCCH/PSSCH transmission as described in
Clauses 16.2.1 and 16.2.2, respectively. If the UE would transmit
PSCCHs/PSSCHs that would overlap in time on respective carriers and a
total power for the PSCCH/PSSCH transmissions would exceed
$P_{\text{CMAX}}$, the UE reduces a power for a PSCCH/PSSCH transmission
that has the largest priority value as determined by SCI formats
provided by the PSCCHs scheduling the respective PSSCHs. If more than
one PSCCH/PSSCH transmission have the largest priority value, the UE
autonomously selects one of the more than one PSCCH/PSSCH transmissions
to reduce a respective power. If, after the reduction of the power of
the PSCCH/PSSCH transmission with the largest priority value, a total
power exceeds $P_{\text{CMAX}}$, the UE drops the PSCCH/PSSCH
transmission with the largest priority value, respectively, and repeats
the procedure over the remaining PSCCH/PSSCH transmission(s).

If a UE would simultaneously transmit PSFCHs and receive PSFCHs on
multiple carriers, the UE performs the procedures in Clause 16.2.4.2 by
considering all the PSFCHs for transmission and all the PSFCHs for
reception in order to determine either PSFCHs to transmit or PSFCHs to
receive. If a UE would simultaneously transmit PSFCHs on multiple
carriers, the UE performs the procedures for single carrier in Clause
16.2.3 by considering all the PSFCHs for transmission using a
corresponding $N_{max,\ PSFCH}$ and $P_{\text{CMAX}}$ in order to
determine PSFCHs to transmit and a corresponding power per PSFCH
transmission, where $P_{\text{CMAX}}$ is defined in Clause 6.2E.4A of
\[8-1, TS 38.101-1\]. The UE expects to be provided a (pre)configuration
such that the PSFCH transmissions on the multiple carriers are with time
resource alignment and a same power.

A UE expects that *sl-StartSymbol*, *sl-LengthSymbols*, *cyclicPrefix*,
and *subcarrierSpacing* are (pre)configured to have same respective
values on multiple carriers.