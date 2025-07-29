## 10.2 ASN.1 violation or encoding error

The UE shall:

1\> when receiving an RRC message on the BCCH, CCCH, PCCH, MCCH,
multicast MCCH or a PC5 RRC message on SBCCH for which the abstract
syntax is invalid \[6\]:

2\> ignore the message.

NOTE: This clause applies in case one or more fields is set to a value,
other than a spare, reserved or extended value, not defined in this
version of the transfer syntax. E.g. in the case the UE receives value
12 for a field defined as INTEGER (1..11). In cases like this, it may
not be possible to reliably detect which field is in the error hence the
error handling is at the message level.