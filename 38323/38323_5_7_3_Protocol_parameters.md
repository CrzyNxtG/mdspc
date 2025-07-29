### 5.7.3 Protocol parameters

RFC 5795 \[7\] has configuration parameters that are mandatory and that
must be configured by upper layers between compressor and decompressor
peers ; these parameters define the ROHC channel. The ROHC channel is a
unidirectional channel, i.e. if *rohc* is configured there is one
channel for the downlink and one for the uplink, and if *uplinkOnlyROHC*
is configured there is only one channel for the uplink. There is thus
one set of parameters for each channel, and if *rohc* is configured the
same values shall be used for both channels belonging to the same PDCP
entity.

These parameters are categorized in two different groups, as defined
below:

\- M: Mandatory and configured by upper layers;

\- N/A: Not used in this specification.

The usage and definition of the parameters shall be as specified below.

\- MAX_CID (M): This is the maximum CID value that can be used. One CID
value shall always be reserved for uncompressed flows. The parameter
MAX_CID is configured by upper layers (*maxCID* in TS 38.331 \[3\]);

\- LARGE_CIDS: This value is not configured by upper layers, but rather
it is inferred from the configured value of MAX_CID according to the
following rule:

\- If MAX_CID \> 15 then LARGE_CIDS = TRUE else LARGE_CIDS = FALSE;

\- PROFILES (M): Profiles are used to define which profiles are allowed
to be used by the UE. The list of supported profiles is described in
clause 5.7.1. The parameter PROFILES is configured by upper layers
(*profiles* for uplink and downlink, *sl-RoHC-Profiles* in
*SidelinkPreconfigNR* for sidelink in TS 38.331 \[3\]);

\- FEEDBACK_FOR (N/A): This is a reference to the channel in the
opposite direction between two compression endpoints and indicates to
what channel any feedback sent refers to. Feedback received on one ROHC
channel for this PDCP entity shall always refer to the ROHC channel in
the opposite direction for this same PDCP entity;

\- MRRU (N/A): ROHC segmentation is not used.