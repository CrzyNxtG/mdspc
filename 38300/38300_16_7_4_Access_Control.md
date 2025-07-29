### 16.7.4 Access Control

During the establishment of the UE-associated logical NG-connection
towards the 5GC, the AMF checks whether the UE is allowed to access the
cell as specified in TS 23.501 \[3\].

If the check is successful, the AMF sets up the UE-associated logical
NG-connection and provides the NG-RAN node with the list of CAGs allowed
for the UE and, whether the UE is allowed to access non-CAG cells. This
information is used by the NG-RAN for access control of subsequent
mobility.

If the check is not successful, the AMF shall reject setting up the
UE-associated NG connection and inform the NG-RAN node with an
appropriate cause value as specified in TS 23.501 \[3\].