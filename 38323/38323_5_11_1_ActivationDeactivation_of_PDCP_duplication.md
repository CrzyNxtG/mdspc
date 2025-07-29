### 5.11.1 Activation/Deactivation of PDCP duplication

For the PDCP entity configured with *pdcp-Duplication*, the transmitting
PDCP entity shall:

\- for SRBs:

\- activate the PDCP duplication;

\- for DRBs:

\- if the activation of PDCP duplication is indicated for the DRB:

\- activate the PDCP duplication for the DRB;

\- if the activation of PDCP duplication is indicated for at least one
associated RLC entities:

\- activate the PDCP duplication for the indicated associated RLC
entities;

\- activate the PDCP duplication for the DRB;

\- if the deactivation of PDCP duplication is indicated for the DRB:

\- deactivate the PDCP duplication for the DRB;

\- if the deactivation of PDCP duplication is indicated for at least one
associated RLC entities:

\- deactivate the PDCP duplication for the indicated associated RLC
entities;

\- if all associated RLC entities other than the primary RLC entity are
deactivated for PDCP duplication:

\- deactivate the PDCP duplication for the DRB.

NOTE: How to identify \"associated RLC entity\" or equivalent entity in
N3C indirect path for a configured DRB is out of scope of 3GPP.