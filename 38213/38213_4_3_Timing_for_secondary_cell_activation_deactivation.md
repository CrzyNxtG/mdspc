## 4.3 Timing for secondary cell activation / deactivation

With reference to slots for PUCCH transmissions, when a UE receives in a
PDSCH an activation command \[11, TS 38.321\] for a secondary cell
ending in slot *n*, the UE applies the corresponding actions in \[11, TS
38.321\] no later than the minimum requirement defined in \[10, TS
38.133\] and no earlier than slot
![](media/image3.wmf){width="0.3229166666666667in"
height="0.19791666666666666in"}, except for the following:

\- the actions related to CSI reporting on a serving cell that is active
in slot ![](media/image4.wmf){width="0.3229166666666667in"
height="0.19791666666666666in"}

\- the actions related to the *sCellDeactivationTimer* associated with
the secondary cell \[11, TS 38.321\] that the UE applies in slot
![](media/image4.wmf){width="0.3229166666666667in"
height="0.19791666666666666in"}

\- the actions related to CSI reporting on a serving cell which is not
active in slot ![](media/image4.wmf){width="0.3229166666666667in"
height="0.19791666666666666in"}that the UE applies in the earliest slot
after ![](media/image4.wmf){width="0.3229166666666667in"
height="0.19791666666666666in"} in which the serving cell is active.

The value of ![](media/image5.wmf){width="0.125in"
height="0.19791666666666666in"} is
${m + 3\ N}_{\text{slot}}^{\text{subframe},\mu} + 1$ where
slot![](media/image6.png) *n*+*m* is a slot indicated for PUCCH
transmission with HARQ-ACK information for the PDSCH reception as
described in clause 9.2.3 and
![](media/image7.wmf){width="0.5833333333333334in"
height="0.2604166666666667in"} is a number of slots per subframe for the
SCS configuration ![](media/image8.wmf){width="0.17708333333333334in"
height="0.17708333333333334in"} of the PUCCH transmission as defined in
\[4, TS 38.211\].

With reference to slots for PUCCH transmissions, if a UE receives a
deactivation command \[11, TS 38.321\] for a secondary cell ending in
slot ![](media/image9.wmf){width="0.125in" height="0.15625in"}, the UE
applies the corresponding actions in \[11, TS 38.321\] no later than the
minimum requirement defined in \[10, TS 38.133\], except for the actions
related to CSI reporting on an activated serving cell which the UE
applies in slot ![](media/image4.wmf){width="0.3229166666666667in"
height="0.19791666666666666in"}*.*

If the *sCellDeactivationTimer* associated with the secondary cell
expires in slot ![](media/image9.wmf){width="0.125in"
height="0.15625in"}, the UE applies the corresponding actions in \[11,
TS 38.321\] no later than the minimum requirement defined in \[10, TS
38.133\], except for the actions related to CSI reporting on an
activated serving cell which the UE applies in the first slot that is
after slot ![](media/image10.wmf){width="0.8854166666666666in"
height="0.21875in"} where ![](media/image11.wmf){width="0.125in"
height="0.15625in"} is the SCS configuration for PDSCH reception on the
secondary cell.