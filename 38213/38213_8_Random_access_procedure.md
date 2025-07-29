# 8 Random access procedure

Prior to initiation of the physical random access procedure, Layer 1
receives from higher layers a set of SS/PBCH block indexes and provides
to higher layers a corresponding set of RSRP measurements.

Prior to initiation of the physical random access procedure, Layer 1 may
receive from higher layers an indication to perform a Type-1 random
access procedure, as described in clauses 8.1 through 8.4, or a Type-2
random access procedure as described in clauses 8.1 through 8.2A.

Prior to initiation of the physical random access procedure, Layer 1
receives the following information from the higher layers:

\- Configuration of physical random access channel (PRACH) transmission
parameters (PRACH preamble format, time resources, and frequency
resources for PRACH transmission).

\- Parameters for determining the root sequences and their cyclic shifts
in the PRACH preamble sequence set (index to logical root sequence
table, cyclic shift (![](media/image62.wmf){width="0.3020833333333333in"
height="0.2604166666666667in"}), and set type (unrestricted, restricted
set A, or restricted set B)).

From the physical layer perspective, the Type-1 L1 random access
procedure includes the transmission of random access preamble (Msg1) in
a PRACH, random access response (RAR) message with a PDCCH/PDSCH (Msg2),
and when applicable, the transmission of a PUSCH scheduled by a RAR UL
grant, and PDSCH for contention resolution.

From the physical layer perspective, the Type-2 L1 random access
procedure includes the transmission of random access preamble in a PRACH
and of a PUSCH (MsgA) and the reception of a RAR message with a
PDCCH/PDSCH (MsgB), and when applicable, the transmission of a PUSCH
scheduled by a fallback RAR UL grant, and PDSCH for contention
resolution.

If a random access procedure is initiated by a PDCCH order to the UE, a
PRACH transmission is with a same SCS as a PRACH transmission initiated
by higher layers.

If a UE is configured with two UL carriers for a serving cell or a
candidate cell and the UE detects a PDCCH order, the UE uses the UL/SUL
indicator field value from the detected PDCCH order to determine the UL
carrier for the corresponding PRACH transmission. If a UE is configured
with two UL carriers for a candidate cell and the UE detects an LTM Cell
Switch Command MAC CE \[11, TS 38.321\] that initiated a CFRA, the UE
uses the S/U field value from the MAC CE to determine the UL carrier for
the corresponding PRACH transmission.