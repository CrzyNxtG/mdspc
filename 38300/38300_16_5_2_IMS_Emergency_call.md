### 16.5.2 IMS Emergency call

An IMS Emergency call support indication is provided to inform the UE
that emergency bearer services are supported. In normal service state
the UE is informed if the PLMN supports emergency services through an
Emergency Service Support indicator in the Attach and TAU procedures
(see TS 23.501 \[3\]). In limited service state and for emergency
services other than eCall over IMS, a UE is informed about if a cell
supports emergency services over NG-RAN from a broadcast indication
(*ims-EmergencySupport*). The broadcast indicator is set to \"support\"
if any AMF in a non-shared environment or at least one of the PLMN\'s in
a shared environment supports IMS emergency bearer services.