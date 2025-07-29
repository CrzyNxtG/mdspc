## 7.4 Paging in extended DRX

The UE may be configured by upper layers and/or RRC with an extended DRX
(eDRX) cycle T~eDRX,\ CN~ and/or T~eDRX,\ RAN~.

For CN paging, the UE operates in eDRX in RRC_IDLE or RRC_INACTIVE
states if the UE is configured for eDRX by upper layers and
*eDRX-AllowedIdle* is signalled in SIB1; otherwise, the UE does not
operate in eDRX.

For RAN paging, the UE in RRC_INACTIVE state:

\- if the UE is configured for eDRX by
*ran-ExtendedPagingCycleConfig-r18* and *eDRX-AllowedInactive-r18* is
signalled in SIB1:

\- operates in eDRX with an eDRX cycle T~eDRX,\ RAN~ configured by
*extendedPagingCycle-r18*;

\- else if the UE is configured for eDRX by
*ran-ExtendedPagingCycle-r17* and *eDRX-AllowedInactive-r17* is
signalled in SIB1:

\- operates in eDRX with an eDRX cycle T~eDRX,\ RAN~ configured by
*ran-ExtendedPagingCycle-r17*;

\- else:

\- does not operate in eDRX.

If the UE operates in eDRX with an eDRX cycle no longer than 1024 radio
frames, it monitors POs as defined in 7.1 with configured eDRX cycle.
Otherwise, a UE operating in eDRX monitors POs as defined in 7.1 during
a periodic Paging Time Window (PTW) configured for the UE. The PTW is
UE-specific and is determined by a Paging Hyperframe (PH), a starting
position within the PH (PTW_start) and an ending position (PTW_end). PH,
PTW_start and PTW_end are given by the following formula:

The PH for CN is the H-SFN satisfying the following equations:

H-SFN mod T~eDRX,\ CN~= (UE_ID_H mod T~eDRX,\ CN~), where

\- T~eDRX,\ CN~: UE-specific eDRX cycle in Hyper-frames, (T~eDRX,\ CN~ =
2, ..., 1024 Hyper-frames) configured by upper layers.

The PH for RAN is the H-SFN satisfying the following equations:

H-SFN mod T~eDRX_RAN~= (UE_ID_H mod T~eDRX_RAN~), where

\- T~eDRX_RAN~: UE-specific eDRX cycle in Hyper-frames, (T~eDRX_RAN~ =
2, ..., 1024 Hyper-frames) configured by RRC.

For CN configured PTW:

PTW_start denotes the first radio frame of the PH for CN that is part of
the PTW and has SFN satisfying the following equation:

SFN = 128 \* i~eDRX,\ CN~, where

\- i~eDRX,\ CN~ = floor(UE_ID_H /T~eDRX,\ CN~) mod 8

PTW_end is the last radio frame of the PTW and has SFN satisfying the
following equation:

SFN = (PTW_start + L\*100 - 1) mod 1024, where

\- L = Paging Time Window (PTW) length (in seconds) configured by upper
layers

For RAN configured PTW:

PTW_start denotes the first radio frame of the PH for RAN that is part
of the PTW and has SFN satisfying the following equation:

SFN = 128 \* i~eDRX_CN~, where

\- i~eDRX_CN~ = floor(UE_ID_H /T~eDRX_CN~) mod 8

PTW_end is the last radio frame of the PTW and has SFN satisfying the
following equation:

SFN = (PTW_start + L\*100 - 1) mod 1024, where

\- L = Paging Time Window (PTW) length (in seconds) configured by RRC

UE_ID_H is defined as follows:

UE_ID_H: 13 most significant bits of the Hashed ID.

Hashed ID is defined as follows:

Hashed_ID is Frame Check Sequence (FCS) for the bits b31, b30..., b0 of
5G-S-TMSI.

5G-S-TMSI = \<b47, b46, ..., b0\> as defined in TS 23.003 \[23\].

The 32-bit FCS shall be the ones complement of the sum (modulo 2) of Y1
and Y2, where

\- Y1 is the remainder of x^k^ (x^31^ + x^30^ + x^29^ + x^28^ + x^27^ +
x^26^ + x^25^ + x^24^ + x^23^ + x^22^ + x^21^ + x^20^ + x^19^ + x^18^ +
x^17^ + x^16^ + x^15^ + x^14^ + x^13^ + x^12^ + x^11^ + x^10^ + x^9^ +
x^8^ + x^7^ + x^6^ + x^5^ + x^4^ + x^3^ + x^2^ + x^1^ + 1) divided
(modulo 2) by the generator polynomial x^32^ + x^26^ + x^23^ + x^22^ +
x^16^ + x^12^ + x^11^ + x^10^ + x^8^ + x^7^ + x^5^ + x^4^ + x^2^ + x +
1, where k is 32; and

\- Y2 is the remainder of Y3 divided (modulo 2) by the generator
polynomial x^32^ + x^26^ + x^23^ + x^22^ + x^16^ + x^12^ + x^11^ +
x^10^ + x^8^ + x^7^ + x^5^ + x^4^ + x^2^ + x + 1, where Y3 is the
product of x^32^ by \"b31, b30..., b0 of S-TMSI or 5G-S-TMSI\", i.e., Y3
is the generator polynomial x^32^ (b31\*x^31^ + b30\*x^30^ + ... +
b0\*1).

NOTE: The Y1 is 0xC704DD7B for any 5G-S-TMSI value. An example of hashed
ID calculation is in Annex A.