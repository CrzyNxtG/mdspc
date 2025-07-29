### 16.15.3 Power Saving

Most XR video frame rates (15, 30, 45, 60, 72, 90 and 120 fps)
correspond to periodicities that are not an integer (66.66, 33.33,
22.22, 16.66, 13.88, 11.11 and 8.33 ms respectively). The gNB may
configure a DRX cycle expressed in rational numbers so that the DRX
cycle matches those periodicities, e.g. for the traffic with a frame
rate of 60 fps, the network may configure the UE with a DRX cycle of
50/3 ms.

Configured grants may be configured without the need for the UE to wake
up to monitor possible grants for UL retransmissions of configured
grants, thus increasing the number of power saving opportunities for the
UE.