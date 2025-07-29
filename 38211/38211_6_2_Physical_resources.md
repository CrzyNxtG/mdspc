## 6.2 Physical resources

The frame structure and physical resources the UE shall use when
transmitting in the uplink transmissions are defined in Clause 4.

The following antenna ports are defined for the uplink:

\- Antenna ports starting with 0 for demodulation reference signals for
PUSCH

\- Antenna ports starting with 1000 for SRS, PUSCH

\- Antenna ports starting with 2000 for PUCCH

\- Antenna port 4000 for PRACH

If PUSCH repetition Type B as described in clause 6.1 of \[6, TS38.214\]
is applied to a physical channel, the UE transmission shall be such that
the channel over which a symbol on the antenna port used for uplink
transmission is conveyed can be inferred from the channel over which
another symbol on the same antenna port is conveyed if the two symbols
correspond to the same actual repetition of a PUSCH transmission with
repetition Type B.

If intra-slot frequency hopping is not enabled for a physical channel
and PUSCH repetition Type B is not applied to the physical channel, the
UE transmission shall be such that the channel over which a symbol on
the antenna port used for uplink transmission is conveyed can be
inferred from the channel over which another symbol on the same antenna
port is conveyed if the two symbols correspond to the same slot.

If intra-slot frequency hopping is enabled for a physical channel, the
UE transmission shall be such that the channel over which a symbol on
the antenna port used for uplink transmission is conveyed can be
inferred from the channel over which another symbol on the same antenna
port is conveyed only if the two symbols correspond to the same
frequency hop, regardless of whether the frequency hop distance is zero
or not.

If DM-RS bundling is applied to PUSCH and/or PUCCH repetitions and/or
transport-block processing over multiple slots as described in clause
6.1.7 of \[6, 38.214\], the UE transmission shall be such that the
channel over which a symbol on the antenna port used for uplink
transmission is conveyed can be inferred from the channel over which
another symbol on the same antenna port is conveyed if the two symbols
are transmitted within the same actual time-domain window.