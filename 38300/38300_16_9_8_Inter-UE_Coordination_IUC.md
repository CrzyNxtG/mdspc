### 16.9.8 Inter-UE Coordination (IUC)

The SL UE can support inter-UE coordination (IUC) in Mode 2, whereby a
UE sends information about resources to a peer UE, which the peer UE
then uses for resource (re)selection. The following schemes of inter-UE
coordination are supported:

\- IUC scheme 1, where the IUC information sent from a UE to a peer UE
is the preferred or non-preferred resources for the peer UE\'s
transmission, and

\- IUC scheme 2, where the IUC information sent from a UE to a peer UE
is the presence of expected/potential resource conflict on the resources
indicated by the peer UE\'s SCI.

In scheme 1, the transmission of IUC information from a UE can be
triggered by a condition at this UE, or by an explicit request from a
peer UE. The UE determines the set of resources reserved by other UEs or
slots where the UE, when it is the intended receiver of the peer UE,
does not expect to perform SL reception from the peer UE due to
half-duplex operation. The UE uses these resources as the set of
non-preferred resources, or excludes these resources to determine a set
of preferred resources and sends the preferred/non-preferred resources
to the peer UE. Regarding the IUC information received from the UE, the
peer UE\'s resources for resource (re)selection can be based on both the
peer UE\'s sensing results (if available) and the IUC information, or it
can be based only on the IUC information. For scheme 1, MAC CE and
second-stage SCI or MAC CE only can be used to send IUC information. For
IUC information transmission triggered by an explicit request, both the
explicit request and the IUC information are transmitted in unicast
manner. For IUC information transmission triggered by a condition other
than the explicit request, the IUC information indicating preferred
resource set is transmitted in unicast manner, and the IUC information
indicating non-preferred resource set is transmitted in unicast,
groupcast or broadcast manner.

In scheme 2, a UE determines the expected/potential resource conflict
within the resources indicated by a peer UE\'s SCI as either resources
reserved by other UEs and identified by the UE as fully/partially
overlapping with the resources indicated by the peer UE\'s SCI, or as
slots where the UE is the intended receiver of the peer UE and does not
expect to perform SL reception on those slots due to half-duplex
operation. The peer UE uses the conflicting resources to determine the
resources to be reselected and exclude the conflicting resources from
the reselected resources. For scheme 2, PSFCH is used to send IUC
information.