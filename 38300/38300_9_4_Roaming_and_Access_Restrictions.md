## 9.4 Roaming and Access Restrictions

The roaming and access restriction information for a UE includes
information on restrictions to be applied for subsequent mobility action
during CM-CONNECTED state. It may be provided by the AMF and also may be
updated by the AMF later.

It includes the forbidden RAT, the forbidden area and the service area
restrictions as specified in TS 23.501 \[3\]. It also includes serving
PLMN/SNPN and may include a list of equivalent PLMNs or a list of
equivalent SNPNs. It may also include PNI-NPN mobility restrictions
(i.e. list of CAGs allowed for the UE and whether the UE can also access
non-CAG cells). The gNB shall consider that roaming or access to CAG
cells is only allowed if PNI-NPN mobility information is available for
the UE.

Upon receiving the roaming and access restriction information for a UE,
if applicable, the gNB should use it to determine whether to apply
restriction handling for subsequent mobility action, e.g., handover,
redirection.

If the roaming and access restriction information is not available for a
UE at the gNB, the gNB shall consider that there is no restriction for
subsequent mobility actions except for the PNI-NPN mobility as described
in TS 23.501 \[3\].

Only if received over NG or Xn signalling, the roaming and access
restriction information shall be propagated over Xn by the source gNB
during Xn handover. If the Xn handover results in a change of serving
PLMN (to an equivalent PLMN), the source gNB shall replace the serving
PLMN with the identity of the target PLMN and move the serving PLMN to
the equivalent PLMN list, before propagating the roaming and access
restriction information. If the Xn handover results in a change of
serving SNPN (to an equivalent SNPN), the source gNB shall replace the
serving SNPN with the identity of the target SNPN and move the serving
SNPN to the equivalent SNPN list, before propagating the roaming and
access restriction information.

If NG-RAN nodes with different versions of the XnAP or NGAP protocol are
deployed, information provided by the 5GC within the NGAP Mobility
Restriction List may be lost in the course of Xn mobility. In order to
avoid such loss of information at Xn handover or UE context retrieval
due to a source NG-RAN node or an old NG-RAN node not able to recognise
the entire content, the source NG-RAN node or the old NG-RAN node may
provide an 5GC Mobility Restriction List Container to the target NG-RAN
node or the new NG-RAN node, containing the Mobility Restriction List as
received from the 5GC. The target NG-RAN node or the new NG-RAN node
shall use the information contained in the 5GC Mobility Restriction List
Container as the Mobility Restriction List, except for the Serving
PLMN/SNPN and the Equivalent PLMNs/SNPNs, which the NG-RAN node shall
use from the XnAP Mobility Restriction List. The 5GC Mobility
Restriction List Container may be propagated at future Xn handover and
UE context retrieval.