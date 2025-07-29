### 5.18.21 PPW Activation/Deactivation Command

If the UE is configured with pre-configured PPW, the network may send DL
MAC CE for PPW Activation/Deactivation Command to the UE as in clause
6.1.3.42. For the activated PPW, the UE shall follow the specified UE
behaviour in clause 5.24.

Upon activation of DL BWP, the PPW(s) configured for that BWP are
considered deactivated. Upon reconfiguration of PPW(s) of the active DL
BWP, all the PPW(s) for that BWP are considered deactivated.

Upon the reception of the MAC CE for PPW Activation/Deactivation
Command, the MAC entity shall:

1\> if the DL MAC CE for PPW Activation/Deactivation Command indicates
the deactivation of a pre-configured PPW:

2\> deactivate the PPW.

1\> else if the DL MAC CE for PPW Activation/Deactivation Command
indicates the activation of a pre-configured PPW:

2\> activate the PPW according to the procedure specified in clause
5.24.