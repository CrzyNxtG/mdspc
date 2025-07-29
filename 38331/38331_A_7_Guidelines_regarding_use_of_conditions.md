# A.7 Guidelines regarding use of conditions

Conditions are primarily used to specify network restrictions, for which
the following types can be distinguished:

\- Message Contents related constraints e.g. that a field B is mandatory
present if the same message includes field A and when it is set value X.

\- Configuration Constraints e.g. that a field D can only be signalled
if field C is configured and set to value Y. (i.e. regardless of whether
field C is present in the same message or previously configured).

The use of these conditions is illustrated by an example.

\-- /example/ ASN1START

RRCMessage-IEs ::= SEQUENCE {

fieldA FieldA OPTIONAL, \-- Need M

fieldB FieldB OPTIONAL, \-- Cond FieldAsetToX

fieldC FieldC OPTIONAL, \-- Need M

fieldD FieldD OPTIONAL, \-- Cond FieldCsetToY

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- /example/ ASN1STOP

  -----------------------------------------------------------------------
  Conditional      Explanation
  presence         
  ---------------- ------------------------------------------------------
  *FieldAsetToX*   The field is mandatory present if fieldA is included
                   and set to valueX. Otherwise the field is optionally
                   present, need R.

  *FieldCsetToY*   The field is optionally present, need M, if fieldC is
                   configured and set to valueY. Otherwise the field is
                   absent and the UE does not maintain the value
  -----------------------------------------------------------------------