# Parts research

This folder contains component research before selection. No purchasing decision or build validation is recorded here.

- [Full component inventory, six fields per part, connection diagrams and sources](meltybrain-component-inventory.md)
- [Research record and evidence status](research-record.md)
- [Related project/firmware survey](../code/meltybrain-project-survey.md)

## 1. One-page component checklist

**R = required function**, **C = common in the inspected examples**, **O = optional**. **O→R** means required only when that branch is chosen. A role can be inside another part. “Common” is descriptive, not a measured percentage. Rule-required items depend on the event. This checklist groups small supporting parts; the numbered inventory below separates them.

| Area | Components and status |
| --- | --- |
| Computing | **R:** processor, circuit interconnections, clock, program memory, working memory, control firmware/timing. **C:** persistent calibration storage, programming/debug connection. **O:** reset/boot control, separate watchdog/supervisor. |
| Heading/motion sensing | **R:** a usable rotation/heading-estimation approach. **O→R:** high-range accelerometer(s), angular-rate sensor, magnetic-field sensor, rotating pickup coil, wheel/motor encoder and target. **O:** inversion/light sensor, ranging sensor. These are alternatives or supplements. |
| Sensor support | **O→R:** analog amplifier, converter, comparator, reference/bias and filter resistors/capacitors, interface pull resistors, logic-level translation, optical lens/hood/light guide. |
| External optical reference | **O→R:** beacon emitter, driver/current control, timing controller, power source and mounting; onboard optical receiver/photodiode, conditioning and viewing aperture. |
| Driver feedback | **C:** heading light. **O→R:** current limiting, light driver, digital light controller, visible mount/light window. **Rule-dependent R:** power-status indicator. |
| Radio and control | **R for radio operation:** operator transmitter/controls and its power, onboard receiver, antennas, signal interface, command-freshness/failsafe behavior. **O→R:** antenna feed, arming switch, trim control, telemetry radio/gateway, logging memory/socket, detachable data connectors. |
| Drive electronics | **R:** motor(s), controllable power stage, command interface, inductive-current return path. **O→R:** bridge/inverter, gate driver, brushless commutation/rotor feedback, current sensing, enable/inhibit, thermal path, configuration interface. Brushes/commutator are intrinsic to brushed motors. |
| Mechanical drive | **R for wheeled layouts:** wheel/contact surface, hub/coupling, shaft/axle, rotational support, motor mounting and retention. **O→R:** separate tire, outboard bearings/bushings, shims/spacers/thrust surfaces, retainers, gearbox/gears, belt/pulleys/tension adjustment, compliant coupling. **O:** skids and drive guards. |
| Power | **R for battery operation:** cells/pack interconnect, conductors/terminations, insulation and secure battery retention. **O→R:** power connectors, distribution junction, regulator, local/bulk capacitors, motor-noise suppression, regenerative-energy handling. **O:** voltage/current/temperature monitoring, balance connector, management/protection board, fuse/breaker/current limiting, polarity/transient protection. **Rule-dependent R:** accessible power disconnect/link. |
| Structure and retention | **R:** chassis/load paths; motor, battery and electronics retention; wire support and insulation. **C/O by layout:** shell/armour, floor, access lid, impact surface/impactor joint, internal partitions/cushioning, sensor/antenna/light mounts, disconnect access, connectors, fasteners/washers/nuts/inserts, adhesives/retainers, balance adjustment, inversion features, replaceable wear modules. |
| Rule/handling equipment | **Rule-dependent R:** motion/weapon lock and attachment, edge covers, power light, disconnect labels/access, safe transport/handling support. **R for spin tests in this workflow:** suitable containment. Exact materials, stopping behavior and exemptions are event-specific. |
| Building and testing, off robot | **R for rechargeable/programmed workflow:** compatible charger/leads/input supply and programming computer/interface. **C:** storage/charging containment, cradle, scale/measurement tools, assembly/repair tools and task protection. **O:** balance jig, calibration fixture, electrical instruments, independent rotation reference/recording. Event rules may make items compulsory. |
| Optional overhead vision | **O→R within add-on:** camera, lens, stable mount/cables, observable robot feature, usable illumination, image-processing computer/interface, calibration reference, ground/robot radio endpoints and antennas, external power/data wiring, time alignment, correction validation and operator override. |

See the detailed entries for dependencies and evidence. **R** identifies a function within the stated architecture; it is not an instruction to buy a separate module.
