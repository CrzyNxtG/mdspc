### 5.14.1 UDC protocol

The UDC protocol is based on IETF RFC 1951 (DEFLATE Compressed Data
Format Specification) \[19\].

Static Huffman coding tree defined in \[19\] is used as the DEFLATE
compression strategy.

UDC Data Block should be byte-alignment. Z_SYNC_FLUSH is used as the
DEFLATE byte-alignment with corresponding reference \[21\], wherein the
fixed last four bytes, 0x00 0x00 0xFF 0xFF, are removed before
transmission.