### 5.18.34 Activation/deactivation of PSI-based SDU discard

The network activates and deactivates PSI-based SDU discard by sending
the PSI-Based SDU Discard Activation/Deactivation MAC CE described in
clause 6.1.3.73. The PSI-based SDU discard is initially deactivated upon
(re-)configuration by upper layers and after reconfiguration with sync.

The MAC entity shall for each DRB configured with
*discardTimerForLowImportance*:

1\> if a PSI-Based SDU Discard Activation/Deactivation MAC CE is
received activating the PSI-based SDU discard for the DRB:

2\> indicate the activation of the PSI-based SDU discard for the DRB to
upper-layers.

1\> if a PSI-Based SDU Discard Activation/Deactivation MAC CE is
received deactivating the PSI-based SDU discard for the DRB:

2\> indicate the deactivation of the PSI-based SDU discard for the DRB
to upper-layers.