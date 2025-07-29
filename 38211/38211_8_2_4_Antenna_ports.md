### 8.2.4 Antenna ports

An antenna port is defined in clause 4.4.1.

The following antenna ports are defined for the sidelink:

\- Antenna ports starting with 1000 for PSSCH

\- Antenna ports starting with 2000 for PSCCH

\- Antenna ports starting with 3000 for CSI-RS

\- Antenna ports starting with 4000 for S-SS/PSBCH block

\- Antenna ports starting with 5000 for PSFCH

\- Antenna ports starting with 6000 for SL PRS

For DM-RS associated with a PSBCH, the channel over which a PSBCH symbol
on one antenna port is conveyed can be inferred from the channel over
which a DM-RS symbol on the same antenna port is conveyed only if the
two symbols are within a S-SS/PSBCH block transmitted within the same
slot, and with the same block index.

For DM-RS associated with a PSSCH, the channel over which a PSSCH symbol
on one antenna port is conveyed can be inferred from the channel over
which a DM-RS symbol on the same antenna port is conveyed only if the
two symbols are within the same frequency resource as the scheduled
PSSCH and in the same slot.

For DM-RS associated with a PSCCH, the channel over which a PSCCH symbol
on one antenna port is conveyed can be inferred from the channel over
which a DM-RS symbol on the same antenna port is conveyed only if the
two symbols are within the same frequency resource as the transmitted
PSCCH and in the same slot.