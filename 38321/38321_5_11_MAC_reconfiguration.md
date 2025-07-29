## 5.11 MAC reconfiguration

When a reconfiguration of the MAC entity is requested by upper layers,
the MAC entity shall:

1\> initialize the corresponding HARQ entity upon addition of an SCell;

1\> remove the corresponding HARQ entity upon removal of an SCell;

1\> apply the new value for timers when the timer is (re)started;

1\> apply the new maximum parameter value when counters are initialized;

1\> apply immediately the configurations received from upper layers for
other parameters.