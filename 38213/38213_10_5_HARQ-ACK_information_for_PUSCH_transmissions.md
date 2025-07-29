## 10.5 HARQ-ACK information for PUSCH transmissions

A UE can be configured a number of search space sets to monitor PDCCH
for detecting a DCI format 0_1 with a DFI flag field and CRC scrambled
with a CS-RNTI provided by *cs-RNTI*. The UE determines that the DCI
format provides HARQ-ACK information for PUSCH transmissions based on
when a DFI flag field value is set to \'1\', if a PUSCH transmission is
configured by *ConfiguredGrantConfig*.

The HARQ-ACK information corresponds to transport blocks in PUSCH
transmissions for all HARQ processes for a serving cell of a PDCCH
reception that provides DCI format 0_1 or, if DCI format 0_1 includes a
carrier indicator field, for a serving cell indicated by a value of the
carrier indicator field.

For a PUSCH transmission configured by *ConfiguredGrantConfig*, HARQ-ACK
information for a transport block of a corresponding HARQ process number
is valid if a first symbol of the PDCCH reception is after a last symbol
of the PUSCH transmission, or of any repetition of the PUSCH
transmission, by a number of symbols provided by *cg-minDFI-Delay*.

For an initial transmission by a UE of a transport block in a PUSCH
configured by *ConfiguredGrantConfig*, if the UE receives a CG-DFI that
provides HARQ-ACK information for the transport block, the UE assumes
that the transport block was correctly decoded if the HARQ-ACK
information value is ACK; otherwise, the UE assumes that the transport
block was not correctly decoded.

For a PUSCH transmission scheduled by a DCI format, if the UE receives a
CG-DFI that provides HARQ-ACK information for the transport block, the
UE assumes that the transport block was correctly decoded if the
HARQ-ACK information value is ACK; otherwise, the UE assumes that the
transport block was not correctly decoded.

For a PUSCH transmission scheduled by a DCI format, HARQ-ACK information
for a transport block of a corresponding HARQ process number is valid if
a first symbol of the PDCCH reception is after a last symbol of the
PUSCH transmission by a number of symbols provided by *cg-minDFI-Delay*
or, if the PUSCH transmission is over multiple slots,

\- after a last symbol of the PUSCH transmission in a first slot from
the multiple slots by a number of symbols provided by *cg-minDFI-Delay*,
if a value of the HARQ-ACK information is ACK.

\- after a last symbol of the PUSCH transmission in a last slot from the
multiple slots by a number of symbols provided by *cg-minDFI-Delay*, if
a value of the HARQ-ACK information is NACK.

UE does not expect to be configured with different *cg-minDFI-Delay*
among multiple *ConfiguredGrantConfig* in one BWP.