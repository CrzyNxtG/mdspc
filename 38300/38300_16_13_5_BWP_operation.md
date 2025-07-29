### 16.13.5 BWP operation

An (e)RedCap UE in RRC_IDLE or RRC_INACTIVE monitors paging only in an
initial BWP (default or RedCap specific) associated with CD-SSB and
performs cell (re-)selection and related measurements on the CD-SSB. If
a RedCap-specific initial UL BWP is configured and NUL is selected,
(e)RedCap UEs shall use only the RedCap-specific initial UL BWP to
perform RACH procedure in RRC_IDLE and RRC_INACTIVE or to perform CG-SDT
procedure (as described in clause 18.0) in RRC_INACTIVE.

An (e)RedCap UE may be configured with multiple NCD-SSBs provided that
each BWP is configured with at most one SSB. NCD-SSB may be configured
for an (e)RedCap UE in RRC_CONNECTED to perform RLM, BFD, and RRM
measurements and RA resource selection when the active BWP does not
contain CD-SSB.

An (e)RedCap UE may be configured with NCD-SSB for a RedCap-specific
initial DL BWP to perform SDT procedure in RRC_INACTIVE (as described in
clause 18.0) in case the RedCap-specific initial DL BWP does not contain
CD-SSB.