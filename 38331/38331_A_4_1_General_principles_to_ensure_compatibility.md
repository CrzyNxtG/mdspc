## A.4.1 General principles to ensure compatibility

It is essential that extension of the protocol does not affect
interoperability i.e. it is essential that implementations based on
different versions of the RRC protocol are able to interoperate. In
particular, this requirement applies for the following kind of protocol
extensions:

\- Introduction of new PDU types (i.e. these should not cause unexpected
behaviour or damage).

\- Introduction of additional fields in an extensible PDUs (i.e. it
should be possible to ignore uncomprehended extensions without affecting
the handling of the other parts of the message).

\- Introduction of additional values of an extensible field of PDUs. If
used, the behaviour upon reception of an uncomprehended value should be
defined.

It should be noted that the PDU extension mechanism may depend on the
logical channel used to transfer the message e.g. for some PDUs an
implementation may be aware of the protocol version of the peer in which
case selective ignoring of extensions may not be required.

The non-critical extension mechanism is the primary mechanism for
introducing protocol extensions i.e. the critical extension mechanism is
used merely when there is a need to introduce a \'clean\' message
version. Such a need appears when the last message version includes a
large number of non-critical extensions, which results in issues like
readability, overhead associated with the extension markers. The
critical extension mechanism may also be considered when it is
complicated to accommodate the extensions by means of non-critical
extension mechanisms.