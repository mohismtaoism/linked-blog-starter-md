# pneumatic_system module

This module collects 9 sensors' data from ADC0. Their meanings are below:

```c
typedef struct
{
	/* Gas source pressure, Uint:BAR */
	float sp;

	/* Normal mode pressure 1, Uint: kpa */
	float np1;

	/* Normal mode pressure 2, Uint: kpa */
	float np2;

	/* Normal mode flow, Uint: L/min*/
	float nf;

	/* Advanced mode pressure (triple chamber pressure), Uint: kpa */
	float ap_replenish;

	/* Advanced reflux pressure. Gas form outlet port to pump, Uint: kpa */
	float ap_reflux;

	/* Advanced circle pressure. Gas form pump to outlet port, Uint: kpa */
	float ap_circle;

	/* The percent of Oxygen. */
	float oxygen;
	
	/* The temperature in the equipment internal. This Data supplied by NTC. */
	float temp_internal;

	/* Uint: Kpa */
	float nf_deta_p;
}ps_sensor_t;
```

| Item | Description | Unit |
| --- | --- | --- |
| sp  | Gas source pressure | BAR |
| np1 | Normal mode pressure 1 | kpa |
| np2 | Normal mode pressure 2 | kpa |
| nf  | Normal mode flow | L/min |
| ap_replenish | Advanced mode pressure (triple chamber pressure) | kpa |
| ap_reflux | Advanced reflux pressure. Gas form outlet port to pump | kpa |
| ap_circle | Advanced circle pressure. Gas form pump to outlet port | kpa |
| oxygen | The percent of Oxygen | |
| temp_internal | The temperature in the equipment internal | |

The struct comes from *pneumatic_system.h*

# CFG module

# Event mechanism

The related source code is at "event.c" and "event.h", its behavior looks like the OS's CPU scheduling policy. There is a doubly linked list. Every time some other modules call evt_create, it allocates a new strucure object of evt_data_t, then adds it to this link list. Every event's function runs all the time if the node is still in the linked list.

| event | function |
| --- | --- |
|app_manager|app_manager|
|cfg|cfg_check_proc|
|dis|dis_proc|
|pcs|pcs_proc|
|safe|safe_proc|
|zro2|zro2_proc|
|terminal|term_proc|
|poweroff|p_core_poweroff|
|p_core|p_core_thread|
|key|key_proc|

# SelfCheck

# data module

# valve module

There are 7 normal valves:

```c
	VALVE_ID_STANDARD_OUTLET = 0,
	VALVE_ID_TRIPLE_CHAMBER_SWITCH,
	VALVE_ID_PUMP_OUTLET_3,
	VALVE_ID_PUMP_INLET,
	VALVE_ID_PUMP_OUTLET_1,
	VALVE_ID_PUMP_OUTLET_2,
	VALVE_ID_PQ,
```

And 2 proportional valves:

```c
enum
{
	/* Inlet proportional valve */
	VALVE_PROP_ID_INLET = RC_ID_INLET,
	/* pump proportional valve */
	VALVE_PROP_ID_PUMP = RC_ID_PUMP,
};
```

According to the source code, VALVE_ID_PUMP_OUTLET_3 is also treated as a proportional valve.

# circulate

circulate_airseal_deal

# About general PID routine

Any mode in these three modes has the same logical routine. They are all invoked from pcs_supply_manager.

# Questions

1. What's actual differences bewteen DT_GAS_TYPE_CENTER and DT_GAS_TYPE_BOTTLE?
2. 