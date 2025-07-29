### 5.8.1a Downlink for Multicast

MBS Semi-Persistent Scheduling (SPS) is only applicable for UEs in
RRC_CONNECTED and is configured by RRC on one Serving Cell per BWP.
Multiple assignments can be active simultaneously in the same BWP.

For the DL MBS SPS, a DL assignment is provided by PDCCH, and stored or
cleared based on L1 signalling indicating SPS activation or
deactivation.

RRC configures the following parameters when the MBS SPS is configured:

\- *cs-RNTI*: CS-RNTI for MBS SPS deactivation, PTP for PTM
retransmission if configured;

\- *g-cs-RNTI*: G-CS-RNTI for activation, deactivation, and
retransmission;

\- *nrofHARQ-Processes*: the number of configured HARQ processes for MBS
SPS;

\- *harq-ProcID-Offset*: Offset of HARQ process for MBS SPS;

\- *periodicity*: periodicity of configured downlink assignment for MBS
SPS.

When the MBS SPS is released by upper layers, all the corresponding
configurations shall be released.

After a downlink assignment is configured for MBS SPS, the MAC entity
shall consider sequentially that the N^th^ downlink assignment occurs in
the slot for which:

> (*numberOfSlotsPerFrame* × SFN + slot number in the frame) =\
> \[(*numberOfSlotsPerFrame* × SFN~start\ time~ + slot~start\ time~) + N
> × *periodicity* × *numberOfSlotsPerFrame* / 10\]\
> modulo (1024 × *numberOfSlotsPerFrame*)

where SFN~start\ time~ and slot~start\ time~ are the SFN and slot,
respectively, of the first transmission of PDSCH where the configured
downlink assignment was (re-)initialised.