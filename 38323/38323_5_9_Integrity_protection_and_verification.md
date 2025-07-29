## 5.9 Integrity protection and verification

The integrity protection function includes both integrity protection and
integrity verification and is performed in PDCP, if configured. The data
unit that is integrity protected is the PDU header and the data part of
the PDU before ciphering. The integrity protection is always applied to
PDCP Data PDUs of SRBs. The integrity protection is applied to sidelink
SRB1, SRB2 and SRB3. The integrity protection is applied to PDCP Data
PDUs of DRBs (including sidelink DRBs for unicast) for which integrity
protection is configured. The integrity protection is not applicable to
PDCP Control PDUs.

For downlink and uplink, the integrity protection algorithm and key to
be used by the PDCP entity are configured by upper layers TS 38.331
\[3\] and the integrity protection method shall be applied as specified
in TS 33.501 \[6\] for NR and in TS 33.401 \[17\] for E-UTRA/EPC.

The integrity protection function is activated/suspended/resumed by
upper layers TS 38.331 \[3\]. When security is activated and not
suspended, the integrity protection function shall be applied to all
PDUs including and subsequent to the PDU indicated by upper layers TS
38.331 \[3\] for the downlink and the uplink, respectively.

NOTE 1: As the RRC message which activates the integrity protection
function is itself integrity protected with the configuration included
in this RRC message, this message needs first be decoded by RRC before
the integrity protection verification could be performed for the PDU in
which the message was received.

NOTE 2: As the PC5-S message which activates the integrity protection
function is itself integrity protected with the configuration included
in this PC5-S message, this message needs first be decoded by upper
layer before the integrity protection verification could be performed
for the PDU in which the message was received.

For DAPS bearers, the PDCP entity shall perform the integrity protection
or verification for the PDCP SDU using the integrity protection
algorithm and key either configured for the source cell or configured
for the target cell, based on to/from which cell the PDCP SDU is
transmitted/received.

For downlink and uplink integrity protection and verification, the
parameters that are required by PDCP for integrity protection are
defined in TS 33.501 \[6\] or TS 33.401 \[17\] and are input to the
integrity protection algorithm. The required inputs to the integrity
protection function include the COUNT value, and DIRECTION (direction of
the transmission: set as specified in TS 33.501 \[6\]) or TS 33.401
\[17\]. The parameters required by PDCP which are provided by upper
layers TS 38.331 \[3\] are listed below:

\- BEARER (defined as the radio bearer identifier in TS 33.501 \[6\] or
TS 33.401 \[17\]. It will use the value RB identity --1 as in TS 38.331
\[3\]);

\- KEY (the integrity protection keys for the control plane and for the
user plane are K~RRCint~ and K~UPint~, respectively).

For NR sidelink communication, the integrity protection algorithm and
key to be used by the PDCP entity are configured by upper layers TS
24.587 \[16\] and the integrity protection method shall be applied as
specified in TS 33.536 \[14\].

For NR sidelink communication, the integrity protection function is
activated for sidelink SRBs and/or sidelink DRBs for a PC5 unicast link
‎by upper layers, as specified in TS 38.331 \[3\]. When security is
activated for sidelink SRBs, the integrity protection ‎function shall be
applied to all PDUs including and subsequent to the PDU for the ‎sidelink
SRBs which belong to the PC5 unicast link.‎ When security is activated
for sidelink DRBs, the integrity protection ‎function shall be applied to
all PDUs including and subsequent to the PDU for the ‎sidelink DRBs which
belong to the PC5 unicast link.‎

For the SLRB that needs integrity protection and verification, the
parameters that are required by PDCP for integrity protection are
defined in TS 33.536 \[14\] and are input to the integrity protection
algorithm. The required inputs to the integrity protection function
include the KEY (NRPIK), COUNT, BEARER (LSB 5 bits of LCID with values 1
to 19 associated with the PDCP entity, as specified in TS 38.321 \[4\])
and DIRECTION (which value shall be set is specified in TS 33.536
\[14\]). For L2 U2U relay communication between source remote UE and
target remote UE, the BEARER is 1/2/3 for sidelink SRB1/2/3 and the LSB
5 bits of *slrb-PC5-ConfigIndex* associated with the PDCP entity for
sidelink DRB, as specified in TS 38.331 \[3\].

At transmission, the UE computes the value of the MAC-I field and at
reception it verifies the integrity of the PDCP Data PDU by calculating
the X-MAC based on the input parameters as specified above. If the
calculated X-MAC corresponds to the received MAC-I, integrity protection
is verified successfully.

The integrity protection and verification are not applied to MRBs and
sidelink SRB4.