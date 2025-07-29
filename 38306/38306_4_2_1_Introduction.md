### 4.2.1 Introduction

The following clauses define the UE radio access capability parameters.
Only parameters for which there is the possibility for UEs to signal
different values are considered as UE radio access capability
parameters. Therefore, mandatory features without capability parameters
that are the same for all UEs are not listed here.

The network needs to respect the signalled UE radio access capability
parameters when configuring the UE and when scheduling the UE.

For capabilities that required to be set consistently for all FDD-FR1
bands (i.e. capabilities that are supposed to be per UE), the UE shall
also set capability values for all SUL bands with same values for
FDD-FR1 bands if SUL band is supported by the UE.

The UE may support different functionalities between FDD and TDD, and/or
between FR1 and FR2. The UE shall indicate the UE capabilities as
follows. In the table of UE capability parameter in subsequent clauses,
\"Yes\" in the column by \"FDD-TDD DIFF\" and \"FR1-FR2 DIFF\" indicates
the UE capability field can have a different value for between FDD and
TDD or between FR1 and FR2 and \"No\" indicates if it cannot. \"(Incl
FR2-2 DIFF)\" in the column by \"FR1-FR2 DIFF\" indicates the UE
capability field can have a different value for between FR2-1 and FR2-2.
Regarding to the per UE capabilities that are FDD/TDD
differentiated(i.e. capabilities indicated as \"Yes\" in the column by
\"FDD-TDD DIFF\"), the corresponding capabilities indicated by the FDD
capability is applied to SUL/SDL if SUL/SDL band is supported by the UE.
\"FD\" in the column indicates to refer the associated field
description. \"FR1 only\" or \"FR2 only\" in the column indicates the
associated feature is only supported in FR1 or FR2 and \"TDD only\"
indicates the associated feature is only supported in TDD and not
applicable to SUL/SDL carriers. \"N/A\" in the column indicates it is
not applicable to the feature (e,g. the signalling supports the UE to
have different values between FDD and TDD or between FR1 and FR2).

1\> set all fields of UE-NR/MRDC-Capability except
fdd-Add-UE-NR/MRDC/Sidelink-Capabilities,
tdd-Add-UE-NR/MRDC/Sidelink-Capabilities,
fr1-Add-UE-NR/MRDC-Capabilities and fr2-Add-UE-NR/MRDC-Capabilities, to
include the values applicable for all duplex mode(s) and frequency
range(s) that the UE supports;

1\> if UE supports both FDD (or SUL/SDL) and TDD and if (some of) the UE
capability fields have a different value for FDD (or SUL/SDL) and TDD:

2\> if for FDD (and, if the UE supports SUL/SDL, for SUL/SDL), the UE
supports additional functionality compared to what is indicated by the
previous fields of UE-NR/MRDC-Capability/SidelinkParameters:

3\> include field fdd-Add-UE-NR/MRDC/Sidelink-Capabilities and set it to
include fields reflecting the additional functionality applicable for
FDD;

2\> if for TDD, the UE supports additional functionality compared to
what is indicated by the previous fields of
UE-NR/MRDC-Capability/SidelinkParameters:

3\> include field tdd-Add-UE-NR/MRDC/Sidelink-Capabilities and set it to
include fields reflecting the additional functionality applicable for
TDD;

1\> if UE supports both FR1 and FR2 and if (some of) the UE capability
fields have a different value for FR1 and FR2:

2\> if for FR1, the UE supports additional functionality compared to
what is indicated by the previous fields of UE-NR/MRDC-Capability:

3\> include field fr1-Add-UE-NR/MRDC-Capabilities and set it to include
fields reflecting the additional functionality applicable for FR1;

2\> if for FR2, the UE supports additional functionality compared to
what is indicated by the previous fields of UE-NR/MRDC-Capability:

3\> include field fr2-Add-UE-NR/MRDC-Capabilities and set it to include
fields reflecting the additional functionality applicable for FR2;

NOTE 1: The fields which indicate \"shall be set to 1\" or \"shall be
set to *supported*\" in the following tables means these features are
purely mandatory and are assumed they are the same as mandatory without
capability signalling.

NOTE 2: For the case where the UE is allowed to support different
functionality between FDD and TDD and between FR1 and FR2 according to
the specification, the UE capability indication is clarified in Annex B.

NOTE 2a: In this release of the specification, if the UE is allowed to
support different functionalities between FDD and TDD, and/or between
FR1 and FR2, these functionalities are signalled per band with the text
\"UE shall set the capability value consistently for all FDD-FR1 bands,
all TDD-FR1 bands, all TDD-FR2-1 bands and all TDD-FR2-2 bands
respectively\".

For optional features, the UE radio access capability parameter
indicates whether the feature has been implemented and successfully
tested. For mandatory features with the UE radio access capability
parameter, the parameter indicates whether the feature has been
successfully tested. In the table of UE capability parameter in
subsequent clauses, \"Yes\" in the column by \"M\" indicates the
associated feature is mandatory and \"No\" indicates the associated
feature is optional. \"CY\" in the column indicates the associated
feature is conditional mandatory and the condition is described in the
field description and the associated feature is considered mandatory
with capability parameter, when the described condition is satisfied.
\"FD\" in the column indicates to refer the associated field
description. Some parameters in subsequent clauses are not related to UE
features and in the case, \"N/A\" is indicated in the column.

UE capability parameters have hierarchical structure. In the table of UE
capability parameter in subsequent clauses, \"Per\" indicates the level
the associated parameter is included. \"UE\" in the column indicates the
associated parameter is signalled per UE, \"Band\" indicates it is
signalled per band, \"BC\" indicates it is signalled per band
combination, \"FS\" indicates it is signalled per feature set (per band
per band combination), \"FSPC\" indicates it is signalled per feature
set per component carrier (per CC per band per band combination), and
\"FD\" in the column indicates to refer the associated field
description.

NOTE 3: Unless otherwise specified, for dependent capabilities with
prerequisite capability in a finer granularity, the UE should indicate
support of the prerequisite capability in at least one finer
granularity. And the dependent capability is supported only in the finer
granularity where the prerequisite capability is supported, e.g. a UE
indicating support of *supportNewDMRS-Port-r16* (dependent capability
which is defined per band) should indicate at least one band combination
where *singleDCI-SDM-scheme-r16* (prerequisite capability which is
defined per feature set) is supported in the corresponding band. In this
case, *supportNewDMRS-Port-r16* is considered supported only in the
corresponding band of the band combination where
*singleDCI-SDM-scheme-r16* is supported.