## 5.13 Handling of unknown, unforeseen and erroneous protocol data

When a MAC entity receives a MAC PDU for the MAC entity\'s C-RNTI,
CS-RNTI, G-RNTI, G-CS-RNTI or by the configured downlink assignment,
containing a Reserved LCID or eLCID value, or an LCID or eLCID value the
MAC Entity does not support, the MAC entity shall at least:

1\> discard the received subPDU and any remaining subPDUs in the MAC
PDU.

When a MAC entity receives a MAC PDU for the MAC entity\'s C-RNTI,
CS-RNTI or G-RNTI (for MBS multicast in RRC_INACTIVE), or by the
configured downlink assignment, containing an LCID or eLCID value which
is not configured, or an LCID or eLCID value associated with a suspended
RB as specified in TS 38.331 \[5\], the MAC entity shall at least:

1\> discard the received subPDU.

When a MAC entity receives a MAC PDU on SL-SCH containing a Reserved
LCID value for broadcast or groupcast, or an LCID value which is not
configured, the MAC entity shall:

1\> discard the received subPDU.

When a MAC entity receives a MAC PDU on SL-SCH containing a Reserved
LCID value for unicast, the MAC entity shall:

1\> discard the received subPDU and any remaining subPDUs in the MAC
PDU.