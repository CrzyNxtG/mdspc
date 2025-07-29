### 16.14.6 AMF (Re-)Selection

The gNB implements the NAS Node Selection Function specified in TS
38.410 \[16\].

For an RRC_CONNECTED UE, when the gNB is configured to ensure that the
UE connects to an AMF that serves the country in which the UE is
located, if the gNB detects that the UE is in a different country to
that served by the serving AMF, then it should perform an NG handover to
change to an appropriate AMF, or initiate an UE Context Release Request
procedure towards the serving AMF (in which case the AMF may decide to
de-register the UE).

For the purpose of selecting an appropriate AMF, the 5GC may verify the
UE location according to TS 23.501 \[3\] and TS 38.305 \[42\] after the
UE has attached to the network.

NOTE: UE location verification for AMF selection should not be necessary
if NTN cell(s) do not extend across countries.