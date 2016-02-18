# Lithium-Ion Polymer Batteries
## Charging
_from_ http://batteryuniversity.com/learn/article/charging_lithium_ion_batteries

* Turn off while charging
  * A portable device should be __turned off__ while charging. This is to prevent the circuit that the battery is powering from drawing current while the battery is charging.
  * The load of the device (known as a __parasitic load__) will confuse the charger by drawing current and preventing the battery from reaching the __saturation stage__.
    * A battery may be close to or fully charged, but the __parasitic load__ will prompt a continued charge, causing stress.

* Fully charged
  * (1) Full charge occurs when the battery reaches the voltage threshold and the current drops to ~3% of the rated current.
  * (2) A battery may also be considered fully charged if the current drops to a lower level and is stable and cannot go down further. In this second scenario, an elevated __self-discharge__ may be preventing the battery from completing the end of the __saturation stage__.
  
* Charge rate
  * Increasing the charge current does not linearly cause the battery to charger faster.
    * The battery may reach __peak voltage__ faster, but the __saturation charge__ time will be increased as well.
  * A high current charge can be used to fill the battery to ~70% at a faster rate.

* Is a full charge required?
  * Li-ion batteries do not need to be fully charged (unlike lead-acid batteries).
    * There are no benefits to a full charge, besides a longer runtime for that single cycle.
    * In fact, it is better not to fully charge the battery because a higher voltage stresses the battery.
  * Choosing a lower __voltage threshold__, or eliminating the __saturation charge__ prolongs battery life.
  * To achieve maximum runtimes, most consumer devices choose a full charge over providing ideal conditions for battery life.
