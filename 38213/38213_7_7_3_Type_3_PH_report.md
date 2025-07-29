### 7.7.3 Type 3 PH report

If a UE determines that a Type 3 power headroom report for an activated
serving cell is based on an actual SRS transmission then, for SRS
transmission occasion
![](media/image45.wmf){width="0.10416666666666667in"
height="0.19791666666666666in"} on active UL BWP
![](media/image42.wmf){width="0.19791666666666666in"
height="0.19791666666666666in"} of carrier
![](media/image46.wmf){width="0.19791666666666666in"
height="0.19791666666666666in"} of serving cell $c$ and if the UE is not
configured for PUSCH transmissions on carrier
![](media/image46.wmf){width="0.19791666666666666in"
height="0.19791666666666666in"} of serving cell $c$ and the resource for
the SRS transmission is provided by *SRS-Resource*, the UE computes a
Type 3 power headroom report as

![](media/image47.wmf){width="6.510416666666667in"
height="0.3020833333333333in"} \[dB\]

where ![](media/image48.wmf){width="0.7708333333333334in"
height="0.2604166666666667in"},
![](media/image49.wmf){width="0.8958333333333334in"
height="0.19791666666666666in"},
![](media/image50.wmf){width="0.6979166666666666in"
height="0.19791666666666666in"},
![](media/image51.wmf){width="0.8020833333333334in"
height="0.2604166666666667in"},
![](media/image52.wmf){width="0.6979166666666666in"
height="0.19791666666666666in"} and
![](media/image53.wmf){width="0.5104166666666666in"
height="0.19791666666666666in"} are defined in clause 7.3.1 with
corresponding values provided by *SRS-ResourceSet*.

If the UE determines that a Type 3 power headroom report for an
activated serving cell is based on a reference SRS transmission then,
for SRS transmission occasion
![](media/image54.wmf){width="0.10416666666666667in"
height="0.19791666666666666in"} on UL BWP
![](media/image42.wmf){width="0.19791666666666666in"
height="0.19791666666666666in"} of carrier
![](media/image46.wmf){width="0.19791666666666666in"
height="0.19791666666666666in"} of serving cell $c$, and if the UE is
not configured for PUSCH transmissions on UL BWP
![](media/image42.wmf){width="0.19791666666666666in"
height="0.19791666666666666in"} of carrier
![](media/image46.wmf){width="0.19791666666666666in"
height="0.19791666666666666in"} of serving cell $c$ and a resource for
the reference SRS transmission is provided by *SRS-Resource*, the UE
computes a Type 3 power headroom report as

![](media/image55.wmf){width="4.885416666666667in"
height="0.2604166666666667in"} \[dB\]

where ![](media/image56.wmf){width="0.19791666666666666in"
height="0.2604166666666667in"} is an SRS resource set corresponding to
*SRS-ResourceSetId = 0* for UL BWP
![](media/image42.wmf){width="0.19791666666666666in"
height="0.19791666666666666in"} and
![](media/image57.wmf){width="0.8958333333333334in"
height="0.2604166666666667in"},
![](media/image58.wmf){width="0.8020833333333334in"
height="0.2604166666666667in"},
![](media/image59.wmf){width="0.6979166666666666in"
height="0.2604166666666667in"} and
![](media/image60.wmf){width="0.5104166666666666in"
height="0.2604166666666667in"} are defined in clause 7.3.1 with
corresponding values obtained from *SRS-ResourceSetId = 0* for UL BWP
![](media/image42.wmf){width="0.19791666666666666in"
height="0.19791666666666666in"}.
![](media/image61.wmf){width="0.8020833333333334in"
height="0.2604166666666667in"} is computed assuming MPR=0 dB, A-MPR=0
dB, P-MPR=0 dB and ∆T~C~ =0 dB. MPR, A-MPR, P-MPR and ∆T~C~ are defined
in \[8-1, TS 38.101-1\], \[8-2, TS 38.101-2\], \[8-3, TS 38.101-3\] and
\[8-5, TS 38.101-5\].

If a UE is configured with two UL carriers for a serving cell and the UE
determines a Type 3 power headroom report for the serving cell based on
a reference SRS transmission and a resource for the reference SRS is
provided by *SRS-Resource*, the UE computes a Type 3 power headroom
report for the serving cell assuming a reference SRS transmission on the
UL carrier provided by *pucch-Config*. If *pucch-Config* is not provided
to the UE for any of the two UL carriers, the UE computes a Type 3 power
headroom report for the serving cell assuming a reference SRS
transmission on the non-supplementary UL carrier.