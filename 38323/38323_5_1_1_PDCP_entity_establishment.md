### 5.1.1 PDCP entity establishment

When upper layers request a PDCP entity establishment for a radio bearer
for Uu or PC5 interface; or for NR sidelink communication for groupcast
and broadcast or for sidelink SRB4, when receiving the first PDCP PDU,
and there is not yet a corresponding PDCP entity, the UE shall:

\- establish a PDCP entity for the radio bearer;

\- set the state variables of the PDCP entity to initial values;

\- follow the procedures in clause 5.2.

NOTE: The receiving PDCP entity of sidelink SRB0 and sidelink SRB1 is
established same as NR sidelink groupcast and broadcast.