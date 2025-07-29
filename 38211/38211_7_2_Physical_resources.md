## 7.2 Physical resources

The frame structure and physical resources the UE shall assume when
receiving downlink transmissions are defined in Clause 4.

The following antenna ports are defined for the downlink:

\- Antenna ports starting with 1000 for PDSCH

\- Antenna ports starting with 2000 for PDCCH

\- Antenna ports starting with 3000 for channel-state information
reference signals

\- Antenna ports starting with 4000 for SS/PBCH block transmission

\- Antenna ports starting with 5000 for positioning reference signals

The UE shall not assume that two antenna ports are quasi co-located with
respect to any QCL type unless specified otherwise.

For DM-RS associated with a PDSCH, the channel over which a PDSCH symbol
on one antenna port is conveyed can be inferred from the channel over
which a DM-RS symbol on the same antenna port is conveyed only if the
two symbols are within the same resource as the scheduled PDSCH, in the
same slot, and in the same PRG as described in clause 5.1.2.3 of \[6, TS
38.214\].

For DM-RS associated with a PDCCH, the channel over which a PDCCH symbol
on one antenna port is conveyed can be inferred from the channel over
which a DM-RS symbol on the same antenna port is conveyed only if the
two symbols are within resources for which the UE may assume the same
precoding being used as described in clause 7.3.2.2.

For DM-RS associated with a PBCH, the channel over which a PBCH symbol
on one antenna port is conveyed can be inferred from the channel over
which a DM-RS symbol on the same antenna port is conveyed only if the
two symbols are within a SS/PBCH block transmitted within the same slot,
and with the same block index according to clause 7.4.3.1.