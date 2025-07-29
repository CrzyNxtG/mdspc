### 16.5.3 eCall over IMS

NG-RAN broadcast an indication to indicate support of eCall over IMS
(*eCallOverIMS-Support*). UEs that are in limited service state need to
consider both *eCallOverIMS-Support* and *ims-EmergencySupport* to
determine if eCall over IMS is possible. UEs that are not in limited
service state need to only consider *eCallOverIMS-Support* to determine
if eCall over IMS is possible. The broadcast indicator is set to
\"support\" if the PLMN in a non-shared environment, or all PLMNs in a
shared environment, supports eCall over IMS.