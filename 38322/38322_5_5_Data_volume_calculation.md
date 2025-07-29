## 5.5 Data volume calculation

For the purpose of MAC buffer status reporting, the UE shall consider
the following as RLC data volume:

\- RLC SDUs and RLC SDU segments that have not yet been included in an
RLC data PDU;

\- RLC data PDUs that are pending for initial transmission;

\- RLC data PDUs that are pending for retransmission (RLC AM).

For the purpose of MAC delay status reporting, the UE shall consider the
following as delay-critical RLC data volume:

\- delay-critical RLC SDUs and delay-critical RLC SDU segments that have
not yet been included in an RLC data PDU;

\- RLC data PDUs pending for initial transmission, and containing a
delay-critical RLC SDU or a delay-critical RLC SDU segment;

\- RLC data PDUs that are pending for retransmission (RLC AM).

In addition, if a STATUS PDU has been triggered and *t-StatusProhibit*
is not running or has expired, the UE shall estimate the size of the
STATUS PDU that will be transmitted in the next transmission
opportunity, and consider this as part of RLC data volume for MAC buffer
status reporting and as part of delay-critical RLC data volume for MAC
delay status reporting.