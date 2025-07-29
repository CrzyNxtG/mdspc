## 13.1 Overview and Principles

The following principles apply to NR connected to 5GC security, see TS
33.501 \[5\]:

\- For user data (DRBs), ciphering provides user data confidentiality
and integrity protection provides user data integrity;

\- For RRC signalling (SRBs), ciphering provides signalling data
confidentiality and integrity protection signalling data integrity;

NOTE: Ciphering and integrity protections are optionally configured
except for RRC signalling for which integrity protection is always
configured. Ciphering and integrity protection can be configured per DRB
but all DRBs belonging to a PDU session for which the User Plane
Security Enforcement information indicates that UP integrity protection
is required (see TS 23.502 \[22\]), are configured with integrity
protection.

\- For key management and data handling, any entity processing cleartext
shall be protected from physical attacks and located in a secure
environment;

\- The gNB (AS) keys are cryptographically separated from the 5GC (NAS)
keys;

\- Separate AS and NAS level Security Mode Command (SMC) procedures are
used;

\- A sequence number (COUNT) is used as input to the ciphering and
integrity protection and a given sequence number must only be used once
for a given key (except for identical re-transmission) on the same radio
bearer in the same direction.

The keys are organised and derived as follows:

\- Key for AMF:

\- K~AMF~ is a key derived by ME and SEAF from K~SEAF~.

\- Keys for NAS signalling:

\- K~NASint~ is a key derived by ME and AMF from K~AMF~, which shall
only be used for the protection of NAS signalling with a particular
integrity algorithm;

\- K~NASenc~ is a key derived by ME and AMF from K~AMF~, which shall
only be used for the protection of NAS signalling with a particular
encryption algorithm.

Key for gNB:

\- K~gNB~ is a key derived by ME and AMF from K~AMF~. K~gNB~ is further
derived by ME and source gNB when performing horizontal or vertical key
derivation.

Keys for UP traffic:

\- K~UPenc~ is a key derived by ME and gNB from K~gNB~, which shall only
be used for the protection of UP traffic between ME and gNB with a
particular encryption algorithm;

\- K~UPint~ is a key derived by ME and gNB from K~gNB~, which shall only
be used for the protection of UP traffic between ME and gNB with a
particular integrity algorithm.

Keys for RRC signalling:

\- K~RRCint~ is a key derived by ME and gNB from K~gNB~, which shall
only be used for the protection of RRC signalling with a particular
integrity algorithm;

\- K~RRCenc~ is a key derived by ME and gNB from K~gNB~, which shall
only be used for the protection of RRC signalling with a particular
encryption algorithm.

Intermediate keys:

\- NH is a key derived by ME and AMF to provide forward security.

\- K~gNB~\* is a key derived by ME and gNB when performing a horizontal
or vertical key derivation.

The primary authentication enables mutual authentication between the UE
and the network and provide an anchor key called K~SEAF~. From K~SEAF~,
K~AMF~ is created during e.g. primary authentication or NAS key
re-keying and key refresh events. Based on K~AMF~, K~NASint~ and
K~NASenc~ are then derived when running a successful NAS SMC procedure.

Whenever an initial AS security context needs to be established between
UE and gNB, AMF and the UE derive a K~gNB~ and a Next Hop parameter
(NH). The K~gNB~ and the NH are derived from the K~AMF~. A NH Chaining
Counter (NCC) is associated with each K~gNB~ and NH parameter. Every
K~gNB~ is associated with the NCC corresponding to the NH value from
which it was derived. At initial setup, the K~gNB~ is derived directly
from K~AMF~, and is then considered to be associated with a virtual NH
parameter with NCC value equal to zero. At initial setup, the derived NH
value is associated with the NCC value one. On handovers, the basis for
the K~gNB~ that will be used between the UE and the target gNB, called
K~gNB~\*, is derived from either the currently active K~gNB~ or from the
NH parameter. If K~gNB~\* is derived from the currently active K~gNB~,
this is referred to as a horizontal key derivation and is indicated to
UE with an NCC that does not increase. If the K~gNB~\* is derived from
the NH parameter, the derivation is referred to as a vertical key
derivation and is indicated to UE with an NCC increase. Finally,
K~RRCint~, K~RRCenc~, K~UPint~ and K~UPenc~ are derived based on K~gNB~
after a new K~gNB~ is derived. This is depicted on Figure 13.1-1 below:

![](media/image61.emf)

Figure 13.1-1: 5G Key Derivation

With such key derivation, a gNB with knowledge of a K~gNB~, shared with
a UE, is unable to compute any previous K~gNB~ that has been used
between the same UE and a previous gNB, therefore providing backward
security. Similarly, a gNB with knowledge of a K~gNB~, shared with a UE,
is unable to predict any future K~gNB~ that will be used between the
same UE and another gNB after n or more handovers (since NH parameters
are only computable by the UE and the AMF).

The AS SMC procedure is for RRC and UP security algorithms negotiation
and RRC security activation. When AS security context is to be
established in the gNB, the AMF sends the complete UE 5G security
capabilities to the gNB (i.e., all bits for every capability defined in
TS 24.501 \[28\] and received in NAS signalling). At handover (or at UE
Context retrieval), the complete UE 5G security capabilities are also
sent by the source gNB to the target gNB (or by the last serving gNB to
the receiving gNB respectively). The gNB chooses the ciphering algorithm
which has the highest priority from its configured list and is also
present in the UE 5G security capabilities. The gNB also chooses the
integrity algorithm which has the highest priority from its configured
list and is also present in the UE 5G security capabilities. The chosen
algorithms are indicated to the UE in the AS SMC and this message is
integrity protected. RRC downlink ciphering (encryption) at the gNB
starts after sending the AS SMC message. RRC uplink deciphering
(decryption) at the gNB starts after receiving and successful
verification of the integrity protected AS security mode complete
message from the UE. The UE verifies the validity of the AS SMC message
from the gNB by verifying the integrity of the received message. RRC
uplink ciphering (encryption) at the UE starts after sending the AS
security mode complete message. RRC downlink deciphering (decryption) at
the UE shall start after receiving and successful verification of the AS
SMC message. The RRC Connection Reconfiguration procedure used to add
DRBs shall be performed only after RRC security has been activated as
part of the AS SMC procedure.

A UE connected to 5GC, shall support integrity protected DRBs at any
data rate, up to and including the highest data rate supported by the UE
for both UL and DL. In case of failed integrity check (i.e. faulty or
missing MAC-I), the concerned PDU shall be discarded by the receiving
PDCP entity.

Key refresh is possible for K~gNB~, K~RRC-enc~, K~RRC-int~, K~UP-enc~,
and K~UP-int~ and can be initiated by the gNB when a PDCP COUNTs are
about to be re-used with the same Radio Bearer identity and with the
same K~gNB~. Key re-keying is also possible for the K~gNB~, K~RRC-enc~,
K~RRC-int~, K~UP-enc~, and K~UP-int~ and can be initiated by the AMF
when a 5G AS security context different from the currently active one
shall be activated.