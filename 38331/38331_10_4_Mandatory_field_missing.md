## 10.4 Mandatory field missing

The UE shall:

1\> if the message includes a field that is mandatory to include in the
message (e.g. because conditions for mandatory presence are fulfilled)
and that field is absent or treated as absent:

2\> if the RRC message was not received on DCCH or CCCH; or

2\> if the PC5 RRC message was not received on SCCH:

3\> if the field concerns a (sub-field of) an entry of a list (i.e. a
SEQUENCE OF):

4\> treat the list as if the entry including the missing or not
comprehended field was absent;

3\> else if the field concerns a sub-field of another field, referred to
as the \'parent\' field i.e. the field that is one nesting level up
compared to the erroneous field:

4\> consider the \'parent\' field to be set to a not comprehended value;

4\> apply the generic error handling to the subsequent \'parent\'
field(s), until reaching the top nesting level i.e. the message level;

3\> else (field at message level):

4\> ignore the message.

NOTE 1: The error handling defined in these clauses implies that the UE
ignores a message with the message type or version set to a not
comprehended value.

NOTE 2: The nested error handling for messages received on logical
channels other than DCCH, CCCH and SCCH applies for errors in extensions
also, even for errors that can be regarded as invalid network operation
e.g. the network not observing conditional presence.

NOTE 3: UE behaviour on receipt of an RRC message on DCCH or CCCH or a
PC5 RRC message on SCCH that does not include a field that is mandatory
(e.g. because conditions for mandatory presence are fulfilled) is
unspecified.

The following ASN.1 further clarifies the levels applicable in case of
nested error handling for errors in extension fields.

\-- /example/ ASN1START

\-- Example with extension addition group

ItemInfoList ::= SEQUENCE (SIZE (1..max)) OFItemInfo

ItemInfo ::= SEQUENCE {

itemIdentity INTEGER (1..max),

field1 Field1,

field2 Field2 OPTIONAL, \-- Need N

\...

\[\[

field3-r9 Field3-r9 OPTIONAL, \-- Cond Cond1

field4-r9 Field4-r9 OPTIONAL \-- Need N

\]\]

}

\-- Example with traditional non-critical extension (empty sequence)

BroadcastInfoBlock1 ::= SEQUENCE {

itemIdentity INTEGER (1..max),

field1 Field1,

field2 Field2 OPTIONAL, \-- Need N

nonCriticalExtension BroadcastInfoBlock1-v940-IEs OPTIONAL

}

BroadcastInfoBlock1-v940-IEs::= SEQUENCE {

field3-r9 Field3-r9 OPTIONAL, \-- Cond Cond1

field4-r9 Field4-r9 OPTIONAL, \-- Need N

nonCriticalExtension SEQUENCE {} OPTIONAL \-- Need S

}

\-- ASN1STOP

The UE shall, apply the following principles regarding the levels
applicable in case of nested error handling:

\- an extension addition group is not regarded as a level on its own.
E.g. in the ASN.1 extract in the previous, a error regarding the
conditionality of *field3* would result in the entire itemInfo entry to
be ignored (rather than just the extension addition group containing
*field3* and *field4*);

\- a traditional *nonCriticalExtension* is not regarded as a level on
its own. E.g. in the ASN.1 extract in the previous, an error regarding
the conditionality of *field3* would result in the entire
*BroadcastInfoBlock1* to be ignored (rather than just the non-critical
extension containing *field3* and *field4*).