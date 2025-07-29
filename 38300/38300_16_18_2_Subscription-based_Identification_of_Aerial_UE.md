### 16.18.2 Subscription-based Identification of Aerial UE

Support for Aerial UE functions is stored in the user\'s subscription
information in UDM. UDM transfers this information to the AMF during
Registration, Service Request and Mobility Registration Update
procedures.

The Aerial UE subscription information can be provided by the AMF to the
NG-RAN node via the NGAP INITIAL CONTEXT SETUP REQUEST message during
the Registration, Mobility Registration Update and Service Request
procedures. The subscription information can also be updated via the
NGAP UE Context Modification procedure and NGAP Path Switch Request
procedure. In addition, for Xn-based handover, the source NG-RAN node
can include the Aerial UE subscription information in the XnAP HANDOVER
REQUEST message and RETRIEVE UE CONTEXT RESPONSE message to the target
NG-RAN node.

For intra- and inter-AMF NG-based handover, the AMF provides the Aerial
UE subscription information to the target NG-RAN node after the handover
procedure.