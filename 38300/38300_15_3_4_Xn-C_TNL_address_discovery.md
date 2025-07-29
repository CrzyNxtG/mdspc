### 15.3.4 Xn-C TNL address discovery

If the NG-RAN node is aware of the RAN node ID of the candidate NG-RAN
node (e.g. via the ANR function) but not of a TNL address suitable for
SCTP connectivity, then the NG-RAN node can utilize the 5GC (an AMF it
is connected to) to determine the TNL address as follows:

\- The NG-RAN node sends the UPLINK RAN CONFIGURATION TRANSFER message
to the AMF to request the TNL address of the candidate NG-RAN node, and
includes relevant information such as the source and target RAN node ID;

\- The AMF relays the request by sending the DOWNLINK RAN CONFIGURATION
TRANSFER message to the candidate NG-RAN node identified by the target
RAN node ID;

\- The candidate NG-RAN node responds by sending the UPLINK RAN
CONFIGURATION TRANSFER message containing one or more TNL addresses to
be used for SCTP connectivity with the initiating NG-RAN node, and
includes other relevant information such as the source and target RAN
node ID;

\- The AMF relays the response by sending the DOWNLINK CONFIGURATION
TRANSFER message to the initiating NG-RAN node identified by the target
RAN node ID.

NOTE: Void.

The NG-RAN node may determine the gNB ID length of the candidate gNB
based on, e.g. OAM configuration or UE reporting in ANR function. If the
NG-RAN node is not able to make this determination, it may include the
NR cell identifier in the UPLINK RAN CONFIGURATION TRANSFER message to
the AMF. The AMF may, if supported, determine the target gNB ID by
matching the NR cell identifier with a gNB ID of a gNB it connects to.