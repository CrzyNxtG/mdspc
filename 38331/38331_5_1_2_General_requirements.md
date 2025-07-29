### 5.1.2 General requirements

The UE shall:

1\> process the received messages in order of reception by RRC, i.e. the
processing of a message shall be completed before starting the
processing of a subsequent message;

NOTE: Network may initiate a subsequent procedure prior to receiving the
UE\'s response of a previously initiated procedure.

1\> within a clause execute the steps according to the order specified
in the procedural description;

1\> consider the term \'radio bearer\' (RB) to cover SRBs, DRBs and MRBs
unless explicitly stated otherwise;

1\> set the *rrc-TransactionIdentifier* in the response message, if
included, to the same value as included in the message received from the
network that triggered the response message;

1\> upon receiving a choice value set to *setup*:

2\> apply the corresponding received configuration and start using the
associated resources, unless explicitly specified otherwise;

1\> upon receiving a choice value set to *release*:

2\> clear the corresponding configuration and stop using the associated
resources;

1\> in case the size of a list is extended, upon receiving an extension
field comprising the entries in addition to the ones carried by the
original field (regardless of whether the network signals more entries
in total); apply the following generic behaviour unless explicitly
stated otherwise:

2\> create a combined list by concatenating the additional entries
included in the extension field to the original field while maintaining
the order among both the original and the additional entries;

2\> for the combined list, created according to the previous, apply the
same behaviour as defined for the original field.