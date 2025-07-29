## 10.3 Field set to a not comprehended value

The UE shall, when receiving an RRC message or PC5 RRC message on any
logical channel:

1\> if the message includes a field that has a value that the UE does
not comprehend:

2\> if a default value is defined for this field:

3\> treat the message while using the default value defined for this
field;

2\> else if the concerned field is optional:

3\> treat the message as if the field were absent and in accordance with
the need code for absence of the concerned field;

2\> else:

3\> treat the message as if the field were absent and in accordance with
clause 10.4.