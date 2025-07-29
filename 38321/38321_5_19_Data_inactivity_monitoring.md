## 5.19 Data inactivity monitoring

The UE may be configured by RRC with a Data inactivity monitoring
functionality, when in RRC_CONNECTED. RRC controls Data inactivity
operation by configuring the timer *dataInactivityTimer*.

When *dataInactivityTimer* is configured, the UE shall:

1\> if any MAC entity receives a MAC SDU for DTCH logical channel, DCCH
logical channel, or CCCH logical channel, or multicast MTCH logical
channel; or

1\> if any MAC entity transmits a MAC SDU for DTCH logical channel, or
DCCH logical channel:

2\> start or restart *dataInactivityTimer*.

1\> if the *dataInactivityTimer* expires:

2\> indicate the expiry of the *dataInactivityTimer* to upper layers.