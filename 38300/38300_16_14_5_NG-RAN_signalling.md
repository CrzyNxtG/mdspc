### 16.14.5 NG-RAN signalling

The Cell Identity, as defined in TS 38.413 \[26\] and TS 38.423 \[50\],
used in following cases corresponds to a Mapped Cell ID, irrespective of
the orbit of the NTN payload or the types of service links supported:

\- The Cell Identity indicated by the gNB to the Core Network as part of
the User Location Information;

\- The Cell Identity used for Paging Optimization in NG interface;

\- The Cell Identity used for Area of Interest;

\- The Cell Identity used for PWS.

The Cell Identity included within the target identification of the
handover messages allows identifying the correct target cell. The cell
identity used in the NG and Xn handover messages, Xn Setup and Xn NG-RAN
Node Configuration Update procedures is expected to be Uu Cell ID.

The Cell Identities used in the RAN Paging Area during Xn RAN paging
allow the identification of the correct target cells for RAN paging.

NOTE 1: The Cell Identity used for RAN Paging is assumed to typically
represent a Uu Cell ID.

The mapping between Mapped Cell IDs and geographical areas is configured
in the RAN and Core Network.

NOTE 2: A specific geographical location may be mapped to multiple
Mapped Cell ID(s), and such Mapped Cell IDs may be configured to
indicate differerent geographical areas (e.g. overlapping and/or with
different dimensions).

The gNB is responsible for constructing the Mapped Cell ID based on the
UE location information received from the UE, if available. The mapping
may be pre-configured (e.g., up to operator\'s policy) or up to
implementation.

NOTE 3: As described in TS 23.501 \[3\], the User Location Information
may enable the AMF to determine whether the UE is allowed to operate at
its present location. Special Mapped Cell IDs or TACs may be used to
indicate areas outside the serving PLMN\'s country.

The gNB reports the broadcasted TAC(s) of the selected PLMN to the AMF
as part of ULI. In case the gNB knows the UE\'s location information,
the gNB may determine the TAI the UE is currently located in and provide
that TAI to the AMF as part of ULI.