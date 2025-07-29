## 9.2 Default radio configurations

The following clauses only list default values for REL-15 parameters
included in protocol version v15.3.0. For all fields introduced in a
later protocol version, the default value is \"released\" or \"false\"
unless explicitly specified otherwise. If the UE is to apply default
configuration while it is configured with some critically extended
fields, the UE shall apply the original version of those fields with
only default values.

NOTE 1: In general, the signalling should preferably support a
\"release\" option for fields introduced after v15.3.0. The \"value not
applicable\" should be used restrictively, mainly limited to for fields
which value is relevant only if another field is set to a value other
than its default.

NOTE 2: For parameters in *ServingCellConfig*, the default values are
specified in the corresponding specification.