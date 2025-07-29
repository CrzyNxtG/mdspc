### 9.2.4 UE procedure for reporting SR

A UE can be provided by *SchedulingRequestResourceConfig* a set of
configurations for SR in a PUCCH transmission using either PUCCH format
0 or PUCCH format 1.

A UE can be provided by *schedulingRequestID-BFR-SCell* a configuration
for LRR in a PUCCH transmission using either PUCCH format 0 or PUCCH
format 1.

A UE can be provided by *schedulingRequestID-BFR* a first configuration
for LRR and, if the UE provides *twoLRRcapability*, the UE can be
provided by *schedulingRequestID-BFR2* a second configuration for LRR in
a PUCCH transmission using either PUCCH format 0 or PUCCH format 1.

A UE can be provided by *schedulingRequestID-LBT-SCell* a configuration
for consistent LBT failure recovery, as described in \[11, TS 38.321\],
in a PUCCH transmission using either PUCCH format 0 or PUCCH format 1.
The UE can be provided, by *phy-PriorityIndex* in
*SchedulingRequestResourceConfig*, a priority index 0 or a priority
index 1 for the SR. If the UE is not provided a priority index for SR,
the priority index is 0.

The UE is also provided a periodicity ${SR}_{PERIODICITY}$ in symbols or
slots and an offset ${SR}_{OFFSET}$ in slots by *periodicityAndOffset*
for a PUCCH transmission conveying SR. If ${SR}_{PERIODICITY}$ is larger
than one slot, the UE determines a SR transmission occasion in a PUCCH
to be in a slot with number $n_{s,f}^{\mu}$ \[4, TS 38.211\] in a frame
with number $n_{f}$ if
$\left( {n_{f} \cdot N_{slot}^{frame,\mu} + n}_{s,f}^{\mu} - {SR}_{OFFSET} \right)mod{SR}_{PERIODICITY} = 0$.

If ${SR}_{PERIODICITY}$ is one slot, the UE expects that
${SR}_{OFFSET} = 0$ and every slot is a SR transmission occasion in a
PUCCH.

If ${SR}_{PERIODICITY}$ is smaller than one slot, the UE determines a SR
transmission occasion in a PUCCH to start in a symbol with index $l$
\[4, TS 38.211\] if
$\left( l - l_{0}mod{SR}_{PERIODICITY} \right)mod{SR}_{PERIODICITY} = 0$
where $l_{0}$ is the value of *startingSymbolIndex*.

If the UE determines that, for a SR transmission occasion in a PUCCH,
the number of symbols available for the PUCCH transmission in a slot is
smaller than the value provided by *nrofSymbols*, the UE does not
transmit the PUCCH in the slot.

SR transmission occasions in a PUCCH are subject to the limitations for
UE transmissions described in clause 11.1, clause 11.1.1 and clause
17.2.

The UE transmits a PUCCH in the PUCCH resource for the corresponding SR
configuration only when the UE transmits a positive SR. For a positive
SR transmission using PUCCH format 0, the UE transmits the PUCCH as
described in \[4, TS 38.211\] by obtaining $m_{0}$ as described for
HARQ-ACK information in clause 9.2.3 and by setting $m_{cs} = 0$. For a
positive SR transmission using PUCCH format 1, the UE transmits the
PUCCH as described in \[4, TS 38.211\] by setting $b(0) = 0$.