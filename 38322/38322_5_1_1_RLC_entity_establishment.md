### 5.1.1 RLC entity establishment

When upper layers request an RLC entity establishment, the UE shall:

\- establish a RLC entity;

\- set the state variables of the RLC entity to initial values;

\- follow the procedures in clause 5.2.

For NR sidelink groupcast and broadcast or SL-SRB4, when receiving the
first UMD PDU from a Source Layer 2 ID and Destination Layer 2 ID pair
for an LCID, and there is not yet a corresponding receiving RLC entity
for a radio bearer, the UE shall:

\- establish a receiving RLC entity;

\- set the state variables of the RLC entity to initial values;

\- follow the procedures in clause 5.2.

NOTE: The receiving RLC entity of SL-SRB0 and SL-SRB1 is established
same as NR sidelink groupcast and broadcast.