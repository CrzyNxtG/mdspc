## 8.1 UE procedure for transmitting the physical sidelink shared channel

Each PSSCH transmission is associated with an PSCCH transmission.

That PSCCH transmission carries the 1^st^ stage of the SCI associated
with the PSSCH transmission; the 2^nd^ stage of the associated SCI is
carried within the resource of the PSSCH.

If the UE transmits SCI format 1-A on PSCCH according to a PSCCH
resource configuration in slot *n* and PSCCH resource *m*, then for the
associated PSSCH transmission in the same slot

\- one transport block is transmitted with up to two layers;

\- The number of layers (ʋ) is determined according to the \'*Number of
DMRS port\'* field in the SCI;

\- The set of consecutive symbols within the slot for transmission of
the PSSCH is determined according to clause 8.1.2.1;

\- The set of contiguous or interlaced resource blocks for transmission
of the PSSCH is determined according to clause 8.1.2.2;

Transform precoding is not supported for PSSCH transmission.

Only wideband precoding is supported for PSSCH transmission.

The DM-RS antenna ports
![cid:image011.png@01D5F222.20AEBCB0](media/image806.png){width="0.6465277777777778in"
height="0.21736111111111112in"} in Clause 8.4.1.1.2 of \[4, TS 38.211\]
are determined according to the ordering of DM-RS port(s) given by
Tables 8.3.1.1-3 in Clause 8.3.1.1 of \[5, TS 38.212\].

The UE shall set the contents of the SCI format 2-A as follows:

\- the UE shall set value of the *\'HARQ process number\'* field as
indicated by higher layers.

\- the UE shall set value of the \'*NDI*\' field as indicated by higher
layers.

\- the UE shall set value of the \'*Redundancy version*\' field as
indicated by higher layers.

\- the UE shall set value of the \'*Source ID*\' field as indicated by
higher layers.

\- the UE shall set value of the \'*Destination ID*\' field as indicated
by higher layers.

\- the UE shall set value of the \'*HARQ feedback enabled/disabled
indicator*\' field as indicated by higher layers.

\- the UE shall set value of the \'*Cast type indicator*\' field as
indicated by higher layers.

\- the UE shall set value of the \'*CSI request*\' field as indicated by
higher layers.

\- the UE shall set value of the \'*CAPC*\' field, if present, as
indicated by higher layers.

\- the UE shall set value of the \'*COT sharing cast type*\' field, if
present, as indicated by higher layers.

\- the UE shall set value of the \'*COT sharing Additional ID\'* field,
if present, as indicated by higher layers.

\- the UE shall set value of the \'*Remaining COT duration\'* field, if
present, as indicated by higher layers.

The UE shall set the contents of the SCI formats 2-B as follows:

\- the UE shall set value of the \'*HARQ process number*\' field as
indicated by higher layers.

\- the UE shall set value of the \'*NDI*\' field as indicated by higher
layers.

\- the UE shall set value of the \'*Redundancy version*\' field as
indicated by higher layers.

\- the UE shall set value of the \'*Source ID*\' field as indicated by
higher layers.

\- the UE shall set value of the \'*Destination ID*\' field as indicated
by higher layers.

\- the UE shall set value of the \'*HARQ feedback enabled/disabled
indicator*\' field as indicated by higher layers.

\- the UE shall set value of the \'*Zone ID*\' field as indicated by
higher layers.

\- the UE shall set the \'*Communication range requirement*\' field as
indicated by higher layers.

The UE shall set the contents of the SCI format 2-C as follows:

\- the UE shall set value of the *\'HARQ process number\'* field as
indicated by higher layers.

\- the UE shall set value of the \'*NDI*\' field as indicated by higher
layers.

\- the UE shall set value of the \'*Redundancy version*\' field as
indicated by higher layers.

\- the UE shall set value of the \'*Source ID*\' field as indicated by
higher layers.

\- the UE shall set value of the \'*Destination ID*\' field as indicated
by higher layers.

\- the UE shall set value of the \'*HARQ feedback enabled/disabled
indicator*\' field as indicated by higher layers.

\- the UE shall set value of the \'*CSI request*\' field as indicated by
higher layers.

\- the UE shall set value of \'*Providing/Requesting indicator*\' field
as indicated by higher layers.

\- if \'*Providing/Requesting indicator*\' indicates SCI format 2-C is
used to convey an explicit request for inter-UE coordination
information:

\- the UE shall set value of the \'*Priority*\' field as indicated by
higher layers.

\- the UE shall set value of the \'*Number of subchannels*\' field as
indicated by higher layers.

\- the UE shall set value of the \'*Number of RB sets*\' field as
indicated by higher layers if the higher layer parameter
*sl-TransmissionStructureForPSCCHandPSSCH* in *SL-BWP-Config* is
configured to \'interlaceRB\'.

\- the UE shall set value of the \'*Resource reservation period*\' field
as indicated by higher layers.

\- the UE shall set value of the \'*Resource selection window
location*\' field as indicated by higher layers.

\- the UE shall set value of the \'*Resource set type*\' field as
indicated by higher layers if higher layer parameter
*sl-DetermineResourceType* is configured to \'UE-B\'s request\';
otherwise this field is omitted.

\- if \'*Providing/Requesting indicator*\' indicates SCI format 2-C is
used to convey inter-UE coordination information:

\- the UE shall set value of the \'*Resource set type*\' field as
indicated by higher layers.

\- the UE shall set value of the \'*Resource combination(s)*\' field
(clause 8.1.5A) as indicated by higher layers.

\- the UE shall set value of the *\'Lowest subchannel indices\'* as
indicated by higher layers

\- the UE shall set value of the *\'Lowest RB set indices\'* as
indicated by higher layers if the higher layer parameter
*sl-TransmissionStructureForPSCCHandPSSCH* in *SL-BWP-Config* is
configured to \'interlaceRB\'.

\- the UE shall set value of the \'*First resource location*\' as
indicated by higher layers

\- the UE shall set value of the \'*Reference slot location*\' as
indicated by higher layers

The UE shall set the contents of the SCI format 2-D as follows:

\- the UE shall set value of the *\'SL PRS resource ID\'* field as
indicated by higher layers.

\- the UE shall set value of the *\'SL PRS request\'* field as indicated
by higher layers.

\- the UE shall set value of the *\'Embedded SCI format\'* field as
indicated by higher layers.

\- if *\'Embedded SCI format\'* indicates that SCI format 2-A is
embedded within this SCI format 2-D then the UE shall include in the
*\'Embedded SCI format payload\'* field the fields of SCI format 2-A,
set as specified above.

\- if *\'Embedded SCI format\'* indicates that SCI format 2-B is
embedded within this SCI format 2-D then the UE shall include in the
*\'Embedded SCI format payload\'* field the fields of SCI format 2-B,
set as specified above.