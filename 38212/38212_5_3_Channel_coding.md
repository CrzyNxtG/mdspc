## 5.3 Channel coding

Usage of coding scheme for the different types of TrCH is shown in table
5.3-1. Usage of coding scheme for the different control information
types is shown in table 5.3-2.

Table 5.3-1: Usage of channel coding scheme for TrCHs

+-------------------------------------------------+--------------------+
| TrCH                                            | Coding scheme      |
+=================================================+====================+
| UL-SCH                                          | LDPC               |
+-------------------------------------------------+                    |
| DL-SCH                                          |                    |
+-------------------------------------------------+                    |
| PCH                                             |                    |
+-------------------------------------------------+--------------------+
| BCH                                             | Polar code         |
+-------------------------------------------------+--------------------+

Table 5.3-2: Usage of channel coding scheme for control information

+-------------------------------------------------+--------------------+
| Control Information                             | Coding scheme      |
+=================================================+====================+
| DCI                                             | Polar code         |
+-------------------------------------------------+--------------------+
| UCI                                             | Block code         |
|                                                 +--------------------+
|                                                 | Polar code         |
+-------------------------------------------------+--------------------+