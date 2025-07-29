### 5.14.6 Pre-defined dictionary

One standard dictionary for SIP and SDP and one operator defined
dictionary can be used as pre-defined dictionaries in UDC. The standard
dictionary for SIP and SDP consists of the first 3468 bytes of the
dictionary for SigComp defined in RFC 3485 \[20\]. When UDC is
configured, at most one dictionary, configured by upper layers, is put
into the tail of the compression buffer. Also, the compression buffer
acts as a FIFO and hence the content of the dictionary is to be totally
pushed out of the compression buffer after the size of transmitted
uncompressed packets compressed by UDC exceeds the compression buffer
size. If the size of dictionary is larger than the compression buffer
size, only the tail of the dictionary is inserted in the compression
buffer.