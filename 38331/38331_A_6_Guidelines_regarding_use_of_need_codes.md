# A.6 Guidelines regarding use of need codes

The following rule provides guidance for determining need codes for
optional downlink fields:

\- if the field needs to be stored by the UE (i.e. maintained) when
absent:

\- use Need M (=Maintain);

\- else, if the field needs to be released by the UE when absent:

\- use Need R (=Release);

\- else, if UE shall take no action when the field is absent (i.e. UE
does not even need to maintain any existing value of the field):

\- use Need N (=None);

\- else (UE behaviour upon absence does not fit any of the above
conditions):

\- use Need S (=Specified);

\- specify the UE behaviour upon absence of the field in the procedural
text or in the field description table.