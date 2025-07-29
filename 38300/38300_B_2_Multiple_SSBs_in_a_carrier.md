# B.2 Multiple SSBs in a carrier

For a UE in RRC_CONNECTED, the BWPs configured by a serving cell may
overlap in the frequency domain with the BWPs configured for other UEs
by other cells within a carrier. Multiple SSBs may also be transmitted
within the frequency span of a carrier used by the serving cell.
However, from the UE perspective, each serving cell is associated to at
most a single SSB. Figure B.2-1 below describes a scenario with multiple
SSBs in a carrier, identifying two different cells (NCGI = 5, associated
to SSB1, and NCGI = 6, associated to SSB3) with overlapping BWPs, and
where RRM measurements can be configured to be performed by the UE on
each of the available SSBs, i.e. SSB1, SSB2, SSB3 and SSB4.

![](media/image120.emf)

Figure B.2-1: Example of multiple SSBs in a carrier