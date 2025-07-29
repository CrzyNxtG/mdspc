### 6.3.0 Parameterized types

#### -- *SetupRelease*

*SetupRelease* allows the *ElementTypeParam* to be used as the
referenced data type for the setup and release entries. See A.3.8 for
guidelines.

\-- ASN1START

\-- TAG-SETUPRELEASE-START

SetupRelease { ElementTypeParam } ::= CHOICE {

release NULL,

setup ElementTypeParam

}

\-- TAG-SETUPRELEASE-STOP

\-- ASN1STOP