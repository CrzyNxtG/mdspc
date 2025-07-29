### 5.1.3 PDCP entity release

When upper layers request a PDCP entity release for a radio bearer for
Uu or PC5 interface, the UE shall:

\- discard all stored PDCP SDUs and PDCP PDUs in the transmitting PDCP
entity;

\- for UM DRBs, AM DRBs, UM MRBs and AM MRBs, deliver the PDCP SDUs
stored in the receiving PDCP entity to upper layers in ascending order
of associated COUNT values after performing header decompression, if not
decompressed before;

\- release the PDCP entity for the radio bearer.

NOTE: For NR sidelink communication for groupcast and broadcast or for
sidelink SRB4, the receiving PDCP entity release for an SLRB is up to UE
implementation.