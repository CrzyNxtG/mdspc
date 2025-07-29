## 8.3 UE procedure for receiving the physical sidelink shared channel

For sidelink resource allocation mode 1, a UE upon detection of SCI
format 1-A on PSCCH can decode PSSCH according to the detected SCI
formats 2-A, 2-B, 2-C and 2-D, and associated PSSCH resource
configuration configured by higher layers. The UE is not required to
decode more than one PSCCH at each PSCCH resource candidate.

For sidelink resource allocation mode 2, a UE upon detection of SCI
format 1-A on PSCCH can decode PSSCH according to the detected SCI
formats 2-A, 2-B, 2-C and 2-D, and associated PSSCH resource
configuration configured by higher layers. The UE is not required to
decode more than one PSCCH at each PSCCH resource candidate.

A UE is required to decode neither the corresponding SCI formats 2-A,
2-B, 2-C, 2-D nor the PSSCH associated with an SCI format 1-A if the SCI
format 1-A indicates an MCS table that the UE does not support.

In any slot without PSFCH symbols within a resource pool, the UE can
decode PSSCH transmission starting from the first candidate starting
symbol provided by *sl-startingSymbolFirst*, and can decode, subject to
UE capability, PSSCH transmission starting from the second candidate
starting symbol provided by *sl-StartingSymbolSecond*, if
*sl-StartingSymbolFirst* and *sl-StartingSymbolSecond* are provided.