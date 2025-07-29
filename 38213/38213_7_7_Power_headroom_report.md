## 7.7 Power headroom report

The types of UE power headroom reports are the following. A Type 1 UE
power headroom ![](media/image40.wmf){width="0.2604166666666667in"
height="0.15625in"} that is valid for PUSCH transmission occasion
![](media/image41.wmf){width="0.10416666666666667in"
height="0.19791666666666666in"} on active UL BWP
![](media/image42.wmf){width="0.19791666666666666in"
height="0.19791666666666666in"} of carrier
![](media/image43.wmf){width="0.10416666666666667in"
height="0.19791666666666666in"} of serving cell
![](media/image44.wmf){width="0.125in" height="0.17708333333333334in"}.
A Type 3 UE power
headroom![](media/image40.wmf){width="0.2604166666666667in"
height="0.15625in"} that is valid for SRS transmission occasion
![](media/image41.wmf){width="0.10416666666666667in"
height="0.19791666666666666in"} on active UL BWP
![](media/image42.wmf){width="0.19791666666666666in"
height="0.19791666666666666in"} of carrier
![](media/image43.wmf){width="0.10416666666666667in"
height="0.19791666666666666in"} of serving cell
![](media/image44.wmf){width="0.125in" height="0.17708333333333334in"}.

A UE determines whether a power headroom report for an activated serving
cell \[11, TS 38.321\] is based on an actual transmission or a reference
format based on the higher layer signalling of configured grant and
periodic/semi-persistent sounding reference signal transmissions and
downlink control information the UE received until and including the
PDCCH monitoring occasion where the UE detects the first DCI format
scheduling an initial transmission of a transport block since a power
headroom report was triggered if the power headroom report is reported
on a PUSCH triggered by the first DCI format. Otherwise, a UE determines
whether a power headroom report is based on an actual transmission or a
reference format based on the higher layer signalling of configured
grant and periodic/semi-persistent sounding reference signal
transmissions and downlink control information the UE received until the
first uplink symbol of a configured PUSCH transmission minus
*T\'~proc,2~*=*T~proc,2~* where *T~proc,2\ ~*is determined according to
\[6, TS 38.214\] assuming *d~2,1\ ~*= 1, *d~2,2~*=0, and with *µ~DL~*
corresponding to the subcarrier spacing of the active downlink BWP of
the scheduling cell for a configured grant if the power headroom report
is reported on the PUSCH using the configured grant.

If a UE

\- is configured with two UL carriers for a serving cell, and

\- determines a Type 1 power headroom report and a Type 3 power headroom
report for the serving cell

the UE

\- provides the Type 1 power headroom report if both the Type 1 and Type
3 power headroom reports are based on respective actual transmissions or
on respective reference transmissions

\- provides the power headroom report that is based on a respective
actual transmission if either the Type 1 report or the Type 3 report is
based on a respective reference transmission

If a UE is configured with a SCG and if *phr-ModeOtherCG* for a CG
indicates \'virtual\' then, for power headroom reports transmitted on
the CG, the UE computes *PH* assuming that the UE does not transmit
PUSCH/PUCCH on any serving cell of the other CG. For NR-DC when both the
MCG and the SCG operate either in FR1 or in FR2 and for a power headroom
report transmitted on the MCG or the SCG, the UE computes *PH* assuming
that the UE does not transmit PUSCH/PUCCH on any serving cell of the SCG
or the MCG, respectively.

If the UE is configured with a SCG,

\- For computing power headroom for cells belonging to MCG, the term
\'serving cell\' in this clause refers to serving cell belonging to the
MCG.

\- For computing power headroom for cells belonging to SCG, the term
\'serving cell\' in this clause refers to serving cell belonging to the
SCG. The term \'primary cell\' in this clause refers to the PSCell of
the SCG.

If the UE is configured with a PUCCH-SCell,

\- For computing power headroom for cells belonging to primary PUCCH
group, the term \'serving cell\' in this clause refers to serving cell
belonging to the primary PUCCH group.

\- For computing power headroom for cells belonging to secondary PUCCH
group, the term \'serving cell\' in this clause refers to serving cell
belonging to the secondary PUCCH group. The term \'primary cell\' in
this clause refers to the PUCCH-SCell of the secondary PUCCH group.

For a UE configured with EN-DC/NE-DC and capable of dynamic power
sharing, if E-UTRA Dual Connectivity PHR \[14, TS 36.321\] is triggered
and,

\- if the duration of NR slot on active UL BWP is different from that of
E-UTRA subframe carrying the Dual Connectivity PHR, the UE provides
power headroom of the first NR slot that fully overlaps with the E-UTRA
subframe;

\- if the duration of NR slot on active UL BWP is the same as that of
E-UTRA subframe carrying the Dual Connectivity PHR for asynchronous
EN-DC/NE-DC \[10, TS 38.133\], the UE provides power headroom of the
first NR slot that overlaps with the E-UTRA subframe.