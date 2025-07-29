### 5.4.2 Receive operation

For AM DRBs, when a PDCP status report is received in the downlink or in
the sidelink, the transmitting PDCP entity shall:

\- consider for each PDCP SDU, if any, with the bit in the bitmap set to
\'1\', or with the associated COUNT value less than the value of FMC
field as successfully delivered, and discard the PDCP SDU as specified
in clause 5.3.