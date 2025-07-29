### 5.7.1 Supported header compression protocols and profiles

The ROHC protocol is based on the Robust Header Compression (ROHC)
framework defined in RFC 5795 \[7\]. There are multiple ROHC algorithms,
called profiles, defined for the ROHC framework. Each profile is
specific to the particular network layer, transport layer or upper layer
protocol combination e.g. TCP/IP and RTP/UDP/IP.

The detailed definition of the ROHC channel is specified as part of the
ROHC framework defined in RFC 5795 \[7\]. This includes how to multiplex
different flows (header compressed or not) over the ROHC channel, as
well as how to associate a specific IP flow with a specific context
state during initialization of the compression algorithm for that flow.

The implementation of the functionality of the ROHC framework and of the
functionality of the supported header compression profiles is not
covered in this specification.

In this version of the specification the support of the following
profiles is described:

Table 5.7.1-1: Supported ROHC protocols and profiles

  ------------------------------------------------------------------------
    Profile Identifier   Usage                 Reference
  ---------------------- --------------------- ---------------------------
          0x0000         No compression        RFC 5795

          0x0001         RTP/UDP/IP            RFC 3095, RFC 4815

          0x0002         UDP/IP                RFC 3095, RFC 4815

          0x0003         ESP/IP                RFC 3095, RFC 4815

          0x0004         IP                    RFC 3843, RFC 4815

          0x0006         TCP/IP                RFC 6846

          0x0101         RTP/UDP/IP            RFC 5225

          0x0102         UDP/IP                RFC 5225

          0x0103         ESP/IP                RFC 5225

          0x0104         IP                    RFC 5225
  ------------------------------------------------------------------------