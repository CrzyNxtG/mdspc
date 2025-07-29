## 7.10 Segmentation of RRC messages

An RRC message may be segmented in case the size of the encoded RRC
message PDU exceeds the maximum PDCP SDU size. Segmentation is performed
in the RRC layer using a separate RRC PDU to carry each segment. The
receiver reassembles the segments to form the complete RRC message. All
segments of an RRC message are transmitted before sending another RRC
message. Segmentation is supported in both uplink and downlink as
specified in TS 38.331 \[12\].