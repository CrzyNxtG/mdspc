### 5.7.3 Physical sidelink channels and signals

Physical Sidelink Control Channel (PSCCH) indicates resource and other
transmission parameters used by a UE for PSSCH. PSCCH transmission is
associated with a DM-RS.

Physical Sidelink Shared Channel (PSSCH) transmits the TBs of data
themselves, and control information for HARQ procedures and CSI feedback
triggers, etc. At least 6 OFDM symbols within a slot are used for PSSCH
transmission. PSSCH transmission is associated with a DM-RS and may be
associated with a PT-RS.

Physical Sidelink Feedback Channel (PSFCH) carries HARQ feedback over
the sidelink from a UE which is an intended recipient of a PSSCH
transmission to the UE which performed the transmission. PSFCH sequence
is transmitted in one PRB repeated over two OFDM symbols near the end of
the sidelink resource in a slot.

The Sidelink synchronization signal consists of sidelink primary and
sidelink secondary synchronization signals (S-PSS, S-SSS), each
occupying 2 symbols and 127 subcarriers. Physical Sidelink Broadcast
Channel (PSBCH) occupies 9 and 7 symbols for normal and extended CP
cases respectively, including the associated DM-RS.