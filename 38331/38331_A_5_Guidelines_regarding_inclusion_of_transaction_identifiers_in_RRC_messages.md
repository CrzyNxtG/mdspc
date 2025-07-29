# A.5 Guidelines regarding inclusion of transaction identifiers in RRC messages

The following rules provide guidance on which messages should include a
Transaction identifier

1: DL messages on CCCH that move UE to RRC-Idle should not include the
RRC transaction identifier.

2: All network initiated DL messages by default should include the RRC
transaction identifier.

3: All UL messages that are direct response to a DL message with an RRC
Transaction identifier should include the RRC Transaction identifier.

4: All UL messages that require a direct DL response message should
include an RRC transaction identifier.

5: All UL messages that are not in response to a DL message nor require
a corresponding response from the network should not include the RRC
Transaction identifier.