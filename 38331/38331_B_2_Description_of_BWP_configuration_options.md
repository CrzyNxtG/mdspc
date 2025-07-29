# B.2 Description of BWP configuration options

There are two possible ways to configure BWP#0 (i.e. the initial BWP)
for a UE:

1\) Configure *BWP-DownlinkCommon* and *BWP-UplinkCommon* in
*ServingCellConfigCommon*, but do not configure dedicated configurations
in *BWP-DownlinkDedicated* or *BWP-UplinkDedicated* in
*ServingCellConfig*.

2\) Configure both *BWP-DownlinkCommon* and *BWP-UplinkCommon* in
*ServingCellConfigCommon* and configure dedicated configurations in at
least one of *BWP-DownlinkDedicated* or *BWP-UplinkDedicated* in
*ServingCellConfig*.

The same way of configuration is used for UL BWP#0 and DL BWP#0 if both
are configured.

With the first option (illustrated by figure B2-1 below), the BWP#0 is
not considered to be an RRC-configured BWP, i.e., UE only supporting one
BWP can still be configured with BWP#1 in addition to BWP#0 when using
this configuration. The BWP#0 can still be used even if it does not have
the dedicated configuration, albeit in a more limited manner since only
the SIB1-defined configurations are available. For example, only DCI
format 1_0 can be used with BWP#0 without dedicated configuration, so
changing to another BWP requires RRCReconfiguration since DCI format 1_0
doesn\'t support DCI-based switching.

![](media/image70.emf)

Figure B2-1: BWP#0 configuration without dedicated configuration

With the second option (illustrated by figure B2-2 below), the BWP#0 is
considered to be an RRC-configured BWP, i.e. UE only supporting one BWP
cannot be configured with BWP#1 in addition to BWP#0 when using this
configuration. However, UE supporting more than one BWP can still switch
to and from BWP#0 e.g. via DCI normally, and there are no explicit
limitations to using the BWP#0 (compared to the first option).

![](media/image71.emf)

Figure B2-2: BWP#0 configuration with dedicated configuration

For BWP#0, the *BWP-DownlinkCommon* and *BWP-UplinkCommon* in
*ServingCellConfigCommon* should match the parameters configured by MIB
and SIB1 (if provided) in the corresponding serving cell.

If an RedCap-specific initial DL BWP is configured, for BWP switching,
the BWP #0 always maps to the RedCap-specific initial DL BWP. If a
RedCap-specific initial UL BWP is configured, for BWP switching on NUL,
the BWP #0 always maps to the RedCap-specific initial UL BWP, for BWP
switching on SUL, the BWP#0 always maps to the initial UL BWP.