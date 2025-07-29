### 6.1.2 Need codes and conditions for optional fields

The need for fields to be present in a message or an abstract type,
i.e., the ASN.1 fields that are specified as OPTIONAL in the abstract
notation (ASN.1), is specified by means of comment text tags attached to
the OPTIONAL statement in the abstract syntax. All comment text tags are
available for use in the downlink direction for RRC message and in the
sidelink for PC5 RRC message. The meaning of each tag is specified in
table 6.1.2-1.

If conditions are used, a conditional presence table is provided for the
message or information element specifying the need of the field for each
condition case. The table also specifies whether UE maintains or
releases the value in case the field is absent. The conditions clarify
what the UE may expect regarding the setting of the message by the
network for the RRC message or by the peer UE in the sidelink RRC
message. Violation of conditions is regarded as invalid network
behaviour when transmitting downlink RRC message or invalid UE behavior
when transmitting PC5 RRC message, which the UE is not required to cope
with. Hence the general error handling defined in 10.4 does not apply in
case a field is absent although it is mandatory according to the CondC
or CondM condition.

For guidelines on the use of need codes and conditions, see Annex A.6
and A.7.

Table 6.1.2-1: Meaning of abbreviations used to specify the need for
fields to be present

+--------------+----------------------------------------------------------+
| Abbreviation | Meaning                                                  |
+==============+==========================================================+
| Cond         | Conditionally present                                    |
| conditionTag |                                                          |
|              | Presence of the field is specified in a tabular form     |
|              | following the ASN.1 segment.                             |
+--------------+----------------------------------------------------------+
| CondC        | Configuration condition                                  |
| conditionTag |                                                          |
|              | Presence of the field is conditional to other            |
|              | configuration settings.                                  |
+--------------+----------------------------------------------------------+
| CondM        | Message condition                                        |
| conditionTag |                                                          |
|              | Presence of the field is conditional to other fields     |
|              | included in the message.                                 |
+--------------+----------------------------------------------------------+
| Need S       | *Specified*                                              |
|              |                                                          |
|              | Used for (configuration) fields, whose field description |
|              | or procedure **specifies** the UE behavior performed     |
|              | upon receiving a message with the field absent (and not  |
|              | if field description or procedure specifies the UE       |
|              | behavior when field is not configured).                  |
+--------------+----------------------------------------------------------+
| Need M       | *Maintain*                                               |
|              |                                                          |
|              | Used for (configuration) fields that are stored by the   |
|              | UE i.e. not one-shot. Upon receiving a message with the  |
|              | field absent, the UE maintains the current value.        |
+--------------+----------------------------------------------------------+
| Need N       | *No action* (one-shot configuration that is not          |
|              | maintained)                                              |
|              |                                                          |
|              | Used for (configuration) fields that are not stored and  |
|              | whose presence causes a one-time action by the UE. Upon  |
|              | receiving message with the field absent, the UE takes no |
|              | action.                                                  |
+--------------+----------------------------------------------------------+
| Need R       | *Release*                                                |
|              |                                                          |
|              | Used for (configuration) fields that are stored by the   |
|              | UE i.e. not one-shot. Upon receiving a message with the  |
|              | field absent, the UE releases the current value.         |
+--------------+----------------------------------------------------------+

NOTE: In this version of the specification, the condition tags CondC and
CondM are not used.

Any field with Need M or Need N in system information shall be
interpreted as Need R.

The need code used within a CondX definition only applies for the case
(part of the condition) where it is defined: A condition may have
different need codes for different parts of the condition. In
particular, the CondX definition may contain the following \"otherwise
the field is absent\" parts:

\- \"Otherwise, the field is absent\": The field is not relevant or
should not be configured when this part of the condition applies. In
particular, the UE behaviour is not defined when the field is configured
via another part of the condition and is reconfigured to this part of
the condition. A need code is not provided when the transition from
another part of the condition to this part of the condition is not
supported, when the field clearly is a one-shot or there is no
difference whether UE maintains or releases the value (e.g., in case the
field is mandatory present according to the other part of the
condition).

\- \"Otherwise, the field is absent, Need R\": The field is released if
absent when this part of the condition applies. This handles UE
behaviour in case the field is configured via another part of the
condition and this part of the condition applies (which means that
network when transmitting downlink RRC message or peer UE transmitting
PC5 RRC message can assume UE releases the field if this part of the
condition is valid).

\- \"Otherwise, the field is absent, Need M\": The UE retains the field
if it was already configured when this part of the condition applies.
This means the network when transmitting downlink RRC message or the
peer UE when transmitting PC5 RRC message cannot release the field, but
UE retains the previously configured value.

Use of different Need codes in different parts of a condition should be
avoided.

For downlink RRC message and sidelink PC5 RRC messages, the need codes,
conditions and ASN.1 defaults specified for a particular (child) field
only apply in case the (parent) field including the particular field is
present. Thus, if the parent is absent the UE shall not release the
field unless the absence of the parent field implies that.

For (parent) fields without need codes in downlink RRC messages or
sidelink PC5 RRC message, if the parent field is absent, UE shall follow
the need codes of the child fields. Thus, if parent field is absent, the
need code of each child field is followed (i.e. Need R child fields are
released, Need M child fields are not modified and the actions for Need
S child fields depend on the specified conditions of each field).
Examples of (parent) fields in downlink RRC messages and sidelink PC5
RRC message without need codes where this rule applies are:

\- *nonCriticalExtension* fields at the end of a message using empty
SEQUENCE extension mechanism,

\- groups of non-critical extensions using double brackets (referred to
as extension groups), and

\- non-critical extensions at the end of a message or at the end of a
structure, contained in a BIT STRING or OCTET STRING (referred to as
parent extension fields).

The handling of need codes as specified in the previous is illustrated
by means of an example, as shown in the following ASN.1.

\-- /example/ ASN1START

RRCMessage-IEs ::= SEQUENCE {

field1 InformationElement1 OPTIONAL, \-- Need M

field2 InformationElement2 OPTIONAL, \-- Need R

nonCriticalExtension RRCMessage-v1570-IEs OPTIONAL

}

RRCMessage-1570-IEs ::= SEQUENCE {

field3 InformationElement3 OPTIONAL, \-- Need M

nonCriticalExtension RRCMessage-v1640-IEs OPTIONAL

}

RRCMessage-v1640-IEs ::= SEQUENCE {

field4 InformationElement4 OPTIONAL, \-- Need R

nonCriticalExtension SEQUENCE {} OPTIONAL

}

InformationElement1 ::= SEQUENCE {

field10 InformationElement10 OPTIONAL, \-- Need N

field11 InformationElement11 OPTIONAL, \-- Need M

field12 InformationElement12 OPTIONAL, \-- Need R

\...,

\[\[

field13 InformationElement13 OPTIONAL, \-- Need R

field14 InformationElement14 OPTIONAL \-- Need M

\]\]

}

InformationElement2 ::= SEQUENCE {

field21 InformationElement11 OPTIONAL, \-- Need M

\...

}

\-- ASN1STOP

The handling of need codes as specified in the previous implies that:

\- if *field1* in *RRCMessage-IEs* is absent, UE does not modify or take
action on any child fields configured within *field1* (regardless of
their need codes);

\- if *field2* in *RRCMessage-IEs* is absent, UE releases the *field2*
(and also its child field *field21*);

\- if *field1* or *field2* in *RRCMessage-IEs* is present, UE retains or
releases their child fields according to the child field presence
conditions;

\- if *field1* in *RRCMessage-IEs* is present but the extension group
containing *field13* and *field14* is absent, the UE releases *field13*
but does not modify *field14*;

\- if *nonCriticalExtension* defined by IE *RRCMessage-v1570-IEs* is
absent, the UE does not modify *field3* but releases *field4*;