## 16.4 Public Warning System

NR connected to 5GC provides support for public warning systems (PWS)
through means of system information broadcast capability. NR is
responsible for scheduling and broadcasting of the warning messages as
well as for paging the UE to provide indication that the warning message
is being broadcast:

\- Earthquake and Tsunami Warning System: ETWS is a public warning
system developed to meet the regulatory requirements for warning
notifications related to earthquake and/or tsunami events (see TS 22.168
\[14\]). ETWS warning notifications can either be a primary notification
(short notification) or secondary notification (providing detailed
information).

\- Commercial Mobile Alert System: CMAS is a public warning system
developed for the delivery of multiple, concurrent warning notifications
(see TS 22.268 \[15\]).

Different SIBs are defined for ETWS primary notification, ETWS secondary
notification and CMAS notification. Paging is used to inform UEs about
ETWS indication and CMAS indication (see clause 9.2.5). UE monitors
ETWS/CMAS indication in its own paging occasion for RRC_IDLE and for
RRC_INACTIVE while no SDT procedure (see clause 18.0) is ongoing. UE
monitors ETWS/CMAS indication in any paging occasion for RRC Connected
and during the SDT procedure in RRC_INACTIVE. Paging indicating
ETWS/CMAS notification triggers acquisition of system information
(without delaying until the next modification period).

Enhancements of public warning system (ePWS) enable broadcast of
language-independent content and notifications to UEs with no user
interface or with a user interface that is incapable of displaying text,
see clause 9 in TS 22.268 \[15\] and TS 23.041 \[54\]. ETWS/CMAS
notifications with ePWS functionality use the same AS mechanisms as
ETWS/CMAS.

KPAS and EU-Alert are public warning systems developed for the delivery
of multiple, concurrent warning notifications (see TS 22.268 \[15\]).
KPAS and EU-Alert uses the same AS mechanisms as CMAS. Therefore, the NR
procedures defined for CMAS equally apply for KPAS and EU-Alert.