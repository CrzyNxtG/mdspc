## 5.10 Activation/Deactivation of PDCP duplication

If one or more DRBs are configured with PDCP duplication, the network
may activate and deactivate the PDCP duplication for all or a subset of
associated RLC entities for the configured DRB(s).

The PDCP duplication for the configured DRB(s) is activated and
deactivated by:

\- receiving the Duplication Activation/Deactivation MAC CE described in
clause 6.1.3.11;

\- receiving the Duplication RLC Activation/Deactivation MAC CE
described in clause 6.1.3.32;

\- indication by RRC.

The PDCP duplication for all or a subset of associated RLC entities for
the configured DRB(s) is activated and deactivated by:

\- receiving the Duplication RLC Activation/Deactivation MAC CE
described in clause 6.1.3.32;

\- indication by RRC.

The PDCP duplication for all associated RLC entities for the configured
DRB(s) is activated by:

\- receiving an uplink grant addressed to CS-RNTI with NDI=1 for a
logical channel associated with the DRB configured with
*survivalTimeStateSupport*, described in clause 5.4.1.

The MAC entity shall for each DRB configured with PDCP duplication:

1\> if a Duplication Activation/Deactivation MAC CE is received
activating the PDCP duplication of the DRB:

2\> indicate the activation of PDCP duplication of the DRB to upper
layers.

1\> if a Duplication Activation/Deactivation MAC CE is received
deactivating the PDCP duplication of the DRB:

2\> indicate the deactivation of PDCP duplication of the DRB to upper
layers.

1\> if a Duplication RLC Activation/Deactivation MAC CE is received
activating PDCP duplication for associated RLC entities of a DRB
configured with PDCP duplication:

2\> indicate the activation of PDCP duplication for the indicated
secondary RLC entity(ies) of the DRB to upper layers.

1\> if a Duplication RLC Activation/Deactivation MAC CE is received
deactivating PDCP duplication for associated RLC entities of a DRB
configured with PDCP duplication:

2\> indicate the deactivation of PDCP duplication for the indicated
secondary RLC entity(ies) of the DRB to upper layers.

1\> if activation of a PDCP duplication for all configured RLC entities
is triggered for the DRB as specified in clause 5.4.1:

2\> indicate the activation of PDCP duplication for all configured RLC
entities of the DRB to upper layers.

NOTE: How to identify \"associated RLC entity\" or equivalent entity in
N3C indirect path for a configured DRB is out of scope of 3GPP.