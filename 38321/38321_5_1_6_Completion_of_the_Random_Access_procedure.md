### 5.1.6 Completion of the Random Access procedure

Upon completion of the Random Access procedure, the MAC entity shall:

1\> discard any explicitly signalled contention-free Random Access
Resources for 2-step RA type and 4-step RA type except the 4-step RA
type contention-free Random Access Resources for beam failure recovery
request, if any;

1\> flush the HARQ buffer used for transmission of the MAC PDU in the
Msg3 buffer and the MSGA buffer.

Upon successful completion of the Random Access procedure initiated for
DAPS handover, the target MAC entity shall:

1\> indicate the successful completion of the Random Access procedure to
the upper layers.

Upon successful completion of the Random Access procedure initiated for
LTM cell switch, the MAC entity shall:

1\> indicate the successful completion of the LTM cell switch to upper
layers.