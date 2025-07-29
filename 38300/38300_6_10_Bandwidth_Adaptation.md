## 6.10 Bandwidth Adaptation

With Bandwidth Adaptation (BA), the receive and transmit bandwidth of a
UE need not be as large as the bandwidth of the cell and can be
adjusted: the width can be ordered to change (e.g. to shrink during
period of low activity to save power); the location can move in the
frequency domain (e.g. to increase scheduling flexibility); and the
subcarrier spacing can be ordered to change (e.g. to allow different
services). A subset of the total cell bandwidth of a cell is referred to
as a Bandwidth Part (BWP) and BA is achieved by configuring the UE with
BWP(s) and telling the UE which of the configured BWPs is currently the
active one.

Figure 6.10-1 below describes a scenario where 3 different BWPs are
configured:

\- BWP~1~ with a width of 40 MHz and subcarrier spacing of 15 kHz;

\- BWP~2~ with a width of 10 MHz and subcarrier spacing of 15 kHz;

\- BWP~3~ with a width of 20 MHz and subcarrier spacing of 60 kHz.

![](media/image32.emf)

Figure 6.10-1: BA Example