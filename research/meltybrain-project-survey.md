# Melty brain / translational drift combat robot survey

Research snapshot: **8 November 2026, Australia/Sydney**.

This survey contains **188 separate project/source entries**: 23 core controller repositories, 57 additional repositories and research sources, 41 forks/variants and radio-sensing experiments, and 67 builder/history/competition records. These numbers count records, **not confirmed distinct physical robots**. A robot and its controller repository can have separate records. Companion hardware, simulations, empty project repositories, prototypes and unfinished work are included. Possible aliases or revisions remain explicitly uncertain.

The purpose is to preserve distinct documented ideas and methods. There is no project ranking, comparative score or design recommendation. The index is in source-group order, without merit ordering.

**Evidence labels.** Confirmed in code / inspected means the stated source was read, not that the firmware compiled or the robot worked. Reported means a builder, author or event source states it. Planned means intended work rather than a demonstrated implementation. Inferred means an interpretation explicitly marked as such. Not found means not established in the inspected material; it does not prove the information is absent everywhere. No robot, firmware build or simulation was independently run for this survey.

**Citation scope.** Links beside claims identify primary articles, exact files/functions or competition records. Most core/fork code citations are pinned to inspected commits. Some additional-source citations use mutable default-branch URLs; interpret those against this snapshot date. Repository push dates are UTC metadata, not completion dates or last successful tests. A source's own incorrect or unfinished formula is described as written, without silently repairing it. License descriptions record notices found, not a legal audit.

**Search coverage.** Searches used melty brain, meltybrain, translational drift, TD spinner, tornado drive, accelerometer, magnetometer, IR/infrared, heading, RSSI and related names. GitHub repository search was combined with author crosslinks, upstream/fork lineage, blogs, Bristol Bot Builders and other forums, NHRL pages, RobotShop, Hack Club, Hackster, BeagleBoard, published interviews, university reports and theses, and video descriptions. GitLab, Tangled, Codeberg, Bitbucket and SourceForge were also searched or followed where relevant. Generic visual-odometry “translational drift,” unrelated Tornado projects, molecular melting-analysis tools and observability software were excluded.

**Coverage limitation.** Internet-wide exhaustiveness cannot be demonstrated. Private/unindexed projects, inaccessible pages, deleted histories, Discord/Facebook material and untranscribed video detail can be missing. Video descriptions, captions or author posts are distinguished from actually watched footage. Access failures and unresolved leads are listed at the end; a cache miss, robots restriction or subscriber wall is not called a dead link.

## Short index

- [LukeUeda/TesselateF](#p001) — Featherweight controller using radial acceleration, sector modulation, and adjustable virtual heading.
- [LukeUeda/Tessellate](#p002) — Earlier accelerometer controller with timer-based heading integration and experimental calibration routines.
- [skysdottir/PotatoMelt](#p003) — Arduino controller combining DShot motor modulation with speed-indexed acceleration correction.
- [skysdottir/potatomelt-esp32](#p004) — ESP32 controller with dual accelerometers, Bluetooth gamepad input, and shaped translation pulses.
- [swallenhardware/MeltyHalo](#p005) — Halo firmware combining infrared beacon and accelerometer heading with a POV display.
- [nothinglabs/openmelt2](#p006) — Arduino translational-drift controller supporting one or two motors and interactive calibration.
- [nothinglabs/openmelt](#p007) — Original AVR controller using analog acceleration and phase-timed motor switching.
- [nothinglabs/openmelt-ble](#p008) — Experimental Nordic BLE controller with Zephyr firmware and an Android control application.
- [AlfredoSystems/SimpleMelt](#p009) — Melty control library with magnetic heading correction and Rotini hardware examples.
- [AlfredoSystems/Rotini-Hardware](#p010) — Integrated controller board design with sensing, radio, power regulation, and manufacturing assets.
- [GHF/gyroking](#p011) — Gyroscope-based dual-brushless controller using custom electronics and narrow translation pulses.
- [jackmaxg/melty](#p012) — Analog-acceleration controller using sinusoidal motor modulation, with board and beacon designs.
- [AmbientChaos/Spin-Doctor---Meltybrain-Software](#p013) — Experimental accelerometer controller with fitted calibration curves and DShot motor outputs.
- [AmbientChaos/Spin-Doctor-V2](#p014) — Experimental controller deriving body heading from ESC telemetry instead of accelerometers.
- [Blackcatmaxy/Meltybrain](#p015) — ESP32-S3 controller with dual accelerometers, Bluetooth input, and unresolved timing issues.
- [Mew463/Oreo](#p016) — Infrared-beacon controller with triangular translation pulses, inversion sensing, and laptop controls.
- [PsychoticRobotics/Project-Meltybrain](#p017) — Master Wu development firmware containing accelerometer processing and unfinished robot control integration.
- [lpinfinity/picomelt](#p018) — Unfinished RP2040 MicroPython experiment implementing DShot output before melty control.
- [Nv7-GitHub/sunshine](#p019) — One-pound robot system combining magnetic heading, acceleration, telemetry, and desktop replay.
- [MeltyFC/meltyfc](#p020) — STM32 flight-controller platform with implemented logic modules and unfinished firmware integration.
- [swallenhardware/MeltyHitNSpinV1_1](#p021) — Hit ’N Spin firmware using acceleration and photodiode beacon heading correction.
- [gavin4d/dangerDonut](#p022) — 150-gram robot project combining infrared phase estimation, acceleration, and POV graphics.
- [celeron55/kasari](#p023) — Autonomous spinning robot using fixed LIDAR, accelerometer timing, and sinusoidal motor modulation.
- [Holy Guacamole — Kieran Klukas (Tangled canonical, GitHub mirror)](#p024) — Antweight multi-IMU controller, RSSI beacon experiment, and shared firmware/simulation estimator.
- [OlivePrichard/meltybrain](#p025) — Rust async ESP controller with incomplete melty estimation and motor-board I2C commands.
- [OlivePrichard/meltybrain_driver_station](#p026) — Separate Rust desktop gamepad input companion for OlivePrichard's controller.
- [DublerIno meltybrain PCB](#p027) — First-iteration ESP32-S3 SuperMini and high-g accelerometer PCB.
- [Luna Waller — MeltyBrain PCB](#p028) — 34 × 34 mm PCB design with fabrication and electrical validation still pending.
- [DiamondSpectre1 — Antweight MeltyBrain](#p029) — One-pound polycarbonate/PETG sandwich robot with N20 drives and removable AR500 blades.
- [SpinStroyer — @koko / KoKoOogit](#p030) — Work-in-progress antweight design with a short journal stub.
- [Ty Tremblay — MeltyBrainHERO](#p031) — C# HERO/VictorSPX experiment with incomplete accelerometer conversion.
- [Toby Thomson — Python meltybrain simulator](#p032) — Pygame/Matplotlib differential-wheel translation simulation.
- [AVatLeeds/meltybrain](#p033) — Separate GitHub fork of Toby Thomson's Python simulator.
- [N0x1an/MeltyBrain](#p034) — Arduino receiver/PWM and NeoPixel example, without heading estimation.
- [Brainfreeze — FROST Robotics, University of Connecticut](#p035) — University meltybrain bring-up repository with tank drive and experimental acceleration handling.
- [FROST Brainfreeze PCB companion repository](#p036) — Separate KiCad hardware repository associated with Brainfreeze.
- [Sabrebrain / Sabretooth — Owen Fisher](#p037) — Dual-core RP2040 sinusoidal drift controller with an animated POV screen.
- [Un-Koalified — CU Combat Bots](#p038) — Early receiver bring-up code for a named meltybrain project.
- [Tbarkin121 — STM32F334 MeltyBrain project](#p039) — STM32/FreeRTOS development scaffold; translation implementation not established.
- [PeronaBot — OPRobots](#p040) — One-pound ESP32-C3 robot with half-cycle sinusoidal motor modulation.
- [LostInTranslation — NRS048](#p041) — Multi-weightclass board and dual-accelerometer/CoR estimation experiments.
- [Persistence of Memory — jkadin](#p042) — Thirty-pound WIP with selectable motor-eRPM or accelerometer rotation estimate.
- [Shay-Nanigans dual-accelerometer Bluetooth meltybrain](#p043) — ESP32 dual-core, two-sensor timing controller with command-driven setup.
- [Dylan Mays — Personal Meltybrain](#p044) — OpenMelt-derived spin-test development with documented receiver and sensor bench tests.
- [Unscheduled Disassembly — Dylan and Luke](#p045) — Three-pound OpenMelt-derived custom-PCB and AR500 weapon project.
- [Rust'N'Roll — lorenzoGT2007](#p046) — 150g Teensy controller with one motor modulated and RPM-dependent phase calibration.
- [Sweati — Liam Long](#p047) — Three-pound dual-sensor cosine controller with adjustable radius and inactivity lock.
- [q314tracy — CircuitPython melty robot](#p048) — Four-motor-layout experiment currently reading high-g acceleration and transmitting telemetry.
- [q314tracy — melty transmitter](#p049) — Nunchuk/OLED/RFM69 custom remote companion.
- [q314tracy — Melty Simulations](#p050) — Translation-vector and three-ToF wall-localization proof-of-concept simulations.
- [UCR/HCR — Melty Brain](#p051) — ESP32 BNO08x heading/SD logging experiment with unresolved IMU stoppages.
- [StanBeru77 — UCR Melty Brain fork](#p052) — Separate fork retaining UCR's IMU/SD heading test.
- [Doomba — yahirconejo-cpu](#p053) — ESP-NOW two-ESC experiment using a low-range accelerometer.
- [Max-Med — Melty Brain Code](#p054) — Three-motor Arduino/Nano-era phase-gated translation experiment.
- [jjrreett — melty-brain planning project](#p055) — Mind-map design exploration of beetleweight layouts and software-in-loop goals.
- [Sarcophilus — negativeview](#p056) — Named meltybrain battlebot repository with minimal written description.
- [Redline — matt-nolan11](#p057) — Insect-class meltybrain project with exact weight class undecided.
- [Tunamelt — Joe Earlam](#p058) — Empty repository describing planned asynchronous sinusoidal firmware.
- [MeltyMind — fks-2702](#p059) — Empty repository describing planned STM32 full-body-spinner control.
- [Trick V2 — Gaantry88](#p060) — Empty repository intended to hold second-version meltybrain parts.
- [Multybrain — peterhenryd](#p061) — Twelve-pound autonomous/manual Teensy concept represented by repository metadata and license.
- [DONUT — ManasAgrawal05](#p062) — MeltyHalo fork with experimental OpenMelt-style code largely commented out.
- [Jeremiah FBS — NURobotics](#p063) — ESP32/PS4 MeltyHalo port retaining hybrid IR and accelerometer logic.
- [AnthonyMichaelTDM — Rust battlebot firmware experiments](#p064) — Rust ESP high-g sensor, DShot and LED diagnostic monorepo.
- [Melontype — zenith-parsec](#p065) — Teensy iBus controller with empirical acceleration-to-RPM table and POV numbers.
- [Beyblade Melty Brain Kit — AriM224](#p066) — Plastic one-pound kit controller with DShot600 and timed deceleration pulses.
- [anba9306-ai — Melty-Brain placeholder](#p067) — Arduino project skeleton without implemented melty control.
- [Candas1 — Melty Brain Simulator](#p068) — Browser simulator with adjustable high/low wheel speeds and acceleration response.
- [OPRobots — H3LIS331 demo](#p069) — STM32F401 high-g SPI driver and centripetal angle-estimation demonstration.
- [Homer — Zac Q Howard](#p070) — ESP32-C3 differential-drive controller with a currently empty melty-drive function.
- [Stuffed Crust — Wildcat Robotics / buttonbugs](#p071) — OpenMelt-derived nonblocking controller with width-controlled translation windows.
- [Hamachi — Griswald Brooks](#p072) — OpenMelt2 hard fork with a single motor and spring-centered pistol-trigger calibration.
- [D.O.N.U.T. — Cameron Cox](#p073) — Separately named OpenMelt2 fork with ESP32 and brushless hardware listed.
- [Dark Melty — ssharp-source](#p074) — OpenMelt fork exploring FIR filtering, continuous drive and new MCU targets.
- [Eyeliner / Eyeliner Evo — Caleb012711](#p075) — Extensive three-pound design/CAD/autonomy concept with hardware build status unverified.
- [Jackson Gray — MIT inertial measurement hardware study](#p076) — 2020 analog IR-reference and motor-phase sensing study for translational drift.
- [MagnetoMelty — Team Mind Melt (GitLab)](#p077) — GitLab repository linked by Spencer Allen to the Meltycompass investigation.
- [John Aduroja — MTSU meltybrain/autonomy thesis](#p078) — Three-pound prototype thesis with NRC use reported and separate scan-charge-spin autonomy example.
- [Beyblade of Death — Minhaz Abedin](#p079) — Hack Club prototype with planned Raspberry Pi opponent tracking.
- [Gentry Clark — PocketBeagle meltybrain circuit](#p080) — 2018 beetleweight circuit prototype with an OpenMelt-derived AVR listing requiring a PocketBeagle port.
- [OscarGRG14/TesselateF](#p081) — Featherweight Teensy controller fork with two-axis acceleration sensing and vector translation.
- [mechovation/TesselateF](#p082) — Behind-upstream TesselateF fork retaining Teensy acceleration-based heading and motor control.
- [13djwright/TesselateMeltyFork](#p083) — TesselateF fork matching the inspected upstream branch, including accelerometer recovery changes.
- [13djwright/MeltyBrain](#p084) — PotatoMelt fork with AVR DShot timing and eight-point speed calibration.
- [dinoceros/The-Wheel-of-Power](#p085) — Antweight controller with LoRa gamepad link, acceleration-derived phase and motor-lag adjustment.
- [SaintSampo/The-Wheel-of-Power](#p086) — Earlier Wheel of Power fork retaining LoRa control and forward/back translation.
- [teamhappybots/MeltyHalo](#p087) — Halo controller fork retaining infrared, acceleration and hybrid heading-sensing modes.
- [sicktastic/MeltyHalo](#p088) — Halo controller fork retaining hybrid sensing, POV display and arcade driving.
- [nurdism/MeltyHalo](#p089) — Halo controller fork with unchanged inspected upstream acceleration and beacon code.
- [martinkuberski/MeltyHalo](#p090) — MeltyBrian Flysky adaptation with acceleration-only controls and a separate sensorless experiment.
- [Ryan-WHOOP-26982E/PotatoMelt_Stig](#p091) — PotatoMelt fork retaining AVR control, correction tables and interrupt-driven DShot.
- [Ryan-WHOOP-26982E/stigpotatomelt-esp32](#p092) — XIAO ESP32-S3 SBUS adaptation with single vertical accelerometer and telemetry.
- [TGower/potatomelt-esp32](#p093) — ESP32 PotatoMelt variant using Bluetooth Xbox controls, dual accelerometers and DShot.
- [shrine-priestess/LoserMelt](#p094) — SBUS PotatoMelt derivative with averaged absolute sensor axes and parabolic translation.
- [kemacalls/ServalLoserMelt](#p095) — Earlier LoserMelt fork retaining SBUS controls and single-axis acceleration sensing.
- [BTSC10/Oreo](#p096) — Beetleweight robot repository with hardware assets and inspected STM32 application skeleton.
- [Danwith2ns/Oreo](#p097) — Earlier Oreo fork containing design assets and an inspected STM32 application skeleton.
- [rtforsy/openmelt](#p098) — Native AVR Open Melt fork retaining analog acceleration and timer-based motor phases.
- [acklenx/openmelt](#p099) — Native AVR Open Melt fork with inherited analog sensing and phase timing.
- [qbnut/openmelt](#p100) — Native AVR Open Melt fork retaining moving-average acceleration and binary drive scheduling.
- [dhmeves/openmelt](#p101) — Open Melt fork matching inspected upstream code and obsolete-version documentation.
- [gentry-atkinson/openmelt](#p102) — Open Melt fork removing historical artifacts while retaining the main control source.
- [amramsey/openmelt2](#p103) — Arduino Open Melt 2 fork matching the inspected upstream default branch.
- [teamhappybots/openmelt2](#p104) — Arduino controller fork retaining interactive radius calibration and angular motor windows.
- [lobonz/openmelt2-ESP32](#p105) — Work-in-progress M5 Stamp S3 port with servo-PWM ESCs and web diagnostics.
- [gmazin/openmelt2-custom](#p106) — Pico port with dual SPI accelerometers, CRSF input and PIO DShot.
- [Cschlaefli/openmelt2](#p107) — Open Melt 2 fork adding a development container for planned ESP32 conversion.
- [DiracDesigns/openmelt2](#p108) — Arduino fork adding brushless Servo branches while binary throttle remains selected.
- [acklenx/openmelt2](#p109) — Earlier Open Melt 2 fork retaining Arduino acceleration-based phase scheduling.
- [HelloGuy8000/espmelt](#p110) — ESP32-described repository whose inspected default branch retains inherited Arduino firmware.
- [mak0t0san/openmelt2](#p111) — Earlier default-branch Open Melt 2 snapshot retaining Arduino control and calibration.
- [Ryan-WHOOP-26982E/openmeltStig](#p112) — Separately hosted Open Melt 2 derivative with inherited controller source.
- [TomasSiauliaiNights/openmelty](#p113) — Standalone Open Melt-style snapshot using ADXL375 sensing and remapped motor settings.
- [TomasSiauliaiNights/Openmeltyy](#p114) — Empty public repository identity with no available controller source or documentation.
- [Jacob-Harrell-RIT/PolarMelt](#p115) — Teensy sensing and spin experiments proposing magnetometer-assisted directional-error detection.
- [EpicStuff/NSL-Susan-Code](#p116) — PotatoMelt derivative with PlatformIO layout, altered PID settings and calibration controls.
- [wengdahl/whirlwind-combat-SW](#p117) — Experimental ESP32 wireless controller and acceleration-heading sketches with unfinished melty translation.
- [Dean27817/FizzBee-V2](#p118) — Custom ESP32-S3 controller with dual acceleration inputs and sinusoidal vector motor mixing.
- [Dean27817/Universal-Melty-AIO](#p119) — Two-accelerometer board project with Xbox controls, runtime radius inference and multitasking.
- [royce24864/vibemelt](#p120) — ESP32-C3 firmware with radial projection, scheduled motor phases, diagnostics and simulator.
- [TGower/rotation_sensing](#p121) — Radio-based rotation estimator using ESP-NOW RSSI, period matching and I/Q phase.
- [Halo — Spencer Allen and team](#p122) — Ring chassis using accelerometer and infrared reference, with documented algorithm revisions.
- [Hit 'N Spin — Spencer Allen](#p123) — One pound single wheel platform testing magnetometer heading and accelerometer control.
- [Rotating-coil heading experiment — Spencer Allen](#p124) — Bench rotating coil reference later failed amid installed motor magnetic interference.
- [Meltycompass — adaptive-sampling Goertzel experiment, Spencer Allen](#p125) — Adaptive angle sampling and Goertzel heading experiment with unresolved implementation flaw.
- [Room-Ba — Joe Earlam / IrregularJoe](#p126) — Brushed and brushless prototype documenting acceleration filtering, modulation, and hardware failures.
- [Project LiftOff — Andrew and Jim Kazmer](#p127) — Three pound platform using opposed accelerometers and repeated hardware development.
- [DeepMelt — Team Liftoff](#p128) — Autonomous meltybrain platform with published mechanical hardware and sparse control details.
- [Torment Nexus — Alberta Big Bot Builders](#p129) — Sixty pound platform with documented traction, controller, and structural failures.
- [Super Nintendo Chalmers — Brian Cassin](#p130) — One pound predecessor supplying firmware experience for the larger Torment Nexus.
- [Light Seeking Spinner — Dale A. Heatherington](#p131) — Analog light following experiment using photocells, relays, and timed motor reversal.
- [Small radio-controlled full-body-spinner prototype — Dale Heatherington](#p132) — Small radio controlled infrared beacon prototype preceding the combat sized build.
- [Scary-Go-Round — Dale Heatherington](#p133) — Thirty pound infrared controlled platform with mechanical tank mode conversion.
- [Spinning Compass — Dale Heatherington](#p134) — Bench magnetic heading circuit demonstrating comparator driven half rotation LED indication.
- [Lobotomi — Dylan Park / Georgia Tech RoboJackets](#p135) — RoboJackets brushed implementation documenting motor, receiver, MOSFET, and OpenMelt2 usage.
- [DangerCone — UCLA ASME 2016–2017](#p136) — UCLA cylindrical wheel weapon design documented through a participant control prototype.
- [Barrel Roll — UCLA ASME, Ryan's portfolio](#p137) — UCLA cylindrical shell project documenting mechanical construction, with identity overlap unresolved.
- [Disperse — William / Team UR (translational drift planned only)](#p138) — One wheel combat spinner with translational drift reserved for future development.
- [(Liftoff)² — NHRL record](#p139) — League category record identifies a meltybrain; detailed implementation evidence remains unavailable.
- [AC/RC — NHRL record](#p140) — 12 pound league record classified as meltybrain, with limited implementation information.
- [Alicorn — NHRL record](#p141) — 3 pound league record classified as meltybrain, with limited implementation information.
- [Ankle-breaker (II) — NHRL record](#p142) — 3 pound league record classified as meltybrain, with limited implementation information.
- [Brian — NHRL record](#p143) — 3 pound league record classified as meltybrain, with limited implementation information.
- [Doom — NHRL record](#p144) — League category record identifies a meltybrain; detailed implementation evidence remains unavailable.
- [Emotional Trauma — NHRL record](#p145) — League category record identifies a meltybrain; detailed implementation evidence remains unavailable.
- [Flip N' Cut — NHRL record](#p146) — 3 pound league record classified as meltybrain, with limited implementation information.
- [Flip-N-Cut 12 — NHRL record](#p147) — League category record identifies a meltybrain; detailed implementation evidence remains unavailable.
- [Hockii — NHRL record](#p148) — 12 pound league record classified as meltybrain, with limited implementation information.
- [Jerry — NHRL record](#p149) — 3 pound league record classified as meltybrain, with limited implementation information.
- [Karoomba — NHRL record](#p150) — 3 pound league record classified as meltybrain, with limited implementation information.
- [Katrina — NHRL record](#p151) — League category record identifies a meltybrain; detailed implementation evidence remains unavailable.
- [LiftOff — NHRL record](#p152) — League category record identifies a meltybrain; detailed implementation evidence remains unavailable.
- [Little Melty — NHRL record](#p153) — 3 pound league record classified as meltybrain, with limited implementation information.
- [Lobotomizer Prime — NHRL record](#p154) — League category record identifies a meltybrain; detailed implementation evidence remains unavailable.
- [Marceline — NHRL record](#p155) — League category record identifies a meltybrain; detailed implementation evidence remains unavailable.
- [Neether — NHRL record](#p156) — League category record identifies a meltybrain; detailed implementation evidence remains unavailable.
- [Omnipotence — NHRL record](#p157) — League category record identifies a meltybrain; detailed implementation evidence remains unavailable.
- [OpenHELL — NHRL record](#p158) — League category record identifies a meltybrain; detailed implementation evidence remains unavailable.
- [OrbitR and RotatR — NHRL record](#p159) — 3 pound league record classified as meltybrain, with limited implementation information.
- [Project LiftOff-12 — NHRL record](#p160) — 12 pound league record classified as meltybrain, with limited implementation information.
- [Project LiftOff-30 — NHRL record](#p161) — 30 pound league record classified as meltybrain, with limited implementation information.
- [R.U.D. — NHRL record](#p162) — League category record identifies a meltybrain; detailed implementation evidence remains unavailable.
- [Scramble — NHRL record](#p163) — 12 pound league record classified as meltybrain, with limited implementation information.
- [Sir Pops A Lot — NHRL record](#p164) — League category record identifies a meltybrain; detailed implementation evidence remains unavailable.
- [Spin-a-ma-thing — NHRL record](#p165) — 3 pound league record classified as meltybrain, with limited implementation information.
- [T T — NHRL record](#p166) — League category record identifies a meltybrain; detailed implementation evidence remains unavailable.
- [The arena floor — NHRL record](#p167) — League category record identifies a meltybrain; detailed implementation evidence remains unavailable.
- [The Greatest Challenge — NHRL record](#p168) — 3 pound league record classified as meltybrain, with limited implementation information.
- [The Greatest Danger — NHRL record](#p169) — 3 pound league record classified as meltybrain, with limited implementation information.
- [Ti Grrr — NHRL record](#p170) — League category record identifies a meltybrain; detailed implementation evidence remains unavailable.
- [Wheel of Misfortune — NHRL record](#p171) — League category record identifies a meltybrain; detailed implementation evidence remains unavailable.
- [WhirlWax — NHRL record](#p172) — League category record identifies a meltybrain; detailed implementation evidence remains unavailable.
- [Take Cover — Gareth Barnaby](#p173) — Featherweight hub motor design documenting sector reversal and centrifugal hardware problems.
- [TRAC — Gareth Barnaby](#p174) — Featherweight successor using encoder commutation, VESC controllers, and revised mechanical packaging.
- [Nuts 2 — Rory Mangles / Team Nuts](#p175) — Robot Wars heavyweight with custom meltybrain board provenance documented by another builder.
- [Nuts 1 — Rory Mangles / Team Nuts (predecessor; meltybrain unconfirmed)](#p176) — Contextual predecessor to Nuts Two, without verified translational drift implementation evidence.
- [Hocki — Georgia Tech RoboJackets](#p177) — RoboJackets sensor fusion design combining accelerometers, infrared beacons, and magnetometer.
- [Herr Gepoünden — Team Zwölfpack](#p178) — Sixty pound historical meltybrain identified through firsthand opponent and event accounts.
- [Y-POUT — Team Whyachi](#p179) — Whyachi heavyweight with externally described ground referenced mechanical cam steering.
- [Why Not — Team Whyachi](#p180) — Whyachi middleweight with external mechanical steering description and inaccessible team documentation.
- [CycloneBot — CM Robotics / Michael Worry and team](#p181) — Heavyweight FPGA platform combining magnetic reference, wheel encoders, and torque modulation.
- [Blade Runner 1 — Ilya Polyakov / Team Carnivore](#p182) — Historical predecessor operated mainly as pushbot; translational drift completion remains unverified.
- [Blade Runner 2 — Ilya Polyakov / Team Carnivore (unfinished controller)](#p183) — Composite middleweight whose planned meltybrain controller remained unfinished before competition.
- [ZAP — Team Bolt / Team Panic (2022 application design)](#p184) — Proposed heavyweight combining meltybrain locomotion and separate spinning weapons for application.
- [Pac-Attac — RoboWarner / Warner](#p185) — One pound platform documenting selectable sensing, dual range accelerometers, and halfturn modulation.
- [Pong — Backslash Robotics (translation unconfirmed)](#p186) — Single motor plastic spinner with overheating problems; controlled translation remains unverified.
- [Unnamed UofT meltybrain — Nirmal Arunkumar / Combat Robotics Association](#p187) — Unnamed university platform reporting accelerometer calibration, PID speed control, and watchdogs.
- [Persistence of Memory — Meditative Resistance](#p188) — Thirty pound clock themed platform with hardware details and directional LED display.

---

<a id="p001"></a>

## P001. LukeUeda/TesselateF

1. **Identity/activity:** [TesselateF](https://github.com/LukeUeda/TesselateF), LukeUeda; featherweight meltybrain code, last pushed 2025-08-14.
2. **Source type/read:** Arduino C++ implementation; `teensy.ino`, `Meltylock.cpp`, `Motor.cpp`, `Receiver.cpp`, `RobotState.cpp`, `LedController.cpp`, `Config.hpp`, `Constants.hpp`. [Main](https://github.com/LukeUeda/TesselateF/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/teensy.ino).
3. **Robot context:** Featherweight stated; actual weight, dimensions and competition results not found. [README](https://github.com/LukeUeda/TesselateF/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/README.md).
4. **Hardware:** Teensy-oriented sketch, LIS331-compatible I²C accelerometer, two VESC PWM outputs at 250 Hz/12 bits, five LED outputs, six PWM RC channels. Exact board, ESC and motor models not found. [Constants](https://github.com/LukeUeda/TesselateF/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/include/Constants.hpp), [setup](https://github.com/LukeUeda/TesselateF/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/teensy.ino).
5. **Heading sensor/placement:** X/Y acceleration magnitude, configured effective radius 108.3943252563 mm, 400 g conversion and 400 Hz sensor setting. [Meltylock constructor/read](https://github.com/LukeUeda/TesselateF/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/src/Meltylock.cpp).
6. **Math/rates:** `calculateAngularVelocity()` computes √(a×1000/|radius|), converts to degrees/s, then `update()` integrates elapsed microseconds. Main-loop integration; fixed control rate not found. [Estimator](https://github.com/LukeUeda/TesselateF/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/src/Meltylock.cpp).
7. **Drift:** Driver steering changes integrated heading; radius and translation correction adjustments exist. No absolute reference found. The velocity expression uses `translation_offset_adjust`, whereas another stored parameter is `translation_offset`; this is an untested code observation. [Estimator](https://github.com/LukeUeda/TesselateF/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/src/Meltylock.cpp).
8. **Translation:** XY magnitude capped at 1 and `atan2()` direction; two 180° sectors alternate increased/decreased motor commands. [MELTY branch](https://github.com/LukeUeda/TesselateF/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/teensy.ino).
9. **LED:** Five LEDs share a 50° arc, loading animation and all-on failsafe. [LED controller](https://github.com/LukeUeda/TesselateF/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/src/LedController.cpp).
10. **Calibration:** Live radius/translation adjustment modes; persistence not found. [Main](https://github.com/LukeUeda/TesselateF/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/teensy.ino).
11. **RC/modes/failsafe:** Six interrupt-captured PWM channels; no edge for 1000 ms triggers motor-disable. Tank, melty, radius-adjust plus declared additional modes; some reach the default motor-disable branch. [Receiver](https://github.com/LukeUeda/TesselateF/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/src/Receiver.cpp), [mode mapping](https://github.com/LukeUeda/TesselateF/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/src/RobotState.cpp).
12. **Unusual ideas:** Separate heading, motor, receiver, LED and state classes; Wire restart after long I²C read. [Estimator](https://github.com/LukeUeda/TesselateF/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/src/Meltylock.cpp).
13. **Problems/results:** No author performance narrative found; timeout-recovery code exists, but measured handling/heading accuracy not found. [Estimator](https://github.com/LukeUeda/TesselateF/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/src/Meltylock.cpp).
14. **License:** [MIT](https://github.com/LukeUeda/TesselateF/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/LICENSE).

<a id="p002"></a>

## P002. LukeUeda/Tessellate

1. **Identity/activity:** [Tessellate](https://github.com/LukeUeda/Tessellate), last pushed 2023-12-10; separate from TesselateF.
2. **Source type/read:** Arduino C++; `Tessellate.ino`, `receiver.cpp`, `ledDriver.cpp`, README. [Sketch](https://github.com/LukeUeda/Tessellate/blob/a554741c4c663a92da4b5c56c6af741b163271fe/Tessellate.ino).
3. **Robot context:** Described as an accelerometer translational-drifting robot; weight/class and results not found. [README](https://github.com/LukeUeda/Tessellate/blob/a554741c4c663a92da4b5c56c6af741b163271fe/README.md).
4. **Hardware:** Arduino/Teensy-style `IntervalTimer`, LIS331 I²C sensor, two 32 kHz/12-bit motor outputs, four receiver channels, one LED. Exact board/motors/ESC not found. [Sketch setup](https://github.com/LukeUeda/Tessellate/blob/a554741c4c663a92da4b5c56c6af741b163271fe/Tessellate.ino).
5. **Sensor/placement:** X/Y magnitude, high-range/400 g conversion, 1 kHz sensor configuration; `ACCEL_RADIUS=1.19537` explicitly described as calibrated effective millimetre radius. [Sketch](https://github.com/LukeUeda/Tessellate/blob/a554741c4c663a92da4b5c56c6af741b163271fe/Tessellate.ino).
6. **Math/rates:** A 30 µs timer runs angular velocity, heading integration and LED update; accelerometer read in main loop. Formula is literally √(a×RAD_TO_DEG×1000/|effective_radius|); conversion inside the root should not be silently rewritten as a verified physical formula. [Functions/ISR](https://github.com/LukeUeda/Tessellate/blob/a554741c4c663a92da4b5c56c6af741b163271fe/Tessellate.ino).
7. **Drift:** Driver shifts virtual heading, up to 360°/s times stick input; effective-radius calibration function. Absolute correction not found. [steerHeading](https://github.com/LukeUeda/Tessellate/blob/a554741c4c663a92da4b5c56c6af741b163271fe/Tessellate.ino).
8. **Translation:** Forward/back input changes motor outputs by unequal 1400/700-count deltas; switching at heading+45° crossing zero creates rectangular half-turn modulation. [translationalDrift](https://github.com/LukeUeda/Tessellate/blob/a554741c4c663a92da4b5c56c6af741b163271fe/Tessellate.ino).
9. **LED:** Arc, inverted/animated arc, octagon, WAKA_WAKA and loading patterns. [Driver](https://github.com/LukeUeda/Tessellate/blob/a554741c4c663a92da4b5c56c6af741b163271fe/ledDriver.cpp).
10. **Calibration:** Startup averages 1000 X samples; Y/Z subtract fixed 5.5 m/s². Eleven-point acceleration/radius array and `calibrationMode()` exist, but main-loop calibration call is commented out. [Sketch](https://github.com/LukeUeda/Tessellate/blob/a554741c4c663a92da4b5c56c6af741b163271fe/Tessellate.ino).
11. **RC/modes/failsafe:** Exact receiver pulse combination latches failsafe, channel-3 pulse at 1000 clears it; failsafe writes 2005 to motors. Signal-age timeout not found. [Receiver](https://github.com/LukeUeda/Tessellate/blob/a554741c4c663a92da4b5c56c6af741b163271fe/receiver.cpp).
12. **Unusual ideas:** Fast timer maintains heading/display independent of main-loop work; experimental multi-speed calibration array. [Sketch](https://github.com/LukeUeda/Tessellate/blob/a554741c4c663a92da4b5c56c6af741b163271fe/Tessellate.ino).
13. **Problems/results:** Author performance/test narrative not found; calibration-disabled code and nonstandard formula are inspection observations, not confirmed robot failures. [Sketch](https://github.com/LukeUeda/Tessellate/blob/a554741c4c663a92da4b5c56c6af741b163271fe/Tessellate.ino).
14. **License:** [MIT](https://github.com/LukeUeda/Tessellate/blob/a554741c4c663a92da4b5c56c6af741b163271fe/LICENSE).

<a id="p003"></a>

## P003. skysdottir/PotatoMelt

1. **Identity/activity:** [PotatoMelt](https://github.com/skysdottir/PotatoMelt), last pushed 2024-12-30. Author explicitly credits OpenMelt2; it has its own repository and implementation. [README][pm-readme]
2. **Source type/read:** Arduino C++: README, `spin_control.cpp`, `accel_handler.cpp`, `rc_handler.cpp`, `motor_driver.cpp`, `melty_config.h`; code inspected, no build/hardware validation. [Control][pm-spin]
3. **Robot context:** General drive controller; repository README does not specify a completed robot's weight or combat outcomes. [README][pm-readme]
4. **Hardware:** Author development setup: Adafruit ItsyBitsy 32u4 16 MHz/5 V, Adafruit LIS331 board, iBus receiver, Repeat Robotics dual AM32 ESC. DShot motor commands implemented. [README][pm-readme], [motor driver][pm-motor]
5. **Sensor/placement:** Single Y-axis acceleration; configured radius 2.91 cm, stationary zero offset, high-g LIS331 family. [Accelerometer][pm-accel], [configuration][pm-config]
6. **Math/rates:** Raw RPM = √(|g−offset|×89445/r_cm). Corrected RPM adds RPM×lookup correction; period is 60e6/RPM µs. Timer3 ISR runs nominally 2 kHz, slow parameter update delays 20 ms; optional enabled RPM PID has a 20 ms sample. [Accelerometer][pm-accel], [control][pm-spin]
7. **Drift:** Eight-point sorted RPM-to-correction table, linearly interpolated; driver steering biases estimated RPM. No external absolute reference found. [Accelerometer][pm-accel], [control][pm-spin]
8. **Translation:** Signed forward/back proportional command creates high/low DShot levels around base throttle, swapping between motors every half revolution; configurable translation trim. No arbitrary XY direction implemented in the inspected path. [Control][pm-spin]
9. **LED:** Heading arc width varies with measured RPM, clamped to 10–90% revolution; shimmer for configuration/save/low-battery indication. [Control][pm-spin]
10. **Calibration:** At rest, right stick back one second enters configuration and samples zero; save eight correction points at stable RPMs, then adjust LED offset and save to EEPROM. These are author instructions, not independently performed tests. [README][pm-readme], [accelerometer][pm-accel]
11. **RC/modes/failsafe:** iBus, tank mode, spin direction and correction-save channels; weighted channel checksum must change within 3000 ms. Watchdog and battery halt are configured. [RC][pm-rc], [configuration][pm-config]
12. **Unusual ideas:** Separates fast interrupt motor/LED work from slower calculations; PID intentionally uses uncorrected RPM so correction-table bugs affect heading instead of spin regulation. [Control][pm-spin]
13. **Problems/results:** Author says correction code is not yet trusted and flags stale-data assumptions for future omnidirectional control; non-AVR testing/persistence unsupported. No measured robot tracking result found. [Control][pm-spin], [configuration][pm-config]
14. **License:** [LGPL-2.1](https://github.com/skysdottir/PotatoMelt/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/LICENSE).

[pm-readme]: https://github.com/skysdottir/PotatoMelt/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/README.md
[pm-spin]: https://github.com/skysdottir/PotatoMelt/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/spin_control.cpp
[pm-accel]: https://github.com/skysdottir/PotatoMelt/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/accel_handler.cpp
[pm-config]: https://github.com/skysdottir/PotatoMelt/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/melty_config.h
[pm-rc]: https://github.com/skysdottir/PotatoMelt/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/rc_handler.cpp
[pm-motor]: https://github.com/skysdottir/PotatoMelt/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/motor_driver.cpp

<a id="p004"></a>

## P004. skysdottir/potatomelt-esp32

1. **Identity/activity:** [potatomelt-esp32](https://github.com/skysdottir/potatomelt-esp32), last pushed 2025-04-11; separate ESP32-S3 controller repository. [README][pe-readme]
2. **Source type/read:** Arduino C++: README, main sketch, `robot.cpp`, `controller.cpp`, `imu.cpp`, `accelerometer.cpp`, `melty_config.h`. [Sketch][pe-main]
3. **Robot context:** Config comments mention Ant-tato and Beetle-tato dimensions, not confirmed final robot weights/results. [Configuration][pe-config]
4. **Hardware:** ESP32-S3, Bluepad32 Xbox Bluetooth control, two LIS331-family accelerometers at I²C 0x18/0x19, two DShot300 motors and NeoPixel output. Specific ESC/motor models not found in inspected README/code. [Robot][pe-robot], [IMU][pe-imu], [configuration][pe-config]
5. **Sensor/placement:** Both sensors contribute zero-corrected XY acceleration magnitudes averaged together; configured hardware radius 5.13 cm. Z signal has a 0.5 exponential smoothing buffer for inversion detection, which is marked TODO for tank controls. [IMU][pe-imu], [configuration][pe-config]
6. **Math/rates:** RPM = √(|mean XY g|×89445/r_cm)×per-target correction. Period 60e6/RPM, with 400 RPM tracking floor; PID regulates target RPM. Main task delays 10 RTOS ticks, motor/LED task one tick; exact measured rates not found. [Sketch][pe-main], [IMU][pe-imu]
7. **Drift:** D-pad changes stored correction by ×1.005 or inverse at selected target RPM; turn stick biases virtual RPM. Absolute reference not found. [IMU][pe-imu], [sketch][pe-main]
8. **Translation:** Forward/back offset uses parabolic half-sine approximation −4p(p−1) each half-turn, alternately added/subtracted from motor commands. Left/right translation is plumbed through controller but explicitly unused. [Robot][pe-robot], [controller][pe-controller]
9. **LED:** Battery-dependent green/red heading arc, 10–90% width; ready/no-controller/stale state indications documented. [README][pe-readme], [sketch][pe-main]
10. **Calibration:** Startup 60-sample stationary offsets; D-pad spin/translation trims and target RPM selection use persistent storage interfaces. Stationary upright 1 g assumption is explicit. [IMU][pe-imu], [accelerometer][pe-accel], [controller][pe-controller]
11. **RC/modes/failsafe:** Right trigger requests spin, release returns tank; disconnected/stale inputs stop motors, 3000 ms freshness threshold. X toggles reverse request in controller, but no application of that field was found in inspected spin path. [Controller][pe-controller], [robot][pe-robot]
12. **Unusual ideas:** Separate CPU affinity for control and fast motor/LED tasks; shaped modulation and dual-sensor magnitude estimation. [Sketch][pe-main], [robot][pe-robot]
13. **Problems/results:** Author says only Xbox controller tested; disables new Bluetooth scanning to work around reported Bluepad32 timeout/crash. Low-battery state and configurable fast-loop delay remain TODOs in main sketch. [Controller][pe-controller], [sketch][pe-main]
14. **License:** [LGPL-2.1](https://github.com/skysdottir/potatomelt-esp32/blob/65881d9c3547ad4d1383086f021128e3632c0e42/LICENSE).

[pe-readme]: https://github.com/skysdottir/potatomelt-esp32/blob/65881d9c3547ad4d1383086f021128e3632c0e42/README.md
[pe-main]: https://github.com/skysdottir/potatomelt-esp32/blob/65881d9c3547ad4d1383086f021128e3632c0e42/potatomelt/potatomelt.ino
[pe-robot]: https://github.com/skysdottir/potatomelt-esp32/blob/65881d9c3547ad4d1383086f021128e3632c0e42/potatomelt/src/robot.cpp
[pe-controller]: https://github.com/skysdottir/potatomelt-esp32/blob/65881d9c3547ad4d1383086f021128e3632c0e42/potatomelt/src/controller.cpp
[pe-imu]: https://github.com/skysdottir/potatomelt-esp32/blob/65881d9c3547ad4d1383086f021128e3632c0e42/potatomelt/src/subsystems/imu.cpp
[pe-accel]: https://github.com/skysdottir/potatomelt-esp32/blob/65881d9c3547ad4d1383086f021128e3632c0e42/potatomelt/src/subsystems/accelerometer.cpp
[pe-config]: https://github.com/skysdottir/potatomelt-esp32/blob/65881d9c3547ad4d1383086f021128e3632c0e42/potatomelt/src/melty_config.h

<a id="p005"></a>

## P005. swallenhardware/MeltyHalo

1. **Identity/activity:** [MeltyHalo](https://github.com/swallenhardware/MeltyHalo), code for Halo by Spencer Allen and Pierce Jensen; last push 2018-10-06. [README][mh-readme]
2. **Source type/read:** Arduino C++ implementation: README, `haloBot.ino`, `meltybrain.ino`, `Accelerometer.ino`, `Comms.ino`, `Animations.ino`. [Main][mh-main]
3. **Robot context:** Beetleweight battlebot. README reports translation with beacon, accelerometer and hybrid sensing; this survey did not reproduce it. [README][mh-readme]
4. **Hardware:** Teensy-style watchdog/i2c_t3, H3LIS331DL, IR receiver/beacon, two brushless ESC PWM outputs at 250 Hz, five DotStar LEDs, 57,600-baud serial control. Exact board/ESC/motor models not found in inspected code. [Main][mh-main]
5. **Sensor/placement:** Z is radial acceleration, Y axial/flip measurement, X tangential unused; calibrated ring geometry implicit in fitted coefficients. Radius not declared in inspected firmware. [Accelerometer][mh-accel]
6. **Math/rates:** Sensor configured 1 kHz but read every 10 ms; period in µs/degree = 726/√((zRaw−225)/522). Trapezoidal integration at reads, linear period extrapolation between reads. [runAccelerometer][mh-accel]
7. **Drift:** Hybrid mode beacon corrects separate accelerometer trim with a 40° lead offset, gated by predicted 270° of rotation; accelerometer read failure switches to beacon-only. Beacon-only heading extrapolates between pulses. [Melty loop][mh-melty], [accelerometer][mh-accel]
8. **Translation:** Thumbstick `atan2` sets commanded direction; when magnitude exceeds threshold, a 180° sector alternates a fixed 20-point motor reduction relative to spin throttle. Flip input changes sign/mapping. [Comms][mh-comms], [melty loop][mh-melty]
9. **LED:** Five-pixel POV display includes HALO text and directional shapes indexed by estimated angle; inversion reverses LED ordering. [Animations][mh-animation]
10. **Calibration:** Hardcoded robot-specific period curve; optional serial acceleration/beacon-period telemetry present but commented. Manual trim support listed unfinished. [Accelerometer][mh-accel], [comms][mh-comms], [README][mh-readme]
11. **RC/modes/failsafe:** Custom framed serial packets, enable byte/dead-man, idle/tank/spin states, 1 s communications timeout and watchdog hardware enable cutoff. Battery-cutoff code is commented out. [Main][mh-main]
12. **Unusual ideas:** Beacon and accelerometer cross-checking; separate continuous acceleration angle plus externally corrected trim preserves integration continuity. [Accelerometer][mh-accel]
13. **Problems/results:** README explicitly leaves manual trim TODO; comments note blocking I²C and suggest sensor-data-ready interrupt; static animation rollover glitch acknowledged. [README][mh-readme], [accelerometer][mh-accel], [animations][mh-animation]
14. **License:** [MIT](https://github.com/swallenhardware/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/LICENSE).

[mh-readme]: https://github.com/swallenhardware/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/README.md
[mh-main]: https://github.com/swallenhardware/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/haloBot.ino
[mh-melty]: https://github.com/swallenhardware/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/meltybrain.ino
[mh-accel]: https://github.com/swallenhardware/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/Accelerometer.ino
[mh-comms]: https://github.com/swallenhardware/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/Comms.ino
[mh-animation]: https://github.com/swallenhardware/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/Animations.ino

<a id="p006"></a>

## P006. nothinglabs/openmelt2

1. **Identity/activity:** [Open Melt 2](https://github.com/nothinglabs/openmelt2), Rich Olson/Nothing Labs, last pushed 2025-02-03; complete Arduino recode of original AVR Open Melt. [README][om2-readme]
2. **Source type/read:** README, `spin_control.cpp`, `accel_handler.cpp`, `rc_handler.cpp`, `melty_config.h`; firmware plus schematic, reference platform and media are present in repository tree. [Control][om2-spin]
3. **Robot context:** One- or two-wheel robots; antweight reference platform. Author reports testing up to 3200 RPM and shows approximately 2300 RPM demo; not independently measured here. [README][om2-readme]
4. **Hardware:** Arduino Micro/ATmega32u4 5 V/16 MHz, H3LIS331 400 g, three RC PWM inputs, heading LED, one/two motors with MOSFET or suitable controller. ATmega328 explicitly unsupported for insufficient interrupt pins. Author reports SimonK Hobbypower 30 A working. [README][om2-readme]
5. **Sensor/placement:** Single radial acceleration channel, effective radius and stationary zero configurable; mounting is constrained by 400 g maximum, orientation error absorbed in effective radius. [README][om2-readme], [accelerometer][om2-accel]
6. **Math/rates:** RPM = √(|g−offset|×89445/effective_radius_cm), period 60,000/RPM ms. Control samples/calculates once per revolution, alternating start/midpoint update timing; author code comment estimates calculation around 1300 µs on ATmega32u4. [Control][om2-spin]
7. **Drift:** Steering modifies effective radius/rotation estimate; driver corrects heading LED drift. No absolute reference found. [Control][om2-spin]
8. **Translation:** Motor on-windows centered 180° apart; binary throttle controls fraction of revolution energized, with PWM modes also provided. Forward/reverse swaps windows; neutral alternates forward/reverse cycles. At low RPM both motors receive full-cycle power. [Control][om2-spin], [configuration][om2-config]
9. **LED:** One arc per revolution, adjustable offset and throttle-dependent 10–90% width; shimmer for configuration and low battery. [Control][om2-spin]
10. **Calibration:** Interactive effective radius and LED-offset adjustment, stationary zero sampling, EEPROM settings; precisely measured sensor radius unnecessary according to author. [Control][om2-spin], [README][om2-readme]
11. **RC/modes/failsafe:** Three-channel PWM RC; author documents zero-throttle boot verification, watchdog and receiver failsafe requirements. These are implemented intentions, not a safety certification. [README][om2-readme], [RC][om2-rc]
12. **Unusual ideas:** Same timing drives one/two-wheel layouts; alternating computation phase aims to cancel translation bias from ~1 ms sampling/math interruption. [Control][om2-spin]
13. **Problems/results:** Author describes LED occlusion, high-g offset tracking errors, motor-noise power resets requiring bus capacitor, platform interrupt limitations. Reported 3200 RPM is separate from code-derived capability. [README][om2-readme], [configuration][om2-config]
14. **License:** README declares Creative Commons Attribution-NonCommercial-ShareAlike 4.0. This includes a commercial-use restriction; no conventional software LICENSE file found at root. [README][om2-readme]

[om2-readme]: https://github.com/nothinglabs/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md
[om2-spin]: https://github.com/nothinglabs/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/spin_control.cpp
[om2-accel]: https://github.com/nothinglabs/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/accel_handler.cpp
[om2-rc]: https://github.com/nothinglabs/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/rc_handler.cpp
[om2-config]: https://github.com/nothinglabs/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/melty_config.h

<a id="p007"></a>

## P007. nothinglabs/openmelt

1. **Identity/activity:** [Rich Olson’s Open Melt](https://github.com/nothinglabs/openmelt); repository pushed 2023-12-13; documented builds 2009–2011.
2. **Source/read:** Native AVR C; [main.c](https://github.com/nothinglabs/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/main.c), README; no build/hardware validation.
3. **Robot:** Melty B/Beetle ancestry; one/two motors. Two-motor brushless operation untested. [Notes](https://github.com/nothinglabs/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/main.c)
4. **Hardware:** ATmega328/20 MHz Baby Orangutan B-328, MMA2301Eg/ADXL193, transistor drive or PWM ESC. [Hardware](https://github.com/nothinglabs/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/main.c)
5. **Placement:** Radial analog acceleration; configured effective radius 5.4 cm. [Constants](https://github.com/nothinglabs/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/main.c)
6. **Math/rates:** √(g×89445/r_cm); four ADC samples; 0.6/0.4 smoothing; twice-per-revolution calculations; 305 Hz ESC PWM. [Calculations](https://github.com/nothinglabs/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/main.c)
7. **Drift:** Tracking multiplier, steering and forward/back compensation; no absolute reference. [Calculations](https://github.com/nothinglabs/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/main.c)
8. **Translation:** Phase windows, throttle-controlled width; neutral alternates windows; full power below 500 RPM. [Timing](https://github.com/nothinglabs/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/main.c)
9. **LED:** Heading arc, status and maximum-RPM flash count. [Routines](https://github.com/nothinglabs/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/main.c)
10. **Calibration:** Stationary zero, tracking/heading adjustment, EEPROM save; calibration throttle 50%. [Configuration](https://github.com/nothinglabs/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/main.c)
11. **RC/failsafe:** Three PWM channels; range checks, four throttle confirmations, eleven-rotation freshness limit. [Safety](https://github.com/nothinglabs/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/main.c)
12. **Unusual:** Computation delay included and balanced across half-turns. [Timing](https://github.com/nothinglabs/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/main.c)
13. **Problems:** Reported unexplained glitches, voltage resets, balance/bounce sensitivity and poorer heavier-robot translation. [Notes](https://github.com/nothinglabs/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/main.c)
14. **License:** CC BY-NC-SA 3.0; commercial permission required. [Header](https://github.com/nothinglabs/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/main.c)

<a id="p008"></a>

## P008. nothinglabs/openmelt-ble

1. **Identity/activity:** [openmelt-ble](https://github.com/nothinglabs/openmelt-ble), Nothing Labs, NRF52/BLE translational-drift experiment; last pushed 2024-02-25. [Repository](https://github.com/nothinglabs/openmelt-ble)
2. **Source type/read:** Zephyr C implementation: `main.c`, `melty.c/h`, `accel.c`, `melty_ble.c`; tree includes Android controller sources. [Main](https://github.com/nothinglabs/openmelt-ble/blob/8fa91e2a5a4e968678f911d6683f88a3fdb55ebb/firmware/src/main.c)
3. **Robot context:** Generic one/two-motor controller; robot class, weight and verified physical performance not found in inspected files. [Control](https://github.com/nothinglabs/openmelt-ble/blob/8fa91e2a5a4e968678f911d6683f88a3fdb55ebb/firmware/src/melty.c)
4. **Hardware:** nRF52/Zephyr/Nordic Connect SDK 2.02 target, H3LIS331DL I²C, binary motor GPIOs 3/4 and heading LED13. Motor/driver models not found. [Main](https://github.com/nothinglabs/openmelt-ble/blob/8fa91e2a5a4e968678f911d6683f88a3fdb55ebb/firmware/src/main.c), [control](https://github.com/nothinglabs/openmelt-ble/blob/8fa91e2a5a4e968678f911d6683f88a3fdb55ebb/firmware/src/melty.c)
5. **Sensor/placement:** X-axis acceleration, 200 g range, radius received via BLE. Sensor explicitly configured 5 Hz, sample thread sleeps 30 ms; repeated polling is not a 33 Hz physical sensor output. [Sensor](https://github.com/nothinglabs/openmelt-ble/blob/8fa91e2a5a4e968678f911d6683f88a3fdb55ebb/firmware/src/accel.c), [main](https://github.com/nothinglabs/openmelt-ble/blob/8fa91e2a5a4e968678f911d6683f88a3fdb55ebb/firmware/src/main.c)
6. **Math/rates:** 0.5 exponential acceleration filter; RPM = √(g×89445/r_cm), revolution period bounded. Per-revolution loop recalculates parameters with 10 µs RTOS sleeps. [Sensor](https://github.com/nothinglabs/openmelt-ble/blob/8fa91e2a5a4e968678f911d6683f88a3fdb55ebb/firmware/src/accel.c), [control](https://github.com/nothinglabs/openmelt-ble/blob/8fa91e2a5a4e968678f911d6683f88a3fdb55ebb/firmware/src/melty.c)
7. **Drift:** Remote-set effective radius and LED offset; no absolute reference found. A startup `zero_g_accel` average is calculated but not subtracted in inspected RPM expression. [Control](https://github.com/nothinglabs/openmelt-ble/blob/8fa91e2a5a4e968678f911d6683f88a3fdb55ebb/firmware/src/melty.c)
8. **Translation:** Binary on-windows centered half-turn apart, throttle determines duty; forward/reverse swaps windows and idle alternates cycles. [do_melty](https://github.com/nothinglabs/openmelt-ble/blob/8fa91e2a5a4e968678f911d6683f88a3fdb55ebb/firmware/src/melty.c)
9. **LED:** Heading arc width 0.4×(1.1−throttle fraction); disconnected status flash duration depends on sensed acceleration. [Control](https://github.com/nothinglabs/openmelt-ble/blob/8fa91e2a5a4e968678f911d6683f88a3fdb55ebb/firmware/src/melty.c)
10. **Calibration:** Seven-byte BLE config carries radius (two-byte integer divided by 1000, stored in a centimetre-radius variable), LED offset, throttle, direction, heartbeat and reserved byte; exact UI calibration procedure not found. [BLE parser](https://github.com/nothinglabs/openmelt-ble/blob/8fa91e2a5a4e968678f911d6683f88a3fdb55ebb/firmware/src/melty_ble.c)
11. **RC/modes/failsafe:** BLE connection and initialized settings required; every 600 ms heartbeat must change and be in 10–13; failed condition leads to motors_safe after current rotation. [Main](https://github.com/nothinglabs/openmelt-ble/blob/8fa91e2a5a4e968678f911d6683f88a3fdb55ebb/firmware/src/main.c)
12. **Unusual ideas:** Android/BLE command path with rotation/battery notifications instead of hobby RC. [BLE service](https://github.com/nothinglabs/openmelt-ble/blob/8fa91e2a5a4e968678f911d6683f88a3fdb55ebb/firmware/src/melty_ble.c)
13. **Problems/results:** No explicit physical test narrative found; 5 Hz sensor configuration, unused zero average and threaded polling are source observations, not asserted test failures. [Sensor](https://github.com/nothinglabs/openmelt-ble/blob/8fa91e2a5a4e968678f911d6683f88a3fdb55ebb/firmware/src/accel.c)
14. **License:** Repository-wide license not found; main contains Nordic `LicenseRef-Nordic-5-Clause` header; third-party ST sensor driver carries its own terms. Do not infer one permissive license for the entire repository. [Main header](https://github.com/nothinglabs/openmelt-ble/blob/8fa91e2a5a4e968678f911d6683f88a3fdb55ebb/firmware/src/main.c), [sensor driver](https://github.com/nothinglabs/openmelt-ble/blob/8fa91e2a5a4e968678f911d6683f88a3fdb55ebb/firmware/src/h3lis331dl_reg.c)

<a id="p009"></a>

## P009. AlfredoSystems/SimpleMelt

1. **Identity/activity:** [SimpleMelt](https://github.com/AlfredoSystems/SimpleMelt), AlfredoSystems; last pushed 2026-10-14. Current code includes magnetometer fusion; original accelerometer-only V3 version is retained as tag 1.0.0. [README](https://github.com/AlfredoSystems/SimpleMelt/blob/41fb0fe5ce6664cb1e4d9da1856c095c56a147bb/README.md)
2. **Source type/read:** C++ math library `HeadingEstimator.h`, `MeltyDrive.h`, Rotini-V4 sketch/board class, README, changelog and detailed bench notes. [Estimator](https://github.com/AlfredoSystems/SimpleMelt/blob/41fb0fe5ce6664cb1e4d9da1856c095c56a147bb/src/HeadingEstimator.h), [drive](https://github.com/AlfredoSystems/SimpleMelt/blob/41fb0fe5ce6664cb1e4d9da1856c095c56a147bb/src/MeltyDrive.h)
3. **Robot context:** Rotini combat-robot controller; V4 shop-floor measurements and logs reported. Class/weight not found in inspected files. [Bench notes](https://github.com/AlfredoSystems/SimpleMelt/blob/41fb0fe5ce6664cb1e4d9da1856c095c56a147bb/examples/Rotini-V4/README.md)
4. **Hardware:** ESP32, Rotini V4 H3LIS331 accelerometer and MMC5983MA magnetometer over SPI/data-ready, CRSF RadioMaster Zorro, AM32 bidirectional DShot600, LEDs, battery monitor. V3 example uses OneShot125 without telemetry. [README](https://github.com/AlfredoSystems/SimpleMelt/blob/41fb0fe5ce6664cb1e4d9da1856c095c56a147bb/README.md), [board class](https://github.com/AlfredoSystems/SimpleMelt/blob/41fb0fe5ce6664cb1e4d9da1856c095c56a147bb/examples/Rotini-V4/RotiniV4.h)
5. **Sensor/placement:** Radial accel Z; initial effective radius 0.122 m. Magnetometer spin axis (−x+y)/√2, in-plane (x+y)/√2 and z. [Estimator](https://github.com/AlfredoSystems/SimpleMelt/blob/41fb0fe5ce6664cb1e4d9da1856c095c56a147bb/src/HeadingEstimator.h)
6. **Math/rates:** Signed √((a−offset)/radius), trapezoid integration; fresh `atan2(u,v)` compass fixes blended with gain 1/(1+1.5|ω|), field-magnitude gate and innovation weighting. Bench reports accel 415/s, magnetometer 618/s with SET/RESET, loop ~13.9 kHz. [Estimator](https://github.com/AlfredoSystems/SimpleMelt/blob/41fb0fe5ce6664cb1e4d9da1856c095c56a147bb/src/HeadingEstimator.h), [bench](https://github.com/AlfredoSystems/SimpleMelt/blob/41fb0fe5ce6664cb1e4d9da1856c095c56a147bb/examples/Rotini-V4/README.md)
7. **Drift:** Accepted compass fixes learn effective radius, magnetic circle centre and floor axial field; stationary/flat gating learns accelerometer offset. ESC RPM differentiates parked from turning. Persistence of learned calibration remains TODO. [Estimator](https://github.com/AlfredoSystems/SimpleMelt/blob/41fb0fe5ce6664cb1e4d9da1856c095c56a147bb/src/HeadingEstimator.h)
8. **Translation:** Forward/back magnitude and heading-trim steering; rectangular push/ease waveform, one side +3 parts and other −1 part, part=base×stick/2. Separate clockwise/counterclockwise LED offsets. [Drive](https://github.com/AlfredoSystems/SimpleMelt/blob/41fb0fe5ce6664cb1e4d9da1856c095c56a147bb/src/MeltyDrive.h)
9. **LED:** Quarter-turn heading arc, stop/disconnected blink patterns, separate status LED. [Drive](https://github.com/AlfredoSystems/SimpleMelt/blob/41fb0fe5ce6664cb1e4d9da1856c095c56a147bb/src/MeltyDrive.h)
10. **Calibration:** Online learners plus tunable initial radius, Earth-field magnitude, LED offsets and voltage/speed feedforward. Calibration flash save marked TODO; runtime tunables revert on boot. [Estimator](https://github.com/AlfredoSystems/SimpleMelt/blob/41fb0fe5ce6664cb1e4d9da1856c095c56a147bb/src/HeadingEstimator.h), [bench](https://github.com/AlfredoSystems/SimpleMelt/blob/41fb0fe5ce6664cb1e4d9da1856c095c56a147bb/examples/Rotini-V4/README.md)
11. **RC/modes/failsafe:** Stop/arcade/melty/disconnected outputs; CRSF integration. Direction reversal brakes before crossing zero and only changes estimator direction once sufficiently slow, with time bounds. [Drive](https://github.com/AlfredoSystems/SimpleMelt/blob/41fb0fe5ce6664cb1e4d9da1856c095c56a147bb/src/MeltyDrive.h), [sketch](https://github.com/AlfredoSystems/SimpleMelt/blob/41fb0fe5ce6664cb1e4d9da1856c095c56a147bb/examples/Rotini-V4/Rotini-V4.ino)
12. **Unusual ideas:** Body-speed/battery feedforward limits wheel slip; detailed telemetry, online calibration and ESC-informed stationary detection. [Drive](https://github.com/AlfredoSystems/SimpleMelt/blob/41fb0fe5ce6664cb1e4d9da1856c095c56a147bb/src/MeltyDrive.h)
13. **Problems/results:** Bench notes attribute magnetometer Z glitches to ESP-NOW emissions; no fix adopted. Balanced robot feedforward tests and reversal measured, but latest speed-target version model-only; hit/pin recovery untested. Symmetric waveform tried then removed because driving felt wrong; 3:1 waveform restored despite observed RPM rise/slip. [Bench notes](https://github.com/AlfredoSystems/SimpleMelt/blob/41fb0fe5ce6664cb1e4d9da1856c095c56a147bb/examples/Rotini-V4/README.md)
14. **License:** [MIT](https://github.com/AlfredoSystems/SimpleMelt/blob/41fb0fe5ce6664cb1e4d9da1856c095c56a147bb/LICENSE).

<a id="p010"></a>

## P010. AlfredoSystems/Rotini-Hardware

1. **Identity/activity:** [Rotini-Hardware](https://github.com/AlfredoSystems/Rotini-Hardware), AlfredoSystems; last pushed 2026-10-05. Separate hardware artifact repository from SimpleMelt. [README](https://github.com/AlfredoSystems/Rotini-Hardware/blob/393cb7acd2886332a8c6b518cfff1b86c2d9d3ba/README.md)
2. **Source type/read:** README and complete repository file inventory: KiCad schematic/PCB, manufacturing Gerbers/BOM/pick-and-place, V1–V3 schematic/PCB PDFs and docs. Circuit files were located, not electrically validated. [Hardware directory](https://github.com/AlfredoSystems/Rotini-Hardware/tree/393cb7acd2886332a8c6b518cfff1b86c2d9d3ba/Rotini-Hardware)
3. **Robot context:** All-in-one melty controller board; no robot weight or combat outcome found. [README](https://github.com/AlfredoSystems/Rotini-Hardware/blob/393cb7acd2886332a8c6b518cfff1b86c2d9d3ba/README.md)
4. **Hardware:** README describes ESP32-S2, H3LIS331DL 400 g, ESP8285/SX1280 ELRS3, SY8253ADC regulator rated 1 A at 3.3 V and maximum input 27 V, reverse-polarity protection, high-power LED drivers and USB-C. These are design claims, not independently measured ratings. [README](https://github.com/AlfredoSystems/Rotini-Hardware/blob/393cb7acd2886332a8c6b518cfff1b86c2d9d3ba/README.md)
5. **Sensor/placement:** Accelerometer rotated 45° according to author; board-level placement rather than a specific robot radius. [README](https://github.com/AlfredoSystems/Rotini-Hardware/blob/393cb7acd2886332a8c6b518cfff1b86c2d9d3ba/README.md)
6. **Math/rates:** No melty heading algorithm in inspected hardware assets; associated SimpleMelt firmware is a separate entry. [Repository](https://github.com/AlfredoSystems/Rotini-Hardware)
7. **Drift:** No standalone drift-correction implementation found in hardware repository.
8. **Translation:** No standalone motor modulation implementation found; board exposes controller hardware.
9. **LED:** High-power LED driving is an advertised board feature; heading timing supplied by firmware. [README](https://github.com/AlfredoSystems/Rotini-Hardware/blob/393cb7acd2886332a8c6b518cfff1b86c2d9d3ba/README.md)
10. **Calibration:** No robot-level calibration procedure found in inspected README; external documentation link supplied for pinout, flashing and first upload. [README](https://github.com/AlfredoSystems/Rotini-Hardware/blob/393cb7acd2886332a8c6b518cfff1b86c2d9d3ba/README.md)
11. **RC/modes/failsafe:** ELRS receiver/transceiver hardware documented; drive modes and failsafe behavior belong to selected firmware, not established by board files alone. [README](https://github.com/AlfredoSystems/Rotini-Hardware/blob/393cb7acd2886332a8c6b518cfff1b86c2d9d3ba/README.md)
12. **Unusual ideas:** Integrated receiver, MCU, high-g sensing and power/LED stages; manufacturing outputs support third-party assembly. [README](https://github.com/AlfredoSystems/Rotini-Hardware/blob/393cb7acd2886332a8c6b518cfff1b86c2d9d3ba/README.md)
13. **Problems/results:** Author notes JLCPCB lacks the high-g accelerometer in its ordinary parts library, requiring global sourcing; GPIO TVS protection listed as possible V4 feature, not present by implication. [README](https://github.com/AlfredoSystems/Rotini-Hardware/blob/393cb7acd2886332a8c6b518cfff1b86c2d9d3ba/README.md)
14. **License:** [MIT](https://github.com/AlfredoSystems/Rotini-Hardware/blob/393cb7acd2886332a8c6b518cfff1b86c2d9d3ba/LICENSE); verify third-party component assets separately.

<a id="p011"></a>

## P011. GHF/gyroking

1. **Identity/activity:** [gyroking](https://github.com/GHF/gyroking), Xo Wang/Aaron Fan; last pushed 2013-03-10.
2. **Source/read:** C++/ChibiOS control, I/O, main and headers; no compilation/hardware validation. [Main](https://github.com/GHF/gyroking/blob/061499f1712dd6591c0326473e1a67c21ff2f774/src/main.cpp)
3. **Robot:** Tortilla dual-brushless spinner; weight/results not found. [Readme](https://github.com/GHF/gyroking/blob/061499f1712dd6591c0326473e1a67c21ff2f774/readme.txt)
4. **Hardware:** STM32, A4960 drivers, ADS1259 ADC, 20 kHz PWM, Bluetooth-labeled serial. [Main](https://github.com/GHF/gyroking/blob/061499f1712dd6591c0326473e1a67c21ff2f774/src/main.cpp)
5. **Placement:** Analog gyro; part and placement not found. [Control](https://github.com/GHF/gyroking/blob/061499f1712dd6591c0326473e1a67c21ff2f774/src/Tortilla_control.cpp)
6. **Math/rates:** 64,000°/s ADC scaling; nominal 1 kHz, 0.1-new EMA, trapezoid integration. [Control](https://github.com/GHF/gyroking/blob/061499f1712dd6591c0326473e1a67c21ff2f774/src/Tortilla_control.cpp)
7. **Drift:** Startup gyro bias plus remote trim; absolute reference not found. [Control](https://github.com/GHF/gyroking/blob/061499f1712dd6591c0326473e1a67c21ff2f774/src/Tortilla_control.cpp)
8. **Translation:** XY angle/magnitude; narrow opposed pulses alternate full PWM and throttle/30, with rate-dependent phase advance. [Control](https://github.com/GHF/gyroking/blob/061499f1712dd6591c0326473e1a67c21ff2f774/src/Tortilla_control.cpp)
9. **LED:** Blue reference; yellow movement arc or threefold pattern. [Control](https://github.com/GHF/gyroking/blob/061499f1712dd6591c0326473e1a67c21ff2f774/src/Tortilla_control.cpp)
10. **Calibration:** Six-second bias sampling discards first second; adds 1100 counts. [Control](https://github.com/GHF/gyroking/blob/061499f1712dd6591c0326473e1a67c21ff2f774/src/Tortilla_control.cpp)
11. **RC/failsafe:** Serial movement/stop/trim; fifteen 100 ms timeouts zero throttle. [I/O](https://github.com/GHF/gyroking/blob/061499f1712dd6591c0326473e1a67c21ff2f774/src/Tortilla_io.cpp)
12. **Unusual:** Custom motor/ADC electronics and narrow slip pulses. [Control](https://github.com/GHF/gyroking/blob/061499f1712dd6591c0326473e1a67c21ff2f774/src/Tortilla_control.cpp)
13. **Problems/results:** No substantial author test/failure narrative found. [Readme](https://github.com/GHF/gyroking/blob/061499f1712dd6591c0326473e1a67c21ff2f774/readme.txt)
14. **License:** Permissive source grant with name-use advertising restriction; read exact header. [License](https://github.com/GHF/gyroking/blob/061499f1712dd6591c0326473e1a67c21ff2f774/src/Tortilla_control.cpp)

<a id="p012"></a>

## P012. jackmaxg/melty

1. **Identity/activity:** [jackmaxg/melty](https://github.com/jackmaxg/melty); last pushed 2018-07-13.
2. **Source/read:** Arduino sketch and identical V2 copy; no build/hardware validation. [Sketch](https://github.com/jackmaxg/melty/blob/f30421f2c5ea20eca774ef06a25f2da0a51a12df/meltymain/meltymain.ino)
3. **Robot:** Custom shell/wheel robot; weight/results not found. [Repository](https://github.com/jackmaxg/melty)
4. **Hardware:** Kinetis/Teensy-style timers, analog accelerometer, one OneShot125 output, eight RC channels. [Sketch](https://github.com/jackmaxg/melty/blob/f30421f2c5ea20eca774ef06a25f2da0a51a12df/meltymain/meltymain.ino)
5. **Placement:** Physical radius unspecified; ADC centre 795.2, scale 85. [Sketch](https://github.com/jackmaxg/melty/blob/f30421f2c5ea20eca774ef06a25f2da0a51a12df/meltymain/meltymain.ino)
6. **Math/rates:** ω=√(|ADC−centre|×85)+offset+trim; elapsed-time integration; OneShot capped 3 kHz. [Sketch](https://github.com/jackmaxg/melty/blob/f30421f2c5ea20eca774ef06a25f2da0a51a12df/meltymain/meltymain.ino)
7. **Drift:** Additive trims and driver yaw-rate bias; no active beacon reference. [Sketch](https://github.com/jackmaxg/melty/blob/f30421f2c5ea20eca774ef06a25f2da0a51a12df/meltymain/meltymain.ino)
8. **Translation:** Sinusoidal XY modulation, 30° phase shift, output clamped 0–1. [Sketch](https://github.com/jackmaxg/melty/blob/f30421f2c5ea20eca774ef06a25f2da0a51a12df/meltymain/meltymain.ino)
9. **LED:** Configured 30° heading arcs and mode indicators; observed accuracy unknown. [Sketch](https://github.com/jackmaxg/melty/blob/f30421f2c5ea20eca774ef06a25f2da0a51a12df/meltymain/meltymain.ino)
10. **Calibration:** Hardcoded constants, ADC/RPM pairs, RC-controlled sample averaging. [Sketch](https://github.com/jackmaxg/melty/blob/f30421f2c5ea20eca774ef06a25f2da0a51a12df/meltymain/meltymain.ino)
11. **RC/failsafe:** Idle/balance/combat; stale PWM clears after approximately 50 ms. [Sketch](https://github.com/jackmaxg/melty/blob/f30421f2c5ea20eca774ef06a25f2da0a51a12df/meltymain/meltymain.ino)
12. **Unusual:** Cell balancing; V2/V3 board and IR-beacon assets. [Repository](https://github.com/jackmaxg/melty)
13. **Problems:** Author notes unexplained timer divisor and interrupt-race workaround; inversion logic commented. [Sketch](https://github.com/jackmaxg/melty/blob/f30421f2c5ea20eca774ef06a25f2da0a51a12df/meltymain/meltymain.ino)
14. **License:** Not found in inspected root/firmware. [Repository](https://github.com/jackmaxg/melty)

<a id="p013"></a>

## P013. AmbientChaos/Spin-Doctor---Meltybrain-Software

1. **Identity/activity:** [Spin Doctor original](https://github.com/AmbientChaos/Spin-Doctor---Meltybrain-Software), AmbientChaos; last pushed 2019-07-01. [README](https://github.com/AmbientChaos/Spin-Doctor---Meltybrain-Software/blob/1bf9025ef2a486f00524d5effa56a9b71a3d92da/README.md)
2. **Source type/read:** Arduino C++: `SpinDoctor.ino`, `Accelerometer.ino`, `Melty.ino`, `Calibration.ino`, `Receiver.ino`, `Watchdog.ino`, README. [Main](https://github.com/AmbientChaos/Spin-Doctor---Meltybrain-Software/blob/1bf9025ef2a486f00524d5effa56a9b71a3d92da/SpinDoctor.ino)
3. **Robot context:** Translational-drift platform; class/weight not found. Author says accelerometer, receiver and DShot tested but main program untested. [README](https://github.com/AmbientChaos/Spin-Doctor---Meltybrain-Software/blob/1bf9025ef2a486f00524d5effa56a9b71a3d92da/README.md)
4. **Hardware:** Teensy 3.2, SparkFun H3LIS331DL, six-channel CPPM, DShot600 ESCs, 750 KV brushless motors. [README](https://github.com/AmbientChaos/Spin-Doctor---Meltybrain-Software/blob/1bf9025ef2a486f00524d5effa56a9b71a3d92da/README.md)
5. **Sensor/placement:** Radial Z for rate; filtered X intended for inverted orientation. Physical radius not found because calibrated curve maps acceleration directly to degree period. [Accelerometer](https://github.com/AmbientChaos/Spin-Doctor---Meltybrain-Software/blob/1bf9025ef2a486f00524d5effa56a9b71a3d92da/Accelerometer.ino)
6. **Math/rates:** 1 kHz data-ready sensor configuration, five-point triangular Z filter and 100-point orientation average. `period=A×exp(z/B)+C`; trapezoid angle integration and extrapolation between samples. Motor writes limited 4 kHz per motor. [Sensor](https://github.com/AmbientChaos/Spin-Doctor---Meltybrain-Software/blob/1bf9025ef2a486f00524d5effa56a9b71a3d92da/Accelerometer.ino), [melty](https://github.com/AmbientChaos/Spin-Doctor---Meltybrain-Software/blob/1bf9025ef2a486f00524d5effa56a9b71a3d92da/Melty.ino)
7. **Drift:** Rudder shifts integrated heading; no absolute sensor found. Curve calibration intended to reduce rate error. [Melty](https://github.com/AmbientChaos/Spin-Doctor---Meltybrain-Software/blob/1bf9025ef2a486f00524d5effa56a9b71a3d92da/Melty.ino)
8. **Translation:** XY `hypot`/`atan2` direction; above magnitude threshold, 180° sectors swap fixed ±200 motor command offsets. [meltMove](https://github.com/AmbientChaos/Spin-Doctor---Meltybrain-Software/blob/1bf9025ef2a486f00524d5effa56a9b71a3d92da/Melty.ino)
9. **LED:** Green narrow forward-reference arc and red commanded-direction arc; idle/calibration status patterns. [Melty](https://github.com/AmbientChaos/Spin-Doctor---Meltybrain-Software/blob/1bf9025ef2a486f00524d5effa56a9b71a3d92da/Melty.ino)
10. **Calibration:** Menu for throttle saturation, 20 manual stationary-strobe calibration points/regression, and light direction; EEPROM save on exiting. These are provided routines/instructions, not a performed calibration here. [README](https://github.com/AmbientChaos/Spin-Doctor---Meltybrain-Software/blob/1bf9025ef2a486f00524d5effa56a9b71a3d92da/README.md), [calibration implementation](https://github.com/AmbientChaos/Spin-Doctor---Meltybrain-Software/blob/1bf9025ef2a486f00524d5effa56a9b71a3d92da/Calibration.ino)
11. **RC/modes/failsafe:** CPPM gear/flap mode switches; safe startup, idle, drive/melty, calibration and max-spin; watchdog. Max-spin intentionally bypasses accelerometer and commands maximum motor power. [Main](https://github.com/AmbientChaos/Spin-Doctor---Meltybrain-Software/blob/1bf9025ef2a486f00524d5effa56a9b71a3d92da/SpinDoctor.ino), [README](https://github.com/AmbientChaos/Spin-Doctor---Meltybrain-Software/blob/1bf9025ef2a486f00524d5effa56a9b71a3d92da/README.md)
12. **Unusual ideas:** Multi-point fitted period curve, data-ready interrupt, separate reference/movement LEDs and inverted drive logic. [Sensor](https://github.com/AmbientChaos/Spin-Doctor---Meltybrain-Software/blob/1bf9025ef2a486f00524d5effa56a9b71a3d92da/Accelerometer.ino)
13. **Problems/results:** Author explicitly warns main program is untested; component functionality is reported separately. No complete robot demonstration or heading-accuracy measurement found. [README](https://github.com/AmbientChaos/Spin-Doctor---Meltybrain-Software/blob/1bf9025ef2a486f00524d5effa56a9b71a3d92da/README.md)
14. **License:** [GPL-3.0](https://github.com/AmbientChaos/Spin-Doctor---Meltybrain-Software/blob/1bf9025ef2a486f00524d5effa56a9b71a3d92da/LICENSE).

<a id="p014"></a>

## P014. AmbientChaos/Spin-Doctor-V2

1. **Identity/activity:** [Spin Doctor V2](https://github.com/AmbientChaos/Spin-Doctor-V2), last push 2020-08-28; separate ESC-telemetry-only experiment. [README](https://github.com/AmbientChaos/Spin-Doctor-V2/blob/3cbab8af342c968bbac6675bf68d4acf4e922bd1/README.md)
2. **Source type/read:** Arduino C++: `SpinDoctorV2.ino`, `Melty.h`, `Telemetry.h`, `Receiver.h`, README. [Main](https://github.com/AmbientChaos/Spin-Doctor-V2/blob/3cbab8af342c968bbac6675bf68d4acf4e922bd1/SpinDoctorV2.ino)
3. **Robot context:** Sensorless translational drift; author reports receiver/ESC components tested, melty algorithms potentially nonfunctional. Weight/class not found. [README](https://github.com/AmbientChaos/Spin-Doctor-V2/blob/3cbab8af342c968bbac6675bf68d4acf4e922bd1/README.md)
4. **Hardware:** Teensy 3.2, six-channel CPPM, telemetry-capable DShot600 ESCs, 750 KV motors, 5 V converter. [README](https://github.com/AmbientChaos/Spin-Doctor-V2/blob/3cbab8af342c968bbac6675bf68d4acf4e922bd1/README.md)
5. **Heading sensor/placement:** ESC UART electrical RPM, not body accelerometer or absolute orientation; 41 mm wheel, 60 mm wheel-circle diameter, 14 motor poles. [Telemetry](https://github.com/AmbientChaos/Spin-Doctor-V2/blob/3cbab8af342c968bbac6675bf68d4acf4e922bd1/Telemetry.h)
6. **Math/rates:** eRPM×100/(poles/2), wheel/body diameter ratio, then degree period ≈166668/bodyRPM plus offset. Trapezoid angle integration on new telemetry; between-sample extrapolation block commented. Requests telemetry roughly every 900 µs, motor commands max4 kHz. [Telemetry](https://github.com/AmbientChaos/Spin-Doctor-V2/blob/3cbab8af342c968bbac6675bf68d4acf4e922bd1/Telemetry.h), [melty](https://github.com/AmbientChaos/Spin-Doctor-V2/blob/3cbab8af342c968bbac6675bf68d4acf4e922bd1/Melty.h)
7. **Drift:** Manual rudder angle trim and period-offset calibration; wheel slip has no independently measured body reference in this path. [Melty](https://github.com/AmbientChaos/Spin-Doctor-V2/blob/3cbab8af342c968bbac6675bf68d4acf4e922bd1/Melty.h)
8. **Translation:** XY direction and magnitude threshold; rectangular half-turn switching between 100% and 80% current throttle on opposite motors. [meltMove](https://github.com/AmbientChaos/Spin-Doctor-V2/blob/3cbab8af342c968bbac6675bf68d4acf4e922bd1/Melty.h)
9. **LED:** Green reference, red movement arc; calibration/max-spin status. [Melty](https://github.com/AmbientChaos/Spin-Doctor-V2/blob/3cbab8af342c968bbac6675bf68d4acf4e922bd1/Melty.h)
10. **Calibration:** Rudder increments period offset, saved to EEPROM with sentinel; elevator resets. [Telemetry](https://github.com/AmbientChaos/Spin-Doctor-V2/blob/3cbab8af342c968bbac6675bf68d4acf4e922bd1/Telemetry.h), [state machine](https://github.com/AmbientChaos/Spin-Doctor-V2/blob/3cbab8af342c968bbac6675bf68d4acf4e922bd1/SpinDoctorV2.ino)
11. **RC/modes/failsafe:** CPPM safe/drive/juke/melty/max-spin/calibrate; startup must enter drive with low throttle, signal loss enters idle. [Main](https://github.com/AmbientChaos/Spin-Doctor-V2/blob/3cbab8af342c968bbac6675bf68d4acf4e922bd1/SpinDoctorV2.ino)
12. **Unusual ideas:** No high-g sensor; attempts all heading estimation from ESC data, with juke and inversion-switch logic. [README](https://github.com/AmbientChaos/Spin-Doctor-V2/blob/3cbab8af342c968bbac6675bf68d4acf4e922bd1/README.md)
13. **Problems/results:** CRC8 validation explicitly disabled because mostly failed with zero CRC; melty algorithm functionality unconfirmed. Source contains experimental code, not verified autonomous heading. [Telemetry](https://github.com/AmbientChaos/Spin-Doctor-V2/blob/3cbab8af342c968bbac6675bf68d4acf4e922bd1/Telemetry.h), [README](https://github.com/AmbientChaos/Spin-Doctor-V2/blob/3cbab8af342c968bbac6675bf68d4acf4e922bd1/README.md)
14. **License:** Source headers declare GPLv3-or-later even though no root LICENSE appeared in tree. [Melty header](https://github.com/AmbientChaos/Spin-Doctor-V2/blob/3cbab8af342c968bbac6675bf68d4acf4e922bd1/Melty.h)

<a id="p015"></a>

## P015. Blackcatmaxy/Meltybrain

1. **Identity/activity:** [Meltybrain](https://github.com/Blackcatmaxy/Meltybrain), Daniel Bereza/Blackcatmaxy; ESP32-S3 custom board; last pushed 2025-04-14. [README](https://github.com/Blackcatmaxy/Meltybrain/blob/e1bbca62ad1e53fed6f0ace6bf79516f43b5b381/readme.md), [BLE authorship](https://github.com/Blackcatmaxy/Meltybrain/blob/e1bbca62ad1e53fed6f0ace6bf79516f43b5b381/src/bluetooth.hpp)
2. **Source type/read:** PlatformIO Arduino C++: main, `imu.hpp`, `imus.hpp`, `rotation.hpp`, `motors.hpp`, `bluetooth.hpp`, `defines.hpp`. [Main](https://github.com/Blackcatmaxy/Meltybrain/blob/e1bbca62ad1e53fed6f0ace6bf79516f43b5b381/src/main.cpp)
3. **Robot context:** Custom ESP32-S3 melty; class/weight and verified results not found. [README](https://github.com/Blackcatmaxy/Meltybrain/blob/e1bbca62ad1e53fed6f0ace6bf79516f43b5b381/readme.md)
4. **Hardware:** Two SPI LIS331-compatible 400 g sensors, two motor outputs, top/bottom LEDs, BLE HID gamepad (Stadia mapping tested per comment). Exact ESC/motor models not found. [Defines](https://github.com/Blackcatmaxy/Meltybrain/blob/e1bbca62ad1e53fed6f0ace6bf79516f43b5b381/src/defines.hpp), [BLE](https://github.com/Blackcatmaxy/Meltybrain/blob/e1bbca62ad1e53fed6f0ace6bf79516f43b5b381/src/bluetooth.hpp)
5. **Sensor/placement:** X/Y projection corrected by cos-like factors 0.63038/0.77629, averaged per sensor then across two sensors; configured effective radius 0.582 cm. [IMU](https://github.com/Blackcatmaxy/Meltybrain/blob/e1bbca62ad1e53fed6f0ace6bf79516f43b5b381/src/imu.hpp), [dual sensors](https://github.com/Blackcatmaxy/Meltybrain/blob/e1bbca62ad1e53fed6f0ace6bf79516f43b5b381/src/imus.hpp)
6. **Math/rates:** RPM=√(|mean_g×89445|/radius_cm); rotation interval 60,000/RPM ms. Main samples RPM every 51 control-loop passes; no fixed sensor/control rate found. [Main](https://github.com/Blackcatmaxy/Meltybrain/blob/e1bbca62ad1e53fed6f0ace6bf79516f43b5b381/src/main.cpp), [sensors](https://github.com/Blackcatmaxy/Meltybrain/blob/e1bbca62ad1e53fed6f0ace6bf79516f43b5b381/src/imus.hpp)
7. **Drift:** Side stick modifies estimated rotation interval; cycle overflow subtracted next rotation. No absolute reference found. [Rotation](https://github.com/Blackcatmaxy/Meltybrain/blob/e1bbca62ad1e53fed6f0ace6bf79516f43b5b381/src/rotation.hpp)
8. **Translation:** Forward/back scales reduced motor power during half-turn windows; reversing swaps motors. Author flags motor2 window never starts correctly, so do not describe intended symmetry as confirmed behavior. [Rotation](https://github.com/Blackcatmaxy/Meltybrain/blob/e1bbca62ad1e53fed6f0ace6bf79516f43b5b381/src/rotation.hpp)
9. **LED:** Heading window one-eighth turn centred halfway through virtual rotation; gamepad LED button also writes outputs. [Rotation](https://github.com/Blackcatmaxy/Meltybrain/blob/e1bbca62ad1e53fed6f0ace6bf79516f43b5b381/src/rotation.hpp), [BLE](https://github.com/Blackcatmaxy/Meltybrain/blob/e1bbca62ad1e53fed6f0ace6bf79516f43b5b381/src/bluetooth.hpp)
10. **Calibration:** 1000 stationary X/Y samples per sensor; hardcoded projection/radius; persistence code commented. [IMU](https://github.com/Blackcatmaxy/Meltybrain/blob/e1bbca62ad1e53fed6f0ace6bf79516f43b5b381/src/imu.hpp), [main](https://github.com/Blackcatmaxy/Meltybrain/blob/e1bbca62ad1e53fed6f0ace6bf79516f43b5b381/src/main.cpp)
11. **RC/modes/failsafe:** BLE HID controller, right-trigger spin otherwise tank; disconnect clears throttle values. Optional 10 s watchdog code is disabled in defines. [BLE](https://github.com/Blackcatmaxy/Meltybrain/blob/e1bbca62ad1e53fed6f0ace6bf79516f43b5b381/src/bluetooth.hpp), [defines](https://github.com/Blackcatmaxy/Meltybrain/blob/e1bbca62ad1e53fed6f0ace6bf79516f43b5b381/src/defines.hpp)
12. **Unusual ideas:** Dedicated BLE and control tasks on separate cores; dual accelerometers with mounting-angle projection. [Main](https://github.com/Blackcatmaxy/Meltybrain/blob/e1bbca62ad1e53fed6f0ace6bf79516f43b5b381/src/main.cpp)
13. **Problems/results:** Author comments note PCB pin-label mistakes, unresolved motor2 timing and overflow-underflow risk. Inspection also finds local RPM assigned only on some loop passes; no build/test was run to establish effect. [Defines](https://github.com/Blackcatmaxy/Meltybrain/blob/e1bbca62ad1e53fed6f0ace6bf79516f43b5b381/src/defines.hpp), [rotation](https://github.com/Blackcatmaxy/Meltybrain/blob/e1bbca62ad1e53fed6f0ace6bf79516f43b5b381/src/rotation.hpp), [main](https://github.com/Blackcatmaxy/Meltybrain/blob/e1bbca62ad1e53fed6f0ace6bf79516f43b5b381/src/main.cpp)
14. **License:** [GPL-3.0](https://github.com/Blackcatmaxy/Meltybrain/blob/e1bbca62ad1e53fed6f0ace6bf79516f43b5b381/LICENSE).

<a id="p016"></a>

## P016. Mew463/Oreo

1. **Identity/activity:** [Oreo](https://github.com/Mew463/Oreo), Mew463, last pushed 2025-11-21; codebase for a meltybrain. [Repository](https://github.com/Mew463/Oreo)
2. **Source type/read:** ESP32 PlatformIO C++: main, melty timing class, phototransistor orientation class, drive motors, platformio.ini; tree includes IR beacon and laptop controller sources. [Main](https://github.com/Mew463/Oreo/blob/fff232c423e8b3225261daab77ff7cfec03477ce/Robot%20Code/src/main.cpp)
3. **Robot context:** Oreo; optional hockey-puck configuration in source, no confirmed weight/competition result found. [Main](https://github.com/Mew463/Oreo/blob/fff232c423e8b3225261daab77ff7cfec03477ce/Robot%20Code/src/main.cpp)
4. **Hardware:** ESP32 Arduino, two DShotRMT motor channels, top/bottom IR receivers and phototransistors, FastLED LEDs, BLE UART laptop control, SPIFFS settings. Exact motors/ESC/IR module models not found. [Main](https://github.com/Mew463/Oreo/blob/fff232c423e8b3225261daab77ff7cfec03477ce/Robot%20Code/src/main.cpp), [motor driver](https://github.com/Mew463/Oreo/blob/fff232c423e8b3225261daab77ff7cfec03477ce/Robot%20Code/lib/Drive_Motors/Drive_Motors.cpp)
5. **Sensor/placement:** External IR beacon with selected upper/lower receiver; light-intensity sensors choose inversion. Accelerometer test exists in archive, not used in read melty timing implementation. [Melty](https://github.com/Mew463/Oreo/blob/fff232c423e8b3225261daab77ff7cfec03477ce/Robot%20Code/lib/Melty/melty.cpp), [orientation](https://github.com/Mew463/Oreo/blob/fff232c423e8b3225261daab77ff7cfec03477ce/Robot%20Code/lib/Photo_Transistors/Photo_Transistors.h)
6. **Math/rates:** Beacon-envelope duration sanity filter, five-period buffer minimum estimates rotation period/RPM; timestamps envelope centre for phase. Loop-driven acquisition; no measured control rate found. [Melty](https://github.com/Mew463/Oreo/blob/fff232c423e8b3225261daab77ff7cfec03477ce/Robot%20Code/lib/Melty/melty.cpp)
7. **Drift:** Re-observed beacon anchors each set of future timing windows; buffered period tolerates missed detections. Absolute arena-compass calibration not found. [computeTimings](https://github.com/Mew463/Oreo/blob/fff232c423e8b3225261daab77ff7cfec03477ce/Robot%20Code/lib/Melty/melty.cpp)
8. **Translation:** Signed triangular pulse envelopes on selected fraction of revolution, inverse pulse half-turn later; eight discrete 45° directions from laptop packet; opposite motor offsets around base spin power. [Melty](https://github.com/Mew463/Oreo/blob/fff232c423e8b3225261daab77ff7cfec03477ce/Robot%20Code/lib/Melty/melty.cpp), [main](https://github.com/Mew463/Oreo/blob/fff232c423e8b3225261daab77ff7cfec03477ce/Robot%20Code/src/main.cpp)
9. **LED:** Top/bottom high-power red beacon-seen indication plus mode/status colours; no independent heading-arc accuracy results found. [Main](https://github.com/Mew463/Oreo/blob/fff232c423e8b3225261daab77ff7cfec03477ce/Robot%20Code/src/main.cpp)
10. **Calibration:** BLE commands adjust base/translation/rotation-window percentage and save SPIFFS/database; boost input. [Main](https://github.com/Mew463/Oreo/blob/fff232c423e8b3225261daab77ff7cfec03477ce/Robot%20Code/src/main.cpp)
11. **RC/modes/failsafe:** BLE laptop packet selects melty/tank/idle; disconnected branch commands zero motors. Fresh-command timeout not established by inspected main file. [Main](https://github.com/Mew463/Oreo/blob/fff232c423e8b3225261daab77ff7cfec03477ce/Robot%20Code/src/main.cpp)
12. **Unusual ideas:** Phototransistor-based inversion, alternating future timing buffers, triangular translation waveform and laptop-side controls. [Melty](https://github.com/Mew463/Oreo/blob/fff232c423e8b3225261daab77ff7cfec03477ce/Robot%20Code/lib/Melty/melty.cpp), [orientation](https://github.com/Mew463/Oreo/blob/fff232c423e8b3225261daab77ff7cfec03477ce/Robot%20Code/lib/Photo_Transistors/Photo_Transistors.h)
13. **Problems/results:** Code notes RMT initialization-order sensitivity; archived ADXL tests are development assets, not evidence of integrated accelerometer navigation. Measured robot performance not found. [Main](https://github.com/Mew463/Oreo/blob/fff232c423e8b3225261daab77ff7cfec03477ce/Robot%20Code/src/main.cpp)
14. **License:** Repository-wide license not found in inspected tree; included libraries have separate terms. [Repository](https://github.com/Mew463/Oreo)

<a id="p017"></a>

## P017. PsychoticRobotics/Project-Meltybrain

1. **Identity/activity:** [Project-Meltybrain](https://github.com/PsychoticRobotics/Project-Meltybrain), PsychoticRobotics; repository description identifies Master Wu, 3 lb Carnegie Mellon Combat Robotics melty; last push 2026-10-30. [Repository](https://github.com/PsychoticRobotics/Project-Meltybrain)
2. **Source type/read:** C++/PlatformIO: README, main, Robot, Accelerometer, IR, Motor, Receiver and headers. [Main](https://github.com/PsychoticRobotics/Project-Meltybrain/blob/a089aafa578768386fcce71b592ad79e2035c38c/src/main.cpp)
3. **Robot context:** Master Wu; [CAD companion](https://github.com/PsychoticRobotics/Project-Meltybrain-CAD) is same project, not counted as another robot. Completed translational performance not found.
4. **Hardware:** Teensy-oriented platform, LIS331 400 g sensors via selectable SPI/I²C, CRSF receiver, two motor outputs, SD logging provision. Main initializes only one sensor at CS10 or 0x18 despite dual-manager support. [Main](https://github.com/PsychoticRobotics/Project-Meltybrain/blob/a089aafa578768386fcce71b592ad79e2035c38c/src/main.cpp), [sensor](https://github.com/PsychoticRobotics/Project-Meltybrain/blob/a089aafa578768386fcce71b592ad79e2035c38c/src/Accelerometer.cpp)
5. **Sensor/placement:** Manager averages one/two sensors then rotates X/Z by 45° into normal/tangential/up; Robot effective radius 0.033 m. [Sensor](https://github.com/PsychoticRobotics/Project-Meltybrain/blob/a089aafa578768386fcce71b592ad79e2035c38c/src/Accelerometer.cpp), [header](https://github.com/PsychoticRobotics/Project-Meltybrain/blob/a089aafa578768386fcce71b592ad79e2035c38c/include/Robot.h)
6. **Math/rates:** Intended √(normal_accel/radius) integration; sensor setting1 kHz. Current `updateTheta` shadows `filteredAcceleration` with a self-referential local, uses 0.9/0.01 coefficients and directly multiplies by µs dt. These are unvalidated source issues, not established physical estimator behavior. [Robot](https://github.com/PsychoticRobotics/Project-Meltybrain/blob/a089aafa578768386fcce71b592ad79e2035c38c/src/Robot.cpp)
7. **Drift:** No active absolute correction found. Entire IR correction file is commented experimental code. [IR](https://github.com/PsychoticRobotics/Project-Meltybrain/blob/a089aafa578768386fcce71b592ad79e2035c38c/src/IR.cpp)
8. **Translation:** Robot class computes XY `atan2` and magnitude and swaps ±magnitude/2 across half-turns. Current main calls `robot.move(0,0,0,dt)` rather than received channels, so this is unfinished control integration. [Robot](https://github.com/PsychoticRobotics/Project-Meltybrain/blob/a089aafa578768386fcce71b592ad79e2035c38c/src/Robot.cpp), [main](https://github.com/PsychoticRobotics/Project-Meltybrain/blob/a089aafa578768386fcce71b592ad79e2035c38c/src/main.cpp)
9. **LED:** Main includes heading arc, then overrides it with fixed20 ms on/100 ms strobe test. [Main](https://github.com/PsychoticRobotics/Project-Meltybrain/blob/a089aafa578768386fcce71b592ad79e2035c38c/src/main.cpp)
10. **Calibration:** Per-sensor additive offset/scaling supported; runtime correction table credited in README but not present in inspected current accelerometer path; logging code commented. [Sensor](https://github.com/PsychoticRobotics/Project-Meltybrain/blob/a089aafa578768386fcce71b592ad79e2035c38c/src/Accelerometer.cpp), [README](https://github.com/PsychoticRobotics/Project-Meltybrain/blob/a089aafa578768386fcce71b592ad79e2035c38c/readme.md)
11. **RC/modes/failsafe:** CRSF parser/link-loss check; loss enters endless `move(0,0,0,0)` loop. Actual motor-zero efficacy not validated here. [Main](https://github.com/PsychoticRobotics/Project-Meltybrain/blob/a089aafa578768386fcce71b592ad79e2035c38c/src/main.cpp)
12. **Unusual ideas:** Sensor-frame rotation and one/two-sensor manager, source attribution to several earlier libraries. [Sensor](https://github.com/PsychoticRobotics/Project-Meltybrain/blob/a089aafa578768386fcce71b592ad79e2035c38c/src/Accelerometer.cpp), [README](https://github.com/PsychoticRobotics/Project-Meltybrain/blob/a089aafa578768386fcce71b592ad79e2035c38c/readme.md)
13. **Problems/results:** Current source is clearly a development/test configuration; no successful integrated melty test claimed by this survey. Diagnostic serial output extensive. [Main](https://github.com/PsychoticRobotics/Project-Meltybrain/blob/a089aafa578768386fcce71b592ad79e2035c38c/src/main.cpp)
14. **License:** Mixed attribution: SimpleMelt MIT, PotatoMelt LGPL2.1, TeensyShot GPL3; README and separate license files, not a single uniform grant. [Licensing](https://github.com/PsychoticRobotics/Project-Meltybrain/blob/a089aafa578768386fcce71b592ad79e2035c38c/readme.md)

<a id="p018"></a>

## P018. lpinfinity/picomelt

1. **Identity/activity:** [picomelt](https://github.com/lpinfinity/picomelt), lpinfinity; last push 2024-03-23. [README](https://github.com/lpinfinity/picomelt/blob/868b7f1be07e0a49db3b40e7802120189535680e/README.md)
2. **Source type/read:** MicroPython `main.py`, DShotFunctions and PIO SendFrame, README. [Main](https://github.com/lpinfinity/picomelt/blob/868b7f1be07e0a49db3b40e7802120189535680e/code/main.py)
3. **Robot context:** Author calls it very unfinished meltybrain project; weight/class not found. [README](https://github.com/lpinfinity/picomelt/blob/868b7f1be07e0a49db3b40e7802120189535680e/README.md)
4. **Hardware:** RP2040, ESC outputs, planned H3LIS331DL and NRF24L01+ radio. Main runs CPU 250 MHz and sends test commands on pins 0/1. Exact ESC/motor models not found. [Main](https://github.com/lpinfinity/picomelt/blob/868b7f1be07e0a49db3b40e7802120189535680e/code/main.py), [README](https://github.com/lpinfinity/picomelt/blob/868b7f1be07e0a49db3b40e7802120189535680e/README.md)
5. **Sensor/placement:** No implemented heading sensor; accelerometer explicitly not working. Placement not found. [README](https://github.com/lpinfinity/picomelt/blob/868b7f1be07e0a49db3b40e7802120189535680e/README.md)
6. **Math/rates:** DShot frame/checksum and PIO pulse generation implemented; no heading/RPM math. Main fixed command 100; PIO state machine configured 3.6 MHz. [SendFrame](https://github.com/lpinfinity/picomelt/blob/868b7f1be07e0a49db3b40e7802120189535680e/code/Dshot/SendFrame.py)
7. **Drift:** No implementation found; no active heading estimate.
8. **Translation:** Not implemented; author explicitly lists “part where it melts” as not working. [README](https://github.com/lpinfinity/picomelt/blob/868b7f1be07e0a49db3b40e7802120189535680e/README.md)
9. **LED:** Heading display not found in inspected files.
10. **Calibration:** ESC arming helpers; sensor/heading calibration not found. [Helpers](https://github.com/lpinfinity/picomelt/blob/868b7f1be07e0a49db3b40e7802120189535680e/code/Dshot/DshotFunctions.py)
11. **RC/modes/failsafe:** Transmitter communication explicitly not working; no complete robot-mode/failsafe implementation found. [README](https://github.com/lpinfinity/picomelt/blob/868b7f1be07e0a49db3b40e7802120189535680e/README.md)
12. **Unusual ideas:** RP2040 PIO DShot in MicroPython, independent multiple ESC control; this is an experiment, not completed controller. [SendFrame](https://github.com/lpinfinity/picomelt/blob/868b7f1be07e0a49db3b40e7802120189535680e/code/Dshot/SendFrame.py)
13. **Problems/results:** Author reports one-direction DShot up to 1200 and checksums working; return-frame reading and bidirectional DShot not implemented, ESC compatibility uncertain. [README](https://github.com/lpinfinity/picomelt/blob/868b7f1be07e0a49db3b40e7802120189535680e/README.md)
14. **License:** [GPL-3.0](https://github.com/lpinfinity/picomelt/blob/868b7f1be07e0a49db3b40e7802120189535680e/LICENSE).

<a id="p019"></a>

## P019. Nv7-GitHub/sunshine

1. **Identity/activity:** [Sunshine](https://github.com/Nv7-GitHub/sunshine), Nv7-GitHub; last push 2026-08-24; one-pound meltybrain robot and host-control/replay system. [README](https://github.com/Nv7-GitHub/sunshine/blob/f900217bd7e486aa8bf07354697bc85d60384e0a/README.md)
2. **Source type/read:** C core `brain.c`, `kalman.c`, `mag_heading.c`, `control.c`, shared header, ESP32 nav control/config and README. Host React/Tauri app, simulator, tests and PCB assets located; not all UI/build files audited. [Core](https://github.com/Nv7-GitHub/sunshine/blob/f900217bd7e486aa8bf07354697bc85d60384e0a/sunshine_core/src/brain.c)
3. **Robot context:** One-pound body spinner, 44 mm wheels at 40.5 mm contact radius. Author's linked build report describes arena operation and limitations; this survey did not reproduce it. [README](https://github.com/Nv7-GitHub/sunshine/blob/f900217bd7e486aa8bf07354697bc85d60384e0a/README.md), [build report](https://medium.com/@vikramaditya.nishant/building-sunshine-my-meltybrain-combat-robot-c30aa733fb97)
4. **Hardware:** ESP32-S3, ADXL375, LIS3MDL magnetometer, two AM32 bidirectional DShot600 motor channels, battery ADC, switched LED, ESP-NOW bridge and desktop control. [README](https://github.com/Nv7-GitHub/sunshine/blob/f900217bd7e486aa8bf07354697bc85d60384e0a/README.md), [pin config](https://github.com/Nv7-GitHub/sunshine/blob/f900217bd7e486aa8bf07354697bc85d60384e0a/sunshine_brain/include/config.h)
5. **Sensor/placement:** ADXL375, 11 mm off spin centre, rotated 45°; XY acceleration magnitude gives rate, ±200 g per-axis clipping guard plus 280 g magnitude guard. Magnetometer uses two rotating field axes for absolute reference. [Header](https://github.com/Nv7-GitHub/sunshine/blob/f900217bd7e486aa8bf07354697bc85d60384e0a/sunshine_core/include/sunshine_core.h), [brain](https://github.com/Nv7-GitHub/sunshine/blob/f900217bd7e486aa8bf07354697bc85d60384e0a/sunshine_core/src/brain.c)
6. **Math/rates:** 1 kHz control; two-state angle/rate Kalman filter. Rate observation is √(a/r) signed by smoothed magnetometer rotation; `atan2(-my,mx)` after two-axis RBJ bandpass anchors angle. Bandpass Q1.5 centred on independent acceleration-derived spin rate, smoothed 1.5 Hz; compass enabled above ~480 RPM. [Brain](https://github.com/Nv7-GitHub/sunshine/blob/f900217bd7e486aa8bf07354697bc85d60384e0a/sunshine_core/src/brain.c), [Kalman](https://github.com/Nv7-GitHub/sunshine/blob/f900217bd7e486aa8bf07354697bc85d60384e0a/sunshine_core/src/kalman.c), [mag filter](https://github.com/Nv7-GitHub/sunshine/blob/f900217bd7e486aa8bf07354697bc85d60384e0a/sunshine_core/src/mag_heading.c)
7. **Drift:** Magnetic angle updates plus driver heading offset. Code explicitly avoids centring filter on estimated rate because feedback had produced half-rate false lock. Mag-rate observation was reverted; present implementation uses acceleration magnitude, despite stale “mag-driven” phrasing in control comments. [Brain](https://github.com/Nv7-GitHub/sunshine/blob/f900217bd7e486aa8bf07354697bc85d60384e0a/sunshine_core/src/brain.c), [mag filter](https://github.com/Nv7-GitHub/sunshine/blob/f900217bd7e486aa8bf07354697bc85d60384e0a/sunshine_core/src/mag_heading.c)
8. **Translation:** Arbitrary XY direction/magnitude drives balanced bipolar trapezoid, 35% plateau each sign; opposite motor differentials around capped base, 40% headroom amplitude and 18 ms rate-dependent phase lead. [Control](https://github.com/Nv7-GitHub/sunshine/blob/f900217bd7e486aa8bf07354697bc85d60384e0a/sunshine_core/src/control.c), [tuning constants](https://github.com/Nv7-GitHub/sunshine/blob/f900217bd7e486aa8bf07354697bc85d60384e0a/sunshine_core/include/sunshine_core.h)
9. **LED:** ±3° heading dot widened to at least a control-tick sweep at high rate; tank solid armed indicator, disabled idle pattern in hardware layer. [Control](https://github.com/Nv7-GitHub/sunshine/blob/f900217bd7e486aa8bf07354697bc85d60384e0a/sunshine_core/src/control.c), [config](https://github.com/Nv7-GitHub/sunshine/blob/f900217bd7e486aa8bf07354697bc85d60384e0a/sunshine_brain/include/config.h)
10. **Calibration:** Fixed sensor radius/scales, driver offset, logged replay/tuning; code comments document thermal/magnetic filtering and parameter assumptions. No automatic geometric radius learner in read path. [Header](https://github.com/Nv7-GitHub/sunshine/blob/f900217bd7e486aa8bf07354697bc85d60384e0a/sunshine_core/include/sunshine_core.h)
11. **RC/modes/failsafe:** Desktop/ESP-NOW disabled/tank/melty; 500 ms control-packet watchdog forces disabled. [nav_control](https://github.com/Nv7-GitHub/sunshine/blob/f900217bd7e486aa8bf07354697bc85d60384e0a/sunshine_brain/src/nav_control.cpp)
12. **Unusual ideas:** Same deterministic core on robot and desktop replay; full state/input logging; battery-aware wheel-speed/slip ceiling. Implausible battery skips cap (explicit fail-open policy), dead magnetometer leaves low unlocked ceiling. [Control](https://github.com/Nv7-GitHub/sunshine/blob/f900217bd7e486aa8bf07354697bc85d60384e0a/sunshine_core/src/control.c), [README](https://github.com/Nv7-GitHub/sunshine/blob/f900217bd7e486aa8bf07354697bc85d60384e0a/README.md)
13. **Problems/results:** Source reports real-log magnetic interference, rejected mag-rate filter, median stationary wander 25.7°→11.7° after reversion; these are author log-analysis claims. Build report states translation worked mainly near 900 RPM and describes mechanical impact failures. [Brain comments](https://github.com/Nv7-GitHub/sunshine/blob/f900217bd7e486aa8bf07354697bc85d60384e0a/sunshine_core/src/brain.c), [build report](https://medium.com/@vikramaditya.nishant/building-sunshine-my-meltybrain-combat-robot-c30aa733fb97)
14. **License:** Repository-wide license not found in inspected tree; no inferred grant. [Repository](https://github.com/Nv7-GitHub/sunshine)

<a id="p020"></a>

## P020. MeltyFC/meltyfc

1. **Identity/activity:** [MeltyFC](https://github.com/MeltyFC/meltyfc), STM32 flight-controller firmware platform; last pushed 2026-07-10. README credits AI-agent implementation/review. [README](https://github.com/MeltyFC/meltyfc/blob/52c811929e4db16cecced4b1aa2e00c572ebc03e/README.md)
2. **Source type/read:** C++ pure-logic modules `heading.cpp`, `safety.cpp`, `led_beacon.cpp`, `motors_dshot.cpp`, actual `main.cpp`, README and verification policy. **Main-loop module calls are commented out: this checkout is not a completed integrated controller.** [Main](https://github.com/MeltyFC/meltyfc/blob/52c811929e4db16cecced4b1aa2e00c572ebc03e/src/main.cpp)
3. **Robot context:** Intended off-the-shelf FPV controller platform, not a substantiated completed robot build. README target table says “Ready for hardware”; weight/competition results not found. [README](https://github.com/MeltyFC/meltyfc/blob/52c811929e4db16cecced4b1aa2e00c572ebc03e/README.md)
4. **Hardware:** Declared STM32F405/F411/F722/F745/H743/H725 targets, dual H3LIS331 high-g sensors, onboard gyro, CRSF/ELRS, DShot300 and WS2812/POV options. Driver presence does not demonstrate hardware bringup. [README](https://github.com/MeltyFC/meltyfc/blob/52c811929e4db16cecced4b1aa2e00c572ebc03e/README.md)
5. **Sensor/placement:** Differential outer/inner radial acceleration; configured radii/dr_eff and mount-angle calibration required. [Heading](https://github.com/MeltyFC/meltyfc/blob/52c811929e4db16cecced4b1aa2e00c572ebc03e/src/heading.cpp), [verification gates](https://github.com/MeltyFC/meltyfc/blob/52c811929e4db16cecced4b1aa2e00c572ebc03e/docs/VERIFICATION.md)
6. **Math/rates:** Implemented helper √((a_outer−a_inner)×9.80665/dr_eff), invalid-input guard, rate slew limiter, signed phase integration. Main schedules 500 µs loop but actual heading/sensor calls commented; 2 kHz is design target rather than observed operational rate. [Heading](https://github.com/MeltyFC/meltyfc/blob/52c811929e4db16cecced4b1aa2e00c572ebc03e/src/heading.cpp), [main](https://github.com/MeltyFC/meltyfc/blob/52c811929e4db16cecced4b1aa2e00c572ebc03e/src/main.cpp)
7. **Drift:** Manual heading trim helpers and differential sensing intended to reject shared linear acceleration; absolute arena-heading reference not found in read estimator. [Heading](https://github.com/MeltyFC/meltyfc/blob/52c811929e4db16cecced4b1aa2e00c572ebc03e/src/heading.cpp)
8. **Translation:** XY `atan2` and deadband-remapped magnitude; motor thrust-angle correction +90°, triangular boost window and opposing reduction window, capped output. General motor-position math is implemented as pure functions, not wired to motors in main. [Heading](https://github.com/MeltyFC/meltyfc/blob/52c811929e4db16cecced4b1aa2e00c572ebc03e/src/heading.cpp), [main](https://github.com/MeltyFC/meltyfc/blob/52c811929e4db16cecced4b1aa2e00c572ebc03e/src/main.cpp)
9. **LED:** Beacon/POV module exists; main LED init/update still commented. [LED module](https://github.com/MeltyFC/meltyfc/blob/52c811929e4db16cecced4b1aa2e00c572ebc03e/src/led_beacon.cpp), [main](https://github.com/MeltyFC/meltyfc/blob/52c811929e4db16cecced4b1aa2e00c572ebc03e/src/main.cpp)
10. **Calibration:** CLI/config storage and adjustable sensor radii described; dr_eff versus slow-motion-video validation explicitly hardware-gated. [README](https://github.com/MeltyFC/meltyfc/blob/52c811929e4db16cecced4b1aa2e00c572ebc03e/README.md), [verification](https://github.com/MeltyFC/meltyfc/blob/52c811929e4db16cecced4b1aa2e00c572ebc03e/docs/VERIFICATION.md)
11. **RC/modes/failsafe:** Pure state machine checks valid fresh frames, link quality, arm gesture, battery/sensor/config validity, failsafe and explicit rearm. These checks are implemented but main safety/CRSF/watchdog calls are not active. [Safety](https://github.com/MeltyFC/meltyfc/blob/52c811929e4db16cecced4b1aa2e00c572ebc03e/src/safety.cpp), [main](https://github.com/MeltyFC/meltyfc/blob/52c811929e4db16cecced4b1aa2e00c572ebc03e/src/main.cpp)
12. **Unusual ideas:** Native logic/simulator separation, redundant config storage, hit/slip recovery modules, several MCU targets and feature tiers. These are software architecture/assets, not demonstrated combat behavior. [README](https://github.com/MeltyFC/meltyfc/blob/52c811929e4db16cecced4b1aa2e00c572ebc03e/README.md)
13. **Problems/results:** README reports256 native tests and extensive reviews; not rerun here. Verification doc lists unresolved hardware gates and integration deferrals. Source integration gaps materially limit README's operational wording. [Verification](https://github.com/MeltyFC/meltyfc/blob/52c811929e4db16cecced4b1aa2e00c572ebc03e/docs/VERIFICATION.md), [main](https://github.com/MeltyFC/meltyfc/blob/52c811929e4db16cecced4b1aa2e00c572ebc03e/src/main.cpp)
14. **License:** [GPL-3.0](https://github.com/MeltyFC/meltyfc/blob/52c811929e4db16cecced4b1aa2e00c572ebc03e/LICENSE); README states no OpenMelt2 code used because its noncommercial license is incompatible.

<a id="p021"></a>

## P021. swallenhardware/MeltyHitNSpinV1_1

1. **Identity/activity:** [MeltyHitNSpinV1_1](https://github.com/swallenhardware/MeltyHitNSpinV1_1), Spencer Allen, Hit ’N Spin electronics V1.1; last push 2019-11-08. Historical build outcomes covered separately. [Repository](https://github.com/swallenhardware/MeltyHitNSpinV1_1)
2. **Source type/read:** STM32 C/HAL implementation: `topLoop.c`, `accelerometer.c`, `motors.c`, `serial.c`, `LEDs.c`, main/parameter/sensor headers. [State loop](https://github.com/swallenhardware/MeltyHitNSpinV1_1/blob/b90ebff61acd8a871345de8344e8a8c2954188b7/src/topLoop.c)
3. **Robot context:** Hit ’N Spin controller; class/weight not established by inspected code. Repository contents alone are not evidence that later design issues were resolved. [Repository](https://github.com/swallenhardware/MeltyHitNSpinV1_1)
4. **Hardware:** STM32F446-style project, 120 MHz setting, I²C high-g accelerometer/magnetometer, photodiode ADC, serial radio, RGB LED and one motor command output with DShot/OneShot conditional drivers. Exact motor/ESC models not found. [Main](https://github.com/swallenhardware/MeltyHitNSpinV1_1/blob/b90ebff61acd8a871345de8344e8a8c2954188b7/src/main.c), [parameters](https://github.com/swallenhardware/MeltyHitNSpinV1_1/blob/b90ebff61acd8a871345de8344e8a8c2954188b7/include/params.h), [motors](https://github.com/swallenhardware/MeltyHitNSpinV1_1/blob/b90ebff61acd8a871345de8344e8a8c2954188b7/src/motors.c)
5. **Sensor/placement:** Radial accelerationZ; fixed fitted coefficients, physical radius not declared. Active hybrid heading uses photodiode beacon, not magnetometer helper. [Sensor implementation](https://github.com/swallenhardware/MeltyHitNSpinV1_1/blob/b90ebff61acd8a871345de8344e8a8c2954188b7/src/accelerometer.c), [active call](https://github.com/swallenhardware/MeltyHitNSpinV1_1/blob/b90ebff61acd8a871345de8344e8a8c2954188b7/src/topLoop.c)
6. **Math/rates:** Acceleration reads after10 ms, period µs/degree=549/√((rawZ−22)/397), trapezoid integration and extrapolation. Hybrid20-sample moving average finds brightest beacon angle; refreshes trim every 100 ms. [Sensor](https://github.com/swallenhardware/MeltyHitNSpinV1_1/blob/b90ebff61acd8a871345de8344e8a8c2954188b7/src/accelerometer.c)
7. **Drift:** Subtract highest-beacon-angle trim from accelerometer angle. `runMagnetometer()` exists but is not called by active hybrid path; do not imply operational compass fusion. [Sensor](https://github.com/swallenhardware/MeltyHitNSpinV1_1/blob/b90ebff61acd8a871345de8344e8a8c2954188b7/src/accelerometer.c)
8. **Translation:** Serial XY `atan2` desired direction; magnitude>10 enables half-turn sectors alternating speed/2 and speed on single motor command; direction switch changes spin sign. [Loop](https://github.com/swallenhardware/MeltyHitNSpinV1_1/blob/b90ebff61acd8a871345de8344e8a8c2954188b7/src/topLoop.c), [serial](https://github.com/swallenhardware/MeltyHitNSpinV1_1/blob/b90ebff61acd8a871345de8344e8a8c2954188b7/src/serial.c)
9. **LED:** RGB direction/status: blue near requested direction, red/green semicircles, safe red and idle yellow. 20 kHz PWM LED driver. [Loop](https://github.com/swallenhardware/MeltyHitNSpinV1_1/blob/b90ebff61acd8a871345de8344e8a8c2954188b7/src/topLoop.c), [LEDs](https://github.com/swallenhardware/MeltyHitNSpinV1_1/blob/b90ebff61acd8a871345de8344e8a8c2954188b7/src/LEDs.c)
10. **Calibration:** Hardcoded fitted period curve and 90°/270° beacon flip offset; serial calibration/photodiode logging helpers. No complete interactive radius calibration found. [Sensor](https://github.com/swallenhardware/MeltyHitNSpinV1_1/blob/b90ebff61acd8a871345de8344e8a8c2954188b7/src/accelerometer.c), [loop](https://github.com/swallenhardware/MeltyHitNSpinV1_1/blob/b90ebff61acd8a871345de8344e8a8c2954188b7/src/topLoop.c)
11. **RC/modes/failsafe:** Safe/idle/spin, enable 0xAA,1 s receive timeout and watchdog init/feed; motor-enable behavior conditional on selected driver. [Loop](https://github.com/swallenhardware/MeltyHitNSpinV1_1/blob/b90ebff61acd8a871345de8344e8a8c2954188b7/src/topLoop.c), [serial](https://github.com/swallenhardware/MeltyHitNSpinV1_1/blob/b90ebff61acd8a871345de8344e8a8c2954188b7/src/serial.c)
12. **Unusual ideas:** Beacon peak plus acceleration trim, DMA DShot pulse generation and motor-setpoint slew. Magnetometer exploration exists alongside beacon design. [Sensor](https://github.com/swallenhardware/MeltyHitNSpinV1_1/blob/b90ebff61acd8a871345de8344e8a8c2954188b7/src/accelerometer.c), [motors](https://github.com/swallenhardware/MeltyHitNSpinV1_1/blob/b90ebff61acd8a871345de8344e8a8c2954188b7/src/motors.c)
13. **Problems/results:** Code explicitly says accelerometer heading drifts, includes STM32 I²C busy-erratum recovery and notes blocking reads. Independent successful translation/heading results not established. The separate Meltycompass/GitLab research record covers the later magnetic-heading experiment; this repository does not establish its operation. [Sensor](https://github.com/swallenhardware/MeltyHitNSpinV1_1/blob/b90ebff61acd8a871345de8344e8a8c2954188b7/src/accelerometer.c)
14. **License:** Root license not found in inspected file inventory; STM32/HAL vendor terms do not establish a blanket license for author code. [Repository](https://github.com/swallenhardware/MeltyHitNSpinV1_1)

<a id="p022"></a>

## P022. gavin4d/dangerDonut

1. **Identity/activity:** [Danger Donut](https://github.com/gavin4d/dangerDonut), gavin4d; last pushed 2024-05-25. [README](https://github.com/gavin4d/dangerDonut/blob/140206fd95df1dd11c0fde63067f5b25440ca995/README.md)
2. **Source type/read:** ESP-IDF/Arduino C++ `main/sketch.cpp`, `orientator.cpp/h`, `kalmanFilter.cpp`, README/license and component inventory. [Sketch](https://github.com/gavin4d/dangerDonut/blob/140206fd95df1dd11c0fde63067f5b25440ca995/main/sketch.cpp)
3. **Robot context:** Author calls it work-in-progress 150 g melty; CAD, PCB, IR beacon, ESC configs and POV artwork are supplied/linked. No validated competition result found. [README](https://github.com/gavin4d/dangerDonut/blob/140206fd95df1dd11c0fde63067f5b25440ca995/README.md)
4. **Hardware:** ESP32/Bluepad32 Bluetooth gamepad, SPI ADXL375, IR beacon input, two DShotRMT ESC outputs, 11 HD107S LEDs, battery ADC and Preferences storage. Motor/ESC models not found in inspected code. [Sketch](https://github.com/gavin4d/dangerDonut/blob/140206fd95df1dd11c0fde63067f5b25440ca995/main/sketch.cpp)
5. **Sensor/placement:** XY centripetal magnitude; ten speed-indexed effective sensor radii interpolated, default 0.03 m; IR bit history supplies orientation and fallback rotation frequency. [Orientator](https://github.com/gavin4d/dangerDonut/blob/140206fd95df1dd11c0fde63067f5b25440ca995/components/orientator/orientator.cpp)
6. **Math/rates:** √(normAccel×scale/radius), 280 g reject guard; IR sampled every 1 ms into 500 bits. Autocorrelation estimates period on accelerometer failure; two convolution passes estimate beacon phase. Constant-acceleration filter predicts angle/rate/acceleration and blends angle/rate innovations with simplified variance handling. [Orientator](https://github.com/gavin4d/dangerDonut/blob/140206fd95df1dd11c0fde63067f5b25440ca995/components/orientator/orientator.cpp), [filter](https://github.com/gavin4d/dangerDonut/blob/140206fd95df1dd11c0fde63067f5b25440ca995/components/orientator/kalmanFilter.cpp)
7. **Drift:** IR phase updates integrated orientation; invalid measurement gets infinite variance. Driver directly adjusts filter angle. No arena compass used. [Orientator](https://github.com/gavin4d/dangerDonut/blob/140206fd95df1dd11c0fde63067f5b25440ca995/components/orientator/orientator.cpp)
8. **Translation:** Smooth sine differential from XY magnitude/atan2 around signed trigger spin power; direction-specific fixed offsets and flip compensation, outputs jointly normalized. [Sketch](https://github.com/gavin4d/dangerDonut/blob/140206fd95df1dd11c0fde63067f5b25440ca995/main/sketch.cpp)
9. **LED:** Per-revolution timer updates POV text/numerals/art, including RPM; disconnected animation. [Sketch](https://github.com/gavin4d/dangerDonut/blob/140206fd95df1dd11c0fde63067f5b25440ca995/main/sketch.cpp)
10. **Calibration:** Preferences loads per-axis offsets and ten effective radii; gamepad changes/saves values. PID spin-control scaffolding present but commented; active trigger power open-loop. [Sketch](https://github.com/gavin4d/dangerDonut/blob/140206fd95df1dd11c0fde63067f5b25440ca995/main/sketch.cpp)
11. **RC/modes/failsafe:** Bluepad32 gamepad; low spin command tank, otherwise melty; 3 s stale-input threshold zeros motors, disconnect zeros motors. [Sketch](https://github.com/gavin4d/dangerDonut/blob/140206fd95df1dd11c0fde63067f5b25440ca995/main/sketch.cpp)
12. **Unusual ideas:** IR autocorrelation/convolution instead of simple edge triggering; hybrid filter fallback, future heading timer and inertia-based self-right inputs. [Orientator](https://github.com/gavin4d/dangerDonut/blob/140206fd95df1dd11c0fde63067f5b25440ca995/components/orientator/orientator.cpp), [sketch](https://github.com/gavin4d/dangerDonut/blob/140206fd95df1dd11c0fde63067f5b25440ca995/main/sketch.cpp)
13. **Problems/results:** README labels WIP; filter comments explicitly ignore covariance in variance prediction. Completed navigation performance not found; upstream template changelog is not a robot test history. [README](https://github.com/gavin4d/dangerDonut/blob/140206fd95df1dd11c0fde63067f5b25440ca995/README.md), [filter](https://github.com/gavin4d/dangerDonut/blob/140206fd95df1dd11c0fde63067f5b25440ca995/components/orientator/kalmanFilter.cpp)
14. **License:** Root lists template Apache2, Bluepad32 Apache2, Arduino integration Apache2/LGPL2.1-or-later and BTstack external license. It does not clearly state a separate uniform author-code license. [License](https://github.com/gavin4d/dangerDonut/blob/140206fd95df1dd11c0fde63067f5b25440ca995/LICENSE)

<a id="p023"></a>

## P023. celeron55/kasari

1. **Identity/activity:** [Kasari/Kasarisw](https://github.com/celeron55/kasari), celeron55; last pushed 2025-11-17. [README](https://github.com/celeron55/kasari/blob/ec8fc793330301a57c84c984fd68ebf532efdcd2/README.md)
2. **Source type/read:** Rust shared `mod.rs`, `algorithm.rs`, `sensors.rs`, root/software READMEs; firmware, egui simulator/replay, CAD and Python logging tools located. [Software README](https://github.com/celeron55/kasari/blob/ec8fc793330301a57c84c984fd68ebf532efdcd2/kasarisw/README.md)
3. **Robot context:** Autonomous spinning robot, described 500–2000 RPM range;  object-following/wall-avoidance goals. Weight/class and independently verified combat results not found. [README](https://github.com/celeron55/kasari/blob/ec8fc793330301a57c84c984fd68ebf532efdcd2/kasarisw/README.md)
4. **Hardware:** ESP32, fixed LDS02RR LIDAR with fake encoder, ADXL373 SPI, two PWM motor/ESC channels, RMT PWM receiver, battery ADC and Wi-Fi/TCP. [README](https://github.com/celeron55/kasari/blob/ec8fc793330301a57c84c984fd68ebf532efdcd2/kasarisw/README.md)
5. **Sensor/placement:** Radial Y acceleration; calibrated radius 0.0145 m when receiver/extra capacitors installed. Current combat offset 3.4 g hardcoded. [Algorithm](https://github.com/celeron55/kasari/blob/ec8fc793330301a57c84c984fd68ebf532efdcd2/kasarisw/src/shared/algorithm.rs)
6. **Math/rates:** Accel sampled every 10 ms; 0.2 new/0.8 old filter; RPM=√(|g−offset|×9.81/r)×60/(2π). Detector angle integrates at LIDAR event timestamps; 90 distance bins 4° wide. Planner runs 50 ms. Modulator interpolates phase from plan rotation speed between syncs. [Sensors](https://github.com/celeron55/kasari/blob/ec8fc793330301a57c84c984fd68ebf532efdcd2/kasarisw/src/sensors.rs), [algorithm](https://github.com/celeron55/kasari/blob/ec8fc793330301a57c84c984fd68ebf532efdcd2/kasarisw/src/shared/algorithm.rs), [shared logic](https://github.com/celeron55/kasari/blob/ec8fc793330301a57c84c984fd68ebf532efdcd2/kasarisw/src/shared/mod.rs)
7. **Drift:** No absolute magnetic/beacon reference found in read heading path; virtual frame limited by rate accuracy. Planned inversion/angular correction currently forced 0 in both branches. [Shared logic](https://github.com/celeron55/kasari/blob/ec8fc793330301a57c84c984fd68ebf532efdcd2/kasarisw/src/shared/mod.rs), [README](https://github.com/celeron55/kasari/blob/ec8fc793330301a57c84c984fd68ebf532efdcd2/kasarisw/README.md)
8. **Translation:** Desired vector determines phase/magnitude; ±250 RPM×magnitude×cos(theta−phase) around base motor RPM. Autonomous vector blends wall/open-space/object detections with attack behavior. [MotorModulator/planner](https://github.com/celeron55/kasari/blob/ec8fc793330301a57c84c984fd68ebf532efdcd2/kasarisw/src/shared/mod.rs)
9. **LED:** Heading LED behavior not found in inspected shared/sensor implementation.
10. **Calibration:** Effective radius/comment tied to installed mass; stationary-offset learner exists but bypassed by hardcoded combat offset/done flag. [Algorithm](https://github.com/celeron55/kasari/blob/ec8fc793330301a57c84c984fd68ebf532efdcd2/kasarisw/src/shared/algorithm.rs)
11. **RC/modes/failsafe:** Manual Wi-Fi/autonomous/RC control; 5 s input freshness, plus 500 ms stale motor-plan invalidation. RC mode mainly enables autonomy rather than conventional two-stick directional driving. [Shared logic](https://github.com/celeron55/kasari/blob/ec8fc793330301a57c84c984fd68ebf532efdcd2/kasarisw/src/shared/mod.rs)
12. **Unusual ideas:** Fixed LIDAR scans arena through body spin; shared embedded/simulator logic and binary event logging/replay, position/velocity estimates from arena-wall distances. [README](https://github.com/celeron55/kasari/blob/ec8fc793330301a57c84c984fd68ebf532efdcd2/kasarisw/README.md), [algorithm](https://github.com/celeron55/kasari/blob/ec8fc793330301a57c84c984fd68ebf532efdcd2/kasarisw/src/shared/algorithm.rs)
13. **Problems/results:** Author sensor comments document fake encoder too fast causing buffering/data failure: 86 Hz too fast, 83 Hz gave 17 mm false distances; 80 Hz chosen. Virtual frame accuracy and disabled flip correction remain limits; autonomous success not independently established. [Sensors](https://github.com/celeron55/kasari/blob/ec8fc793330301a57c84c984fd68ebf532efdcd2/kasarisw/src/sensors.rs), [shared logic](https://github.com/celeron55/kasari/blob/ec8fc793330301a57c84c984fd68ebf532efdcd2/kasarisw/src/shared/mod.rs)
14. **License:** Repository-wide license not found in inspected root; dependency licenses do not establish author-code grant. [Repository](https://github.com/celeron55/kasari)

<a id="p024"></a>

## P024. Holy Guacamole — Kieran Klukas (Tangled canonical, GitHub mirror)

1. **Name / author / links / activity:** [Holy Guacamole — Kieran Klukas (Tangled canonical, GitHub mirror)](https://github.com/taciturnaxolotl/holy-guacamole); owner/attribution as stated above. Repository push activity 2026-11-06 UTC (not necessarily latest design/test date). [metadata](https://api.github.com/repos/taciturnaxolotl/holy-guacamole).

2. **Source type and actual inspection:** Both code and engineering documentation; actually read docs/firmware.md, drift.c, ekf.c, the ESP-RSSI README and license. Simulator results below are author-reported, not rerun here. [docs/firmware.md](https://github.com/taciturnaxolotl/holy-guacamole/blob/main/docs/firmware.md)

3. **Robot context:** Author's firmware model: 0.454 kg, 170 mm body and 230 mm weapon tip diameter; normal 2600–2750 RPM, burst 3750–4000 RPM are model/design parameters, not verified combat measurements. Competition use: not found. [docs/firmware.md](https://github.com/taciturnaxolotl/holy-guacamole/blob/main/docs/firmware.md)

4. **Hardware:** XIAO RP2350 flight controller; onboard ESP32-C3 RSSI sensor and stationary ESP32-C3 beacon; ELRS/CRSF receiver; LSM6DSV320X inner IMU, two H3LIS331DL outer sensors, DShot600 interface. Exact motors/ESC models: not found in inspected files. [docs/firmware.md](https://github.com/taciturnaxolotl/holy-guacamole/blob/main/docs/firmware.md)

5. **Heading sensing and placement:** Inner IMU at 12 mm/0°, outer sensors at 18 mm/90° and 18 mm/210°; radial and tangential acceleration, plus inner gyro. ESP-NOW packet RSSI is a separate absolute phase candidate; its payload carries sequence/magic, not heading. [docs/firmware.md](https://github.com/taciturnaxolotl/holy-guacamole/blob/main/docs/firmware.md) [firmware/sketches/esp-rssi/README.md](https://github.com/taciturnaxolotl/holy-guacamole/blob/main/firmware/sketches/esp-rssi/README.md)

6. **Angle / RPM algorithm, filtering and rate:** Implemented three-state EKF [theta, omega, alpha], using radial omega²r, tangential alpha*r and gyro measurement rows. ekf_predict integrates theta += omega*dt + alpha*dt²/2 and wraps it; alpha clamped ±500 rad/s²; Joseph-form covariance update. Saturated measurements have noise inflated 1e10. Documented IMU polling: 1 kHz. Aspirational seven-state CoR/jerk/eRPM filter is explicitly unimplemented. [firmware/src/estimation/ekf.c](https://github.com/taciturnaxolotl/holy-guacamole/blob/main/firmware/src/estimation/ekf.c) [docs/firmware.md](https://github.com/taciturnaxolotl/holy-guacamole/blob/main/docs/firmware.md)

7. **Drift handling:** RSSI pipeline interpolates samples, acquires period via autocorrelation, then uses edge PLL; ~100 Hz theta/omega/lock frames to RP2350. EKF has scalar wrapped-heading update. Acceleration alone does not observe absolute heading; gyro rails above ~670 RPM. Real-world heading-lock validation: not found. [firmware/sketches/esp-rssi/README.md](https://github.com/taciturnaxolotl/holy-guacamole/blob/main/firmware/sketches/esp-rssi/README.md) [firmware/src/estimation/ekf.c](https://github.com/taciturnaxolotl/holy-guacamole/blob/main/firmware/src/estimation/ekf.c) [docs/firmware.md](https://github.com/taciturnaxolotl/holy-guacamole/blob/main/docs/firmware.md)

8. **Translation timing and mapping:** drift_compute supports sinusoid A=clamp(base+authority*cos(theta-phi-pi/2)), B with opposite modulation; square mode boosts one motor each half turn, slightly reduces other by 0.15*authority. Stick magnitude sets authority, atan2(y, x) sets phi. Selection is build-time. [firmware/src/control/drift.c](https://github.com/taciturnaxolotl/holy-guacamole/blob/main/firmware/src/control/drift.c) [docs/firmware.md](https://github.com/taciturnaxolotl/holy-guacamole/blob/main/docs/firmware.md)

9. **Heading indicator:** Heading strobe and SK9822 status LEDs are explicitly not implemented despite assigned pins; planned hard PIO pulse-width cap also absent. [docs/firmware.md](https://github.com/taciturnaxolotl/holy-guacamole/blob/main/docs/firmware.md)

10. **Calibration:** accel_cal inverse correction table wired into shared SI path; no-op without table. B/C currently share a curve, bench spin-sweep table acquisition remains future work. Heading/drift phase constants account for ESC response lag. [docs/firmware.md](https://github.com/taciturnaxolotl/holy-guacamole/blob/main/docs/firmware.md)

11. **Controls, modes and failsafes:** ELRS on RP2350 UART0, RSSI on UART1; documented watchdog, RC-health and battery modules. Exact transmitter channel map and timeout values: not found in inspected files. [docs/firmware.md](https://github.com/taciturnaxolotl/holy-guacamole/blob/main/docs/firmware.md)

12. **Notable ideas:** One estimator/controller path serves firmware and software-in-loop twin; three sensor positions and explicit gyro saturation. RSSI heading uses radio amplitude measured on received packets. [docs/firmware.md](https://github.com/taciturnaxolotl/holy-guacamole/blob/main/docs/firmware.md) [firmware/sketches/esp-rssi/README.md](https://github.com/taciturnaxolotl/holy-guacamole/blob/main/firmware/sketches/esp-rssi/README.md)

13. **Problems, failures and evidence limits:** Author records incorrect unsaturated-gyro assumptions in old simulation, sensor nonlinearity causing simulated ~180° drift in 3 s, Box2D high-RPM artifacts, clipping of translation at high throttle, unimplemented drivers/LEDs, and stale contradictory model numbers. Treat simulation tables as version-dependent, not hardware proof. [docs/firmware.md](https://github.com/taciturnaxolotl/holy-guacamole/blob/main/docs/firmware.md)

14. **License:** Hardware CERN-OHL-S v2; firmware/software/docs MIT. [LICENSE.md](https://github.com/taciturnaxolotl/holy-guacamole/blob/main/LICENSE.md)

<a id="p025"></a>

## P025. OlivePrichard/meltybrain

1. **Name / author / links / activity:** [OlivePrichard/meltybrain](https://github.com/OlivePrichard/meltybrain); owner/attribution as stated above. Repository push activity 2025-04-12 UTC (not necessarily latest design/test date). [metadata](https://api.github.com/repos/OlivePrichard/meltybrain).

2. **Source type and actual inspection:** Code repository; read control_logic.rs, hardware.rs, math.rs and watchdog.rs. [src/control_logic.rs](https://github.com/OlivePrichard/meltybrain/blob/main/src/control_logic.rs)

3. **Robot context:** Weight, dimensions, named robot and competition outcome: not found. A code comment mentions the night before competition in November 2024, without identifying event. Source: [OlivePrichard/meltybrain](https://github.com/OlivePrichard/meltybrain).

4. **Hardware:** ESP HAL/Embassy Rust environment, I2C accelerometer interface at 0x53, motor-controller board at 0x42, LED GPIO10. Exact MCU variant and sensor model: not found; 0.049 g/LSB is hardcoded, not enough to assert a part. [src/control_logic.rs](https://github.com/OlivePrichard/meltybrain/blob/main/src/control_logic.rs)

5. **Heading sensing and placement:** read_accelerometer decodes three signed axes; radius variable 10 mm. The function is not called by the inspected motor loop. Mounting orientation: not found. [src/control_logic.rs](https://github.com/OlivePrichard/meltybrain/blob/main/src/control_logic.rs)

6. **Angle / RPM algorithm, filtering and rate:** Nominal 3200 Hz ticker, theta += dt*omega and wrap ±pi. omega starts zero and is never updated in this loop; accelerometer branch is placeholder. Thus operational heading/RPM estimation is not established. [src/control_logic.rs](https://github.com/OlivePrichard/meltybrain/blob/main/src/control_logic.rs)

7. **Drift handling:** not found.

8. **Translation timing and mapping:** Left trigger >=32 commands opposing fixed spin powers; D-pad changes k_spin_velocity (40/80/120) and a move coefficient, but no directional modulation uses that move coefficient in the inspected loop. Motor packets sent every other iteration. Translation algorithm incomplete. [src/control_logic.rs](https://github.com/OlivePrichard/meltybrain/blob/main/src/control_logic.rs)

9. **Heading indicator:** led_update is empty; constants specify a proposed -90° center and 10° window but do not implement a strobe. [src/control_logic.rs](https://github.com/OlivePrichard/meltybrain/blob/main/src/control_logic.rs)

10. **Calibration:** 10 mm radius is a variable; calibration procedure not found. [src/control_logic.rs](https://github.com/OlivePrichard/meltybrain/blob/main/src/control_logic.rs)

11. **Controls, modes and failsafes:** Motor loop sends zero when shared armed flag is false; standalone async watchdog tracks a deadline. End-to-end timeout and radio protocol behavior: not established from inspected files. [src/control_logic.rs](https://github.com/OlivePrichard/meltybrain/blob/main/src/control_logic.rs) [src/watchdog.rs](https://github.com/OlivePrichard/meltybrain/blob/main/src/watchdog.rs)

12. **Notable ideas:** Eight-byte I2C motor command consists of two little-endian float bit patterns; custom trigonometric approximations and inverse-square-root helpers exist. [src/control_logic.rs](https://github.com/OlivePrichard/meltybrain/blob/main/src/control_logic.rs) [src/math.rs](https://github.com/OlivePrichard/meltybrain/blob/main/src/math.rs)

13. **Problems, failures and evidence limits:** Code comment reports left motor does not turn below 22% and suspects ESC issue; hardware.rs warns WheelAngle only works for positive angles. [src/control_logic.rs](https://github.com/OlivePrichard/meltybrain/blob/main/src/control_logic.rs) [src/hardware.rs](https://github.com/OlivePrichard/meltybrain/blob/main/src/hardware.rs)

14. **License:** LICENSE-APACHE and LICENSE-MIT are present in repository tree; per-file dual-license choice was not separately established. [license files](https://github.com/OlivePrichard/meltybrain)

<a id="p026"></a>

## P026. OlivePrichard/meltybrain_driver_station

1. **Name / author / links / activity:** [OlivePrichard/meltybrain_driver_station](https://github.com/OlivePrichard/meltybrain_driver_station); owner/attribution as stated above. Repository push activity 2025-04-09 UTC (not necessarily latest design/test date). [metadata](https://api.github.com/repos/OlivePrichard/meltybrain_driver_station).

2. **Source type and actual inspection:** Code repository; read controller_input.rs and main.rs. Separate companion software, not proof of another physical robot. [src/controller_input.rs](https://github.com/OlivePrichard/meltybrain_driver_station/blob/main/src/controller_input.rs)

3. **Robot context:** not found.

4. **Hardware:** Desktop gilrs gamepad input and Tokio tasks; physical robot MCU/sensors/ESCs: not found in this companion. [src/controller_input.rs](https://github.com/OlivePrichard/meltybrain_driver_station/blob/main/src/controller_input.rs)

5. **Heading sensing and placement:** not found.

6. **Angle / RPM algorithm, filtering and rate:** not found.

7. **Drift handling:** not found.

8. **Translation timing and mapping:** Robot-side pulse scheduling not found. Source: [OlivePrichard/meltybrain_driver_station](https://github.com/OlivePrichard/meltybrain_driver_station).

9. **Heading indicator:** not found.

10. **Calibration:** not found.

11. **Controls, modes and failsafes:** Samples primary and secondary gamepads every 20 ms; converts sticks/triggers, face/D-pad/bumper buttons to ControllerState; disconnected controller produces default state. Robot-side loss-of-link action: not found here. [src/controller_input.rs](https://github.com/OlivePrichard/meltybrain_driver_station/blob/main/src/controller_input.rs)

12. **Notable ideas:** Supports two simultaneous controller states. [src/controller_input.rs](https://github.com/OlivePrichard/meltybrain_driver_station/blob/main/src/controller_input.rs)

13. **Problems, failures and evidence limits:** not found.

14. **License:** MIT, repository LICENSE. [LICENSE](https://github.com/OlivePrichard/meltybrain_driver_station/blob/main/LICENSE)

<a id="p027"></a>

## P027. DublerIno meltybrain PCB

1. **Name / author / links / activity:** [DublerIno meltybrain PCB](https://github.com/DublerIno/meltybrain_pcb); owner/attribution as stated above. Repository push activity 2026-08-19 UTC (not necessarily latest design/test date). [metadata](https://api.github.com/repos/DublerIno/meltybrain_pcb).

2. **Source type and actual inspection:** Hardware repository plus written description; read README, not firmware or schematic nets. Source: [DublerIno meltybrain PCB](https://github.com/DublerIno/meltybrain_pcb).

3. **Robot context:** not found.

4. **Hardware:** ESP32-S3 SuperMini and H3LIS331DL. [README](https://github.com/DublerIno/meltybrain_pcb/blob/main/README.md)

5. **Heading sensing and placement:** High-g accelerometer provided; exact placement relative to spin center not found. Source: [DublerIno meltybrain PCB](https://github.com/DublerIno/meltybrain_pcb).

6. **Angle / RPM algorithm, filtering and rate:** not found.

7. **Drift handling:** not found.

8. **Translation timing and mapping:** not found.

9. **Heading indicator:** not found.

10. **Calibration:** not found.

11. **Controls, modes and failsafes:** not found.

12. **Notable ideas:** Custom integrated PCB first iteration. [README](https://github.com/DublerIno/meltybrain_pcb/blob/main/README.md)

13. **Problems, failures and evidence limits:** Author lists vias under H3 package and mounting-hole mechanical stress as items to fix. [README](https://github.com/DublerIno/meltybrain_pcb/blob/main/README.md)

14. **License:** not found.

<a id="p028"></a>

## P028. Luna Waller — MeltyBrain PCB

1. **Name / author / links / activity:** [Luna Waller — MeltyBrain PCB](https://github.com/LunaWithARose/meltybrain-kicad); owner/attribution as stated above. Repository push activity 2026-11-02 UTC (not necessarily latest design/test date). [metadata](https://api.github.com/repos/LunaWithARose/meltybrain-kicad).

2. **Source type and actual inspection:** Hardware design repository and README; README read, firmware not found in inspected listing. Source: [Luna Waller — MeltyBrain PCB](https://github.com/LunaWithARose/meltybrain-kicad).

3. **Robot context:** Robot weight/size/competition: not found. PCB 34 × 34 mm. [README](https://github.com/LunaWithARose/meltybrain-kicad/blob/main/README.md)

4. **Hardware:** Exact MCU/sensor/radio/ESC/LED components: not found in inspected text. Source: [Luna Waller — MeltyBrain PCB](https://github.com/LunaWithARose/meltybrain-kicad).

5. **Heading sensing and placement:** not found.

6. **Angle / RPM algorithm, filtering and rate:** not found.

7. **Drift handling:** not found.

8. **Translation timing and mapping:** not found.

9. **Heading indicator:** not found.

10. **Calibration:** not found.

11. **Controls, modes and failsafes:** not found.

12. **Notable ideas:** Compact custom electronics platform, design goals include power distribution and mechanical integration. [README](https://github.com/LunaWithARose/meltybrain-kicad/blob/main/README.md)

13. **Problems, failures and evidence limits:** Checklist marks layout/routing/DRC review done but fabrication, assembly, electrical tests and integration pending; these are author-reported design milestones. [README](https://github.com/LunaWithARose/meltybrain-kicad/blob/main/README.md)

14. **License:** not found.

<a id="p029"></a>

## P029. DiamondSpectre1 — Antweight MeltyBrain

1. **Name / author / links / activity:** [DiamondSpectre1 — Antweight MeltyBrain](https://github.com/DiamondSpectre1/Antweight-MeltyBrain); owner/attribution as stated above. Repository push activity 2026-07-31 UTC (not necessarily latest design/test date). [metadata](https://api.github.com/repos/DiamondSpectre1/Antweight-MeltyBrain).

2. **Source type and actual inspection:** Design repository with written build/assembly description; read README, no control code read. Source: [DiamondSpectre1 — Antweight MeltyBrain](https://github.com/DiamondSpectre1/Antweight-MeltyBrain).

3. **Robot context:** 1 lb antweight; competition use and overall size not found. [README](https://github.com/DiamondSpectre1/Antweight-MeltyBrain/blob/main/README.md)

4. **Hardware:** Two N20 motors, foam FingerTech wheels/twist hubs, tinyESCs, Adafruit ItsyBitsy (variant unspecified), Adafruit H3LIS331, FS2A/FlySky radio system, 3S LiPo and heading light. [README](https://github.com/DiamondSpectre1/Antweight-MeltyBrain/blob/main/README.md)

5. **Heading sensing and placement:** Accelerometer bolts to polycarbonate base; exact radius/orientation not found. [README](https://github.com/DiamondSpectre1/Antweight-MeltyBrain/blob/main/README.md)

6. **Angle / RPM algorithm, filtering and rate:** not found.

7. **Drift handling:** not found.

8. **Translation timing and mapping:** not found.

9. **Heading indicator:** Heading light mounted away from center for visual feedback; strobe timing not found. [README](https://github.com/DiamondSpectre1/Antweight-MeltyBrain/blob/main/README.md)

10. **Calibration:** not found.

11. **Controls, modes and failsafes:** Claims invertible driving; channel map and failsafe not found. [README](https://github.com/DiamondSpectre1/Antweight-MeltyBrain/blob/main/README.md)

12. **Notable ideas:** Lightweight configuration removes two blades and centers remaining blades vertically. README links actual Onshape CAD and BOM. [README](https://github.com/DiamondSpectre1/Antweight-MeltyBrain/blob/main/README.md)

13. **Problems, failures and evidence limits:** not found.

14. **License:** MIT, repository LICENSE. [LICENSE](https://github.com/DiamondSpectre1/Antweight-MeltyBrain/blob/main/LICENSE)

<a id="p030"></a>

## P030. SpinStroyer — @koko / KoKoOogit

1. **Name / author / links / activity:** [SpinStroyer — @koko / KoKoOogit](https://github.com/KoKoOogit/SpinStroyer); owner/attribution as stated above. Repository push activity 2025-06-14 UTC (not necessarily latest design/test date). [metadata](https://api.github.com/repos/KoKoOogit/SpinStroyer).

2. **Source type and actual inspection:** Design/journal repository; read JOURNAL.md front matter, not control code. [journal](https://github.com/KoKoOogit/SpinStroyer/blob/main/JOURNAL.md)

3. **Robot context:** Antweight; size and competition use not found. Journal creation label 05/13/2025. [journal](https://github.com/KoKoOogit/SpinStroyer/blob/main/JOURNAL.md)

4. **Hardware:** not found.

5. **Heading sensing and placement:** not found.

6. **Angle / RPM algorithm, filtering and rate:** not found.

7. **Drift handling:** not found.

8. **Translation timing and mapping:** not found.

9. **Heading indicator:** not found.

10. **Calibration:** not found.

11. **Controls, modes and failsafes:** not found.

12. **Notable ideas:** not found.

13. **Problems, failures and evidence limits:** Repository describes work in progress; technical failures not found. [repository](https://github.com/KoKoOogit/SpinStroyer)

14. **License:** not found.

<a id="p031"></a>

## P031. Ty Tremblay — MeltyBrainHERO

1. **Name / author / links / activity:** [Ty Tremblay — MeltyBrainHERO](https://github.com/tytremblay/meltybrain); repository push 2018-07-10 UTC. [metadata](https://api.github.com/repos/tytremblay/meltybrain).

2. **Source type and actual inspection:** Code; read Accelerometer.cs, MeltyDrive.cs, Program.cs. [MeltyBrainHERO/MeltyBrainHERO/Program.cs](https://github.com/tytremblay/meltybrain/blob/master/MeltyBrainHERO/MeltyBrainHERO/Program.cs)

3. **Robot context:** Weight, size and competition: not found. Source: [Ty Tremblay — MeltyBrainHERO](https://github.com/tytremblay/meltybrain).

4. **Hardware:** CTRE HERO, two CAN VictorSPX (IDs 1/2), analog accelerometer on Port1 Analog_Pin3, LED class; sensor and motors exact parts not found. [MeltyBrainHERO/MeltyBrainHERO/Program.cs](https://github.com/tytremblay/meltybrain/blob/master/MeltyBrainHERO/MeltyBrainHERO/Program.cs)

5. **Heading sensing and placement:** Configured 2.54 cm sensor-center distance; analog input, exact orientation not found. [MeltyBrainHERO/MeltyBrainHERO/Program.cs](https://github.com/tytremblay/meltybrain/blob/master/MeltyBrainHERO/MeltyBrainHERO/Program.cs)

6. **Angle / RPM algorithm, filtering and rate:** CalculateRpm uses sqrt(acceleration*89445/r_cm); full period 60000/RPM, half-period clamped 5–200 ms. Five-sample averaging in Accelerometer. Critical incompleteness: convertVoltageToAcceleration returns 0 with TODO, so this revision cannot supply measured RPM through that path. [MeltyBrainHERO/MeltyBrainHERO/MeltyDrive.cs](https://github.com/tytremblay/meltybrain/blob/master/MeltyBrainHERO/MeltyBrainHERO/MeltyDrive.cs) [MeltyBrainHERO/MeltyBrainHERO/Accelerometer.cs](https://github.com/tytremblay/meltybrain/blob/master/MeltyBrainHERO/MeltyBrainHERO/Accelerometer.cs)

7. **Drift handling:** Full-period forward/backward scalars and turn multiplier 1-turnVal*TurnScalar (0.01 default); no external reference found. [MeltyBrainHERO/MeltyBrainHERO/MeltyDrive.cs](https://github.com/tytremblay/meltybrain/blob/master/MeltyBrainHERO/MeltyBrainHERO/MeltyDrive.cs)

8. **Translation timing and mapping:** Blocking DoSpin180 phases alternate left/right power during braking window; FlipPower alternates at idle to cancel translation. MaxPower .25 default, full-power-spin branch below 500 RPM, power reduction >5000 RPM or 250 g. Preserve literal BrakingLength=HalfSpinTimeMs*25 as implemented; do not assume intended fraction. [MeltyBrainHERO/MeltyBrainHERO/MeltyDrive.cs](https://github.com/tytremblay/meltybrain/blob/master/MeltyBrainHERO/MeltyBrainHERO/MeltyDrive.cs)

9. **Heading indicator:** LED start at .63 of full period, ends a third-period later; HoldOver carries timing between half rotations. [MeltyBrainHERO/MeltyBrainHERO/MeltyDrive.cs](https://github.com/tytremblay/meltybrain/blob/master/MeltyBrainHERO/MeltyBrainHERO/MeltyDrive.cs) [MeltyBrainHERO/MeltyBrainHERO/Program.cs](https://github.com/tytremblay/meltybrain/blob/master/MeltyBrainHERO/MeltyBrainHERO/Program.cs)

10. **Calibration:** Tare subtracts a baseline, but conversion unfinished; tracking/forward/backward/LED scalars exposed. [MeltyBrainHERO/MeltyBrainHERO/Accelerometer.cs](https://github.com/tytremblay/meltybrain/blob/master/MeltyBrainHERO/MeltyBrainHERO/Accelerometer.cs) [MeltyBrainHERO/MeltyBrainHERO/MeltyDrive.cs](https://github.com/tytremblay/meltybrain/blob/master/MeltyBrainHERO/MeltyBrainHERO/MeltyDrive.cs)

11. **Controls, modes and failsafes:** UI left Y spin throttle, right Y movement, right X steering; CTRE watchdog feed after two half-turns, reconnect Acquire when UI disconnected. Explicit signal-loss motor behavior: not found in inspected code. [MeltyBrainHERO/MeltyBrainHERO/Program.cs](https://github.com/tytremblay/meltybrain/blob/master/MeltyBrainHERO/MeltyBrainHERO/Program.cs)

12. **Notable ideas:** CAN motor controllers and managed C# instead of Arduino implementation. [MeltyBrainHERO/MeltyBrainHERO/MeltyDrive.cs](https://github.com/tytremblay/meltybrain/blob/master/MeltyBrainHERO/MeltyBrainHERO/MeltyDrive.cs)

13. **Problems, failures and evidence limits:** Accelerometer voltage-to-g math explicitly TODO; no author hardware-test outcome found. [MeltyBrainHERO/MeltyBrainHERO/Accelerometer.cs](https://github.com/tytremblay/meltybrain/blob/master/MeltyBrainHERO/MeltyBrainHERO/Accelerometer.cs)

14. **License:** MIT. [LICENSE](https://github.com/tytremblay/meltybrain/blob/master/LICENSE)

<a id="p032"></a>

## P032. Toby Thomson — Python meltybrain simulator

1. **Name / author / links / activity:** [Toby Thomson — Python meltybrain simulator](https://github.com/TobyThomson/meltybrain); repository push 2022-01-19 UTC. [metadata](https://api.github.com/repos/TobyThomson/meltybrain).

2. **Source type and actual inspection:** Code repository; main.py read; software model only, not run here. [main.py](https://github.com/TobyThomson/meltybrain/blob/master/main.py)

3. **Robot context:** Model parameters 250 mm body, 180 mm wheel spacing, 56 mm wheels, 650 KV, 3:1 reduction, 4S; no actual built robot/competition found. [main.py](https://github.com/TobyThomson/meltybrain/blob/master/main.py)

4. **Hardware:** Desktop Python, Pygame and Matplotlib; physical sensor/MCU/radio/ESC not found. [main.py](https://github.com/TobyThomson/meltybrain/blob/master/main.py)

5. **Heading sensing and placement:** No sensor: uses model's internal angle. [main.py](https://github.com/TobyThomson/meltybrain/blob/master/main.py)

6. **Angle / RPM algorithm, filtering and rate:** 30 FPS fixed step; UpdatePosition uses differential-drive arc integration and deltaAngle=(vR-vL)*dt/wheelSpacing, RPM=abs(deltaAngle/dt)*9.5493. [main.py](https://github.com/TobyThomson/meltybrain/blob/master/main.py)

7. **Drift handling:** not found (ideal internal state). Source: [Toby Thomson — Python meltybrain simulator](https://github.com/TobyThomson/meltybrain).

8. **Translation timing and mapping:** Mouse joystick vector rotated into robot frame; CalculateSteeringThrottle compares wheel-to-steer angle with nominal frame spin angle, converts arc correction to wheel speed, scales by stick magnitude; opposite base spin .3, each motor clamped to its spin polarity. [main.py](https://github.com/TobyThomson/meltybrain/blob/master/main.py)

9. **Heading indicator:** Green drawn heading vector and red steering vector, not hardware LEDs. [main.py](https://github.com/TobyThomson/meltybrain/blob/master/main.py)

10. **Calibration:** Editable geometry/KV/battery/spin parameters; physical calibration not found. [main.py](https://github.com/TobyThomson/meltybrain/blob/master/main.py)

11. **Controls, modes and failsafes:** Mouse virtual joystick; no radio-loss model found. [main.py](https://github.com/TobyThomson/meltybrain/blob/master/main.py)

12. **Notable ideas:** Plots wheel velocity and body angular velocity; cites Rossum differential-steering equations. [main.py](https://github.com/TobyThomson/meltybrain/blob/master/main.py)

13. **Problems, failures and evidence limits:** Code catches zero division in straight-line case; author failure narrative not found. [main.py](https://github.com/TobyThomson/meltybrain/blob/master/main.py)

14. **License:** not found.

<a id="p033"></a>

## P033. AVatLeeds/meltybrain

1. **Name / author / links / activity:** [AVatLeeds/meltybrain](https://github.com/AVatLeeds/meltybrain); repository push 2022-01-19 UTC. [metadata](https://api.github.com/repos/AVatLeeds/meltybrain).

2. **Source type and actual inspection:** Code fork; main.py inspected; same tree SHA 46d7e911884548a0719902fdd7ef54e56e23e6cc in both recursive tree responses at research time. No changed files established. [fork metadata](https://api.github.com/repos/AVatLeeds/meltybrain)

3. **Robot context:** Model body 250 mm, wheel spacing 180 mm, wheel diameter 56 mm; actual robot/competition not found. [main.py](https://github.com/AVatLeeds/meltybrain/blob/master/main.py)

4. **Hardware:** Python/Pygame/Matplotlib simulation. [main.py](https://github.com/AVatLeeds/meltybrain/blob/master/main.py)

5. **Heading sensing and placement:** Internal simulated angle, no sensor model found. [main.py](https://github.com/AVatLeeds/meltybrain/blob/master/main.py)

6. **Angle / RPM algorithm, filtering and rate:** 30 FPS differential-drive integration; delta heading from wheel velocity difference, RPM from angle increment. [main.py](https://github.com/AVatLeeds/meltybrain/blob/master/main.py)

7. **Drift handling:** not found.

8. **Translation timing and mapping:** Separate copy implements CalculateSteeringThrottle wheel-arc correction driven by virtual joystick, with opposite spin base and polarity clamps. [main.py](https://github.com/AVatLeeds/meltybrain/blob/master/main.py)

9. **Heading indicator:** Drawn heading/steering vectors, not physical LED. [main.py](https://github.com/AVatLeeds/meltybrain/blob/master/main.py)

10. **Calibration:** Hardcoded geometry/KV/reduction/battery values; hardware calibration not found. [main.py](https://github.com/AVatLeeds/meltybrain/blob/master/main.py)

11. **Controls, modes and failsafes:** Virtual mouse joystick; physical failsafes not found. [main.py](https://github.com/AVatLeeds/meltybrain/blob/master/main.py)

12. **Notable ideas:** Fork retained as separate source entry; changes from upstream: none in observed matching tree. Source: [AVatLeeds/meltybrain](https://github.com/AVatLeeds/meltybrain).

13. **Problems, failures and evidence limits:** not found.

14. **License:** not found.

<a id="p034"></a>

## P034. N0x1an/MeltyBrain

1. **Name / author / links / activity:** [N0x1an/MeltyBrain](https://github.com/N0x1an/MeltyBrain); repository push 2024-10-23 UTC. [metadata](https://api.github.com/repos/N0x1an/MeltyBrain).

2. **Source type and actual inspection:** Code and minimal README; melty.cpp read. [melty.cpp](https://github.com/N0x1an/MeltyBrain/blob/main/melty.cpp)

3. **Robot context:** not found.

4. **Hardware:** Two PWM receiver inputs pins 2/3, outputs 9/10, one NeoPixel pin 11; exact MCU/radio/motors/ESCs/sensors not found. [melty.cpp](https://github.com/N0x1an/MeltyBrain/blob/main/melty.cpp)

5. **Heading sensing and placement:** not found; no heading sensor code in inspected file. Source: [N0x1an/MeltyBrain](https://github.com/N0x1an/MeltyBrain).

6. **Angle / RPM algorithm, filtering and rate:** not found.

7. **Drift handling:** not found.

8. **Translation timing and mapping:** Reads pulseIn 1000–2000 us and maps to analogWrite 0–255 independently; no rotation-synchronous pulse algorithm found. [melty.cpp](https://github.com/N0x1an/MeltyBrain/blob/main/melty.cpp)

9. **Heading indicator:** NeoPixel set constant red; heading strobe not found. [melty.cpp](https://github.com/N0x1an/MeltyBrain/blob/main/melty.cpp)

10. **Calibration:** not found.

11. **Controls, modes and failsafes:** Receiver passthrough example; no explicit stale-signal shutdown found. [melty.cpp](https://github.com/N0x1an/MeltyBrain/blob/main/melty.cpp)

12. **Notable ideas:** Retained as unfinished meltybrain repository, not evidence of working TD. [README.md](https://github.com/N0x1an/MeltyBrain/blob/main/README.md)

13. **Problems, failures and evidence limits:** not found.

14. **License:** MIT. [LICENSE](https://github.com/N0x1an/MeltyBrain/blob/main/LICENSE)

<a id="p035"></a>

## P035. Brainfreeze — FROST Robotics, University of Connecticut

1. **Name / author / links / activity:** [Brainfreeze — FROST Robotics, University of Connecticut](https://github.com/FROSTatUConn/FROST-Meltybrain); repository push 2026-05-21 UTC. [metadata](https://api.github.com/repos/FROSTatUConn/FROST-Meltybrain).

2. **Source type and actual inspection:** Both code and README; read main FROST-Meltybrain.ino and MB_Testing/accelerometer.ino. [README.md](https://github.com/FROSTatUConn/FROST-Meltybrain/blob/main/README.md)

3. **Robot context:** Robot weight/diameter and competed event not found. README mentions another robot's 10-inch pipe as a design reference, not Brainfreeze dimensions. [README.md](https://github.com/FROSTatUConn/FROST-Meltybrain/blob/main/README.md)

4. **Hardware:** README lists Uno/Nano for dev, Teensy 4.0 target, H3LIS331DL, Readytosky 40A BLHeli32 ESCs, drone BLDC motors, FlySky i6x and iA6B, 5V buck. Part selection is author-reported development list. [README.md](https://github.com/FROSTatUConn/FROST-Meltybrain/blob/main/README.md)

5. **Heading sensing and placement:** Experimental runAccelerometer reads three raw axes over I2C and uses raw Z; exact radius/orientation not found. [MB_Testing/accelerometer.ino](https://github.com/FROSTatUConn/FROST-Meltybrain/blob/main/MB_Testing/accelerometer.ino)

6. **Angle / RPM algorithm, filtering and rate:** Test file records consecutive periods/timestamps and extrapolates between measurements. It assigns raw Z directly to robot_period rather than converting via centripetal formula; this is incomplete experimental code, not validated RPM estimation. [MB_Testing/accelerometer.ino](https://github.com/FROSTatUConn/FROST-Meltybrain/blob/main/MB_Testing/accelerometer.ino)

7. **Drift handling:** not found.

8. **Translation timing and mapping:** Main spin-mode branch empty; active implementation is conventional motor control, with movement/motor handling explicitly unfinished in README. [FROST-Meltybrain.ino](https://github.com/FROSTatUConn/FROST-Meltybrain/blob/main/FROST-Meltybrain.ino) [README.md](https://github.com/FROSTatUConn/FROST-Meltybrain/blob/main/README.md)

9. **Heading indicator:** Built-in status LED configured; functioning heading strobe not found in inspected main sketch. [FROST-Meltybrain.ino](https://github.com/FROSTatUConn/FROST-Meltybrain/blob/main/FROST-Meltybrain.ino)

10. **Calibration:** not found.

11. **Controls, modes and failsafes:** iBus channels 0/1 right stick, 2/3 left stick, channel5 SWD safety; safety requires value 1000 after subtracting 1000, otherwise motors off. Idle/tank/spin definitions; watchdog enable is commented out. Signal-loss timing not found. [FROST-Meltybrain.ino](https://github.com/FROSTatUConn/FROST-Meltybrain/blob/main/FROST-Meltybrain.ino)

12. **Notable ideas:** Main file credits SWallen Hardware; test code and derivations collected alongside firmware. [FROST-Meltybrain.ino](https://github.com/FROSTatUConn/FROST-Meltybrain/blob/main/FROST-Meltybrain.ino) [README.md](https://github.com/FROSTatUConn/FROST-Meltybrain/blob/main/README.md)

13. **Problems, failures and evidence limits:** README leaves movement/motors/CAD unchecked; sensor error handling is TODO in test code. [README.md](https://github.com/FROSTatUConn/FROST-Meltybrain/blob/main/README.md) [MB_Testing/accelerometer.ino](https://github.com/FROSTatUConn/FROST-Meltybrain/blob/main/MB_Testing/accelerometer.ino)

14. **License:** MIT. [LICENSE](https://github.com/FROSTatUConn/FROST-Meltybrain/blob/main/LICENSE)

<a id="p036"></a>

## P036. FROST Brainfreeze PCB companion repository

1. **Name / author / links / activity:** [FROST Brainfreeze PCB companion repository](https://github.com/FROSTatUConn/FROST-Meltybrain-PCB); repository push 2025-04-28 UTC. [metadata](https://api.github.com/repos/FROSTatUConn/FROST-Meltybrain-PCB).

2. **Source type and actual inspection:** Hardware design repository; directory listing and README inspected, schematic nets not analyzed. [contents](https://api.github.com/repos/FROSTatUConn/FROST-Meltybrain-PCB/contents)

3. **Robot context:** not found.

4. **Hardware:** KiCad brainfreeze board with separate accelerometer, MOSFET and buck-converter schematic sheets; exact parts not found from inspected listing. [contents](https://api.github.com/repos/FROSTatUConn/FROST-Meltybrain-PCB/contents)

5. **Heading sensing and placement:** not found.

6. **Angle / RPM algorithm, filtering and rate:** not found.

7. **Drift handling:** not found.

8. **Translation timing and mapping:** not found.

9. **Heading indicator:** not found.

10. **Calibration:** not found.

11. **Controls, modes and failsafes:** not found.

12. **Notable ideas:** Companion asset repository, not a separately established physical robot. Source: [FROST Brainfreeze PCB companion repository](https://github.com/FROSTatUConn/FROST-Meltybrain-PCB).

13. **Problems, failures and evidence limits:** not found.

14. **License:** not found.

<a id="p037"></a>

## P037. Sabrebrain / Sabretooth — Owen Fisher

1. **Name / author / links / activity:** [Sabrebrain / Sabretooth — Owen Fisher](https://github.com/kingfisher09/Sabrebrain); repository push 2026-11-07 UTC. [metadata](https://api.github.com/repos/kingfisher09/Sabrebrain).

2. **Source type and actual inspection:** Code; read Sabrebrain.ino and sabre_config.h. [Sabrebrain/Sabrebrain.ino](https://github.com/kingfisher09/Sabrebrain/blob/Master/Sabrebrain/Sabrebrain.ino)

3. **Robot context:** Sabretooth; weight, size, competition not found. Source: [Sabrebrain / Sabretooth — Owen Fisher](https://github.com/kingfisher09/Sabrebrain).

4. **Hardware:** RP2040 code, CRSFforArduino on Serial1, LIS331-family interface (exact sensor variant not found), APA102 strip 23 LEDs, 150 angular slices, OneShot-style PWM 3500 Hz. Motor/ESC models not found. [Sabrebrain/Sabrebrain.ino](https://github.com/kingfisher09/Sabrebrain/blob/Master/Sabrebrain/Sabrebrain.ino) [Sabrebrain/sabre_config.h](https://github.com/kingfisher09/Sabrebrain/blob/Master/Sabrebrain/sabre_config.h)

5. **Heading sensing and placement:** XY acceleration magnitude, configured radial distance 70 mm, I2C 0x19; medium range converted as 200 g. [Sabrebrain/Sabrebrain.ino](https://github.com/kingfisher09/Sabrebrain/blob/Master/Sabrebrain/Sabrebrain.ino)

6. **Angle / RPM algorithm, filtering and rate:** 1000 Hz sensor ODR; IIR filtered_accel=.7*current+.3*previous; omega_deg/s=degrees(sqrt(filtered_accel/(correct*radius))). Main core integrates using measured micros delta and subtracts steering/head_trim; second core reads radio and sensor. [Sabrebrain/Sabrebrain.ino](https://github.com/kingfisher09/Sabrebrain/blob/Master/Sabrebrain/Sabrebrain.ino)

7. **Drift handling:** Manual steering term and head_trim; CORRECT_CH exposed but correct_max=0 in shown settings. Head mode captures atan2 of stick and shifts virtual angle when released. No working compass sensor is shown despite comments. [Sabrebrain/Sabrebrain.ino](https://github.com/kingfisher09/Sabrebrain/blob/Master/Sabrebrain/Sabrebrain.ino)

8. **Translation timing and mapping:** delta = TRANS_SIGN*trans*cos(angle)+SLIP_SIGN*slip*sin(angle); left=spin+delta, right=-spin+delta. Nonspinning arcade mode uses slip±trans with minimum threshold 80. [Sabrebrain/Sabrebrain.ino](https://github.com/kingfisher09/Sabrebrain/blob/Master/Sabrebrain/Sabrebrain.ino)

9. **Heading indicator:** APA102 POV image/video buffers, 23×150 geometry; selectable animation and taunt frame; heading paint_screen(angle). [Sabrebrain/Sabrebrain.ino](https://github.com/kingfisher09/Sabrebrain/blob/Master/Sabrebrain/Sabrebrain.ino) [Sabrebrain/sabre_config.h](https://github.com/kingfisher09/Sabrebrain/blob/Master/Sabrebrain/sabre_config.h)

10. **Calibration:** 70 mm radius, raw x/y offsets +10, head_delay 17, direction signs and trim constants; bench calibration procedure not found. [Sabrebrain/Sabrebrain.ino](https://github.com/kingfisher09/Sabrebrain/blob/Master/Sabrebrain/Sabrebrain.ino)

11. **Controls, modes and failsafes:** Channels 1 slip, 2 translation, 3 spin, 4 heading, 6 correction, 7 heading mode, 8 offset, 9 lights, 10 trim, 11 emote. Declares 100 ms RC stop and 1000 ms watchdog; callback/helper enforcement not fully inspected. [Sabrebrain/Sabrebrain.ino](https://github.com/kingfisher09/Sabrebrain/blob/Master/Sabrebrain/Sabrebrain.ino)

12. **Notable ideas:** Two-core partitioning plus animated POV display and CRSF GPS-format telemetry. [Sabrebrain/Sabrebrain.ino](https://github.com/kingfisher09/Sabrebrain/blob/Master/Sabrebrain/Sabrebrain.ino)

13. **Problems, failures and evidence limits:** Comments note angle wrap fails for >360° negative per iteration, sensitivity of heading selection to released-stick vibration, and accelerometer startup retries. [Sabrebrain/Sabrebrain.ino](https://github.com/kingfisher09/Sabrebrain/blob/Master/Sabrebrain/Sabrebrain.ino)

14. **License:** not found.

<a id="p038"></a>

## P038. Un-Koalified — CU Combat Bots

1. **Name / author / links / activity:** [Un-Koalified — CU Combat Bots](https://github.com/cu-combat-bots/Un-Koalified); repository push 2021-02-03 UTC. [metadata](https://api.github.com/repos/cu-combat-bots/Un-Koalified).

2. **Source type and actual inspection:** Code repository; read README and src/main.cpp, which only constructs Receiver r(0, 1, Serial1), calls setup/loop. [src/main.cpp](https://github.com/cu-combat-bots/Un-Koalified/blob/main/src/main.cpp)

3. **Robot context:** Repository identifies meltybrain; weight/size/competition not found. [metadata](https://api.github.com/repos/cu-combat-bots/Un-Koalified)

4. **Hardware:** Arduino environment/Serial1 receiver wrapper; exact physical parts not found. [src/main.cpp](https://github.com/cu-combat-bots/Un-Koalified/blob/main/src/main.cpp)

5. **Heading sensing and placement:** not found.

6. **Angle / RPM algorithm, filtering and rate:** not found.

7. **Drift handling:** not found.

8. **Translation timing and mapping:** not found in inspected file. Source: [Un-Koalified — CU Combat Bots](https://github.com/cu-combat-bots/Un-Koalified).

9. **Heading indicator:** not found.

10. **Calibration:** not found.

11. **Controls, modes and failsafes:** Receiver wrapper only; mapping/failsafe not found in inspected file. [src/main.cpp](https://github.com/cu-combat-bots/Un-Koalified/blob/main/src/main.cpp)

12. **Notable ideas:** not found.

13. **Problems, failures and evidence limits:** not found.

14. **License:** not found.

<a id="p039"></a>

## P039. Tbarkin121 — STM32F334 MeltyBrain project

1. **Name / author / links / activity:** [Tbarkin121 — STM32F334 MeltyBrain project](https://github.com/Tbarkin121/MeltyBrain); repository push 2018-11-29 UTC. [metadata](https://api.github.com/repos/Tbarkin121/MeltyBrain).

2. **Source type and actual inspection:** Code and setup README; main.c and freertos_tasks.c inspected. [tree](https://github.com/Tbarkin121/MeltyBrain)

3. **Robot context:** not found.

4. **Hardware:** Repository description specifies STM32F334; platform/FreeRTOS drivers, exact melty sensor/radio/ESC/motor not found. [metadata](https://api.github.com/repos/Tbarkin121/MeltyBrain)

5. **Heading sensing and placement:** not found.

6. **Angle / RPM algorithm, filtering and rate:** not found.

7. **Drift handling:** not found.

8. **Translation timing and mapping:** not found.

9. **Heading indicator:** not found.

10. **Calibration:** not found.

11. **Controls, modes and failsafes:** not found.

12. **Notable ideas:** Platform interfaces for ADC/SPI/I2C/UART/PWM/RTOS are present; no operational melty claim established. [tree](https://github.com/Tbarkin121/MeltyBrain)

13. **Problems, failures and evidence limits:** Setup README records toolchain/environment requirements rather than robot validation. [README.md](https://github.com/Tbarkin121/MeltyBrain/blob/master/README.md)

14. **License:** Repository-level permissive license not found. freertos_tasks.c explicitly carries a Portal Instruments proprietary/confidential header; do not treat public availability as an open-source grant. [src/freertos_tasks.c](https://github.com/Tbarkin121/MeltyBrain/blob/master/src/freertos_tasks.c)

<a id="p040"></a>

## P040. PeronaBot — OPRobots

1. **Name / author / links / activity:** [PeronaBot — OPRobots](https://github.com/OPRobots/PeronaBot); push 2025-10-30 UTC. [metadata](https://api.github.com/repos/OPRobots/PeronaBot).

2. **Source type and actual inspection:** Both; README, mpu.cpp and control.cpp read. [README.md](https://github.com/OPRobots/PeronaBot/blob/main/README.md)

3. **Robot context:** 1 lb (~454 g), PLA body and modified 203 mm bicycle brake-disc ring; competition use not found. [README.md](https://github.com/OPRobots/PeronaBot/blob/main/README.md)

4. **Hardware:** ESP32-C3 SuperMini, H3LIS331 ±400 g, Mini360, two 3400 KV brushless motors, LittleBee-Spring BLHeli_S 20A ESCs, two parallel URUAV 3S 300 mAh packs, FlySky iBus, two NeoPixel strips. [README.md](https://github.com/OPRobots/PeronaBot/blob/main/README.md)

5. **Heading sensing and placement:** SPI high-g sensor Y axis; radius parameter MPU_RADIUS, numerical value not found in inspected file. [source_code/src/mpu.cpp](https://github.com/OPRobots/PeronaBot/blob/main/source_code/src/mpu.cpp)

6. **Angle / RPM algorithm, filtering and rate:** ODR 1 kHz; 100-sample zero offset; IIR .5 previous+.5 current, <2 g suppressed. RPM=60/(2pi)*sqrt(abs(g)*g0*1000/(radius_mm*calibration/100)). calc_turn_time gives microseconds per turn above 300 RPM, scaled by steering. No measured control-loop rate found. [source_code/src/mpu.cpp](https://github.com/OPRobots/PeronaBot/blob/main/source_code/src/mpu.cpp) [source_code/src/control.cpp](https://github.com/OPRobots/PeronaBot/blob/main/source_code/src/control.cpp)

7. **Drift handling:** RC calibration knob changes effective radius; steering maps -100..100 to period multiplier 1.1..0.1. No external heading anchor found. [source_code/src/control.cpp](https://github.com/OPRobots/PeronaBot/blob/main/source_code/src/control.cpp)

8. **Translation timing and mapping:** single_turn blocking scheduler; throttle clamped 75%; translation maps ±100 to ±50. Each motor receives a translation*sin(2pi*t/T) term only on the selected half-turn, determined by translation sign; other half remains base spin. [source_code/src/control.cpp](https://github.com/OPRobots/PeronaBot/blob/main/source_code/src/control.cpp)

9. **Heading indicator:** Red heading LEDs for 20% of estimated rotation centered half-turn; yellow below RPM threshold; rainbow in tank mode. [source_code/src/control.cpp](https://github.com/OPRobots/PeronaBot/blob/main/source_code/src/control.cpp)

10. **Calibration:** 100 stationary samples at 1 ms spacing and radius calibration knob. [source_code/src/mpu.cpp](https://github.com/OPRobots/PeronaBot/blob/main/source_code/src/mpu.cpp)

11. **Controls, modes and failsafes:** Melty/tank/debug modes; tank translation limited ±20 and steering±12; debug commands zero motors. Radio-loss policy/channel numbers not found in inspected files. [source_code/src/control.cpp](https://github.com/OPRobots/PeronaBot/blob/main/source_code/src/control.cpp)

12. **Notable ideas:** Recorded acceleration/RPM/throttle via macroarray diagnostic buffer. [source_code/src/control.cpp](https://github.com/OPRobots/PeronaBot/blob/main/source_code/src/control.cpp)

13. **Problems, failures and evidence limits:** Sensor initialization failure enters red-blink infinite loop; author failure narrative not found. [source_code/src/mpu.cpp](https://github.com/OPRobots/PeronaBot/blob/main/source_code/src/mpu.cpp)

14. **License:** GPL-3.0, repository LICENSE. [LICENSE](https://github.com/OPRobots/PeronaBot/blob/main/LICENSE)

<a id="p041"></a>

## P041. LostInTranslation — NRS048

1. **Name / author / links / activity:** [LostInTranslation — NRS048](https://github.com/NRS048/LostInTranslation-MeltyBrain); push 2024-01-01 UTC. [metadata](https://api.github.com/repos/NRS048/LostInTranslation-MeltyBrain).

2. **Source type and actual inspection:** Code plus minimal README; actual Accelerometer.cpp, sketch_nov17a.ino and COR_calculate.ino read. [README.md](https://github.com/NRS048/LostInTranslation-MeltyBrain/blob/main/README.md)

3. **Robot context:** Multiple weight classes intended; actual class, size, competition not found. [README.md](https://github.com/NRS048/LostInTranslation-MeltyBrain/blob/main/README.md)

4. **Hardware:** Teensy 4.1 SD-card references, two SPI accelerometers CS10/9 configurable 100/200/400 g; exact sensor chip not found in inspected text; LED23. Motors/radio/ESC not found. [src/sketch_nov17a/sketch_nov17a.ino](https://github.com/NRS048/LostInTranslation-MeltyBrain/blob/main/src/sketch_nov17a/sketch_nov17a.ino)

5. **Heading sensing and placement:** Combines absolute X/Y as ((|x|+|y|)/2)/.7071 per sensor, averages both; assumes 45° arrangement in comments, configured 3 cm radius. Separate CoR algebra test uses four fixed acceleration values. [src/sketch_nov17a/sketch_nov17a.ino](https://github.com/NRS048/LostInTranslation-MeltyBrain/blob/main/src/sketch_nov17a/sketch_nov17a.ino) [src/COR_calculate/COR_calculate.ino](https://github.com/NRS048/LostInTranslation-MeltyBrain/blob/main/src/COR_calculate/COR_calculate.ino)

6. **Angle / RPM algorithm, filtering and rate:** 100 Hz sensor ODR; loop >10 ms; scalar Kalman predict/update(combined45), RPM=sqrt(filtered_g/(r_cm*11.18))*1000; angle += RPM*6*dt. Important code-inspection finding: if(firstLoop = true) is assignment, so dt always .011 in this revision; no hardware conclusion inferred. [src/sketch_nov17a/sketch_nov17a.ino](https://github.com/NRS048/LostInTranslation-MeltyBrain/blob/main/src/sketch_nov17a/sketch_nov17a.ino)

7. **Drift handling:** Kalman smooths g, not absolute phase; no external heading correction found. [src/sketch_nov17a/sketch_nov17a.ino](https://github.com/NRS048/LostInTranslation-MeltyBrain/blob/main/src/sketch_nov17a/sketch_nov17a.ino)

8. **Translation timing and mapping:** not found.

9. **Heading indicator:** Heading pin23 on between 20° and 70°. [src/sketch_nov17a/sketch_nov17a.ino](https://github.com/NRS048/LostInTranslation-MeltyBrain/blob/main/src/sketch_nov17a/sketch_nov17a.ino)

10. **Calibration:** Stationary calibration aims 0x/0y/1z with adjustable sample count. [src/sketch_nov17a/Accelerometer.cpp](https://github.com/NRS048/LostInTranslation-MeltyBrain/blob/main/src/sketch_nov17a/Accelerometer.cpp)

11. **Controls, modes and failsafes:** not found.

12. **Notable ideas:** Standalone COR_calculate contains an algebraic combined two-sensor RPM expression, but uses fixed a, b, c, d and empty loop; no verified deployed CoR tracking. [src/COR_calculate/COR_calculate.ino](https://github.com/NRS048/LostInTranslation-MeltyBrain/blob/main/src/COR_calculate/COR_calculate.ino)

13. **Problems, failures and evidence limits:** Author notes burst SPI reads caused trouble; six individual-byte reads reportedly ~93 us. Data-ready interrupts TODO. [src/sketch_nov17a/Accelerometer.cpp](https://github.com/NRS048/LostInTranslation-MeltyBrain/blob/main/src/sketch_nov17a/Accelerometer.cpp)

14. **License:** not found.

<a id="p042"></a>

## P042. Persistence of Memory — jkadin

1. **Name / author / links / activity:** [Persistence of Memory — jkadin](https://github.com/jkadin/persistence_of_memory); push 2025-12-08 UTC. [metadata](https://api.github.com/repos/jkadin/persistence_of_memory).

2. **Source type and actual inspection:** Code and README; meltybrain.ino read. [README.md](https://github.com/jkadin/persistence_of_memory/blob/main/README.md)

3. **Robot context:** 30 lb; README reports tank drive and melty/LED working to about45% throttle; dimensions/event not found. [README.md](https://github.com/jkadin/persistence_of_memory/blob/main/README.md)

4. **Hardware:** VescUart motor control/telemetry, AlfredoCRSF ELRS, LIS331-family interface configured 400 g, 25 DotStar pixels, EEPROM CRC8 storage; exact MCU/motors/sensor chip/ESC hardware not found. [meltybrain/meltybrain.ino](https://github.com/jkadin/persistence_of_memory/blob/main/meltybrain/meltybrain.ino)

5. **Heading sensing and placement:** Acceleration mode uses Y/Z magnitude after offsets; radius 67.385 mm plus user offset. Alternative motor eRPM path uses pole and belt-reduction constants then wheel speed/body radius. [meltybrain/meltybrain.ino](https://github.com/jkadin/persistence_of_memory/blob/main/meltybrain/meltybrain.ino)

6. **Angle / RPM algorithm, filtering and rate:** Acceleration RPM=sqrt(g*89445/(radius_cm)); wheel calculation divides eRPM14 then1.6 reduction. eRPM estimate only updated when not translating. Rotation period60000000/RPM then elapsed-time-to-angle. Fixed loop/filter rate not found. [meltybrain/meltybrain.ino](https://github.com/jkadin/persistence_of_memory/blob/main/meltybrain/meltybrain.ino)

7. **Drift handling:** Left-stickX manually changes headerOffset; CH6 changes radius. Source comment proposes future fusion: current selection is a switch, not fusion. [meltybrain/meltybrain.ino](https://github.com/jkadin/persistence_of_memory/blob/main/meltybrain/meltybrain.ino)

8. **Translation timing and mapping:** Right stick atan2 and magnitude; motor duties spinThrottle±cos(heading+stickAngle)*magnitude*.2; right sign reversed for spin. [meltybrain/meltybrain.ino](https://github.com/jkadin/persistence_of_memory/blob/main/meltybrain/meltybrain.ino)

9. **Heading indicator:** ±5° heading window; 25-pixel animation/status and low-voltage check. [meltybrain/meltybrain.ino](https://github.com/jkadin/persistence_of_memory/blob/main/meltybrain/meltybrain.ino)

10. **Calibration:** Offsets in g, nominal67.385 mm radius and CH6 trim; stored accelConfig table scaffold with CRC8, actual completed calibration workflow not established. [meltybrain/meltybrain.ino](https://github.com/jkadin/persistence_of_memory/blob/main/meltybrain/meltybrain.ino)

11. **Controls, modes and failsafes:** CH1 spin scaled.6; low<.05 selects tank mode; CH2 heading, 3/4 translation, 5 sensor source, 6 radius, 7 brightness. Link down zeros both VESC outputs. [meltybrain/meltybrain.ino](https://github.com/jkadin/persistence_of_memory/blob/main/meltybrain/meltybrain.ino)

12. **Notable ideas:** Uses asynchronous VESC telemetry and sensor reads; recognizes translation corrupts wheel-based body-RPM inference. [meltybrain/meltybrain.ino](https://github.com/jkadin/persistence_of_memory/blob/main/meltybrain/meltybrain.ino)

13. **Problems, failures and evidence limits:** WIP, higher-throttle translation not reported working. [README.md](https://github.com/jkadin/persistence_of_memory/blob/main/README.md)

14. **License:** not found.

<a id="p043"></a>

## P043. Shay-Nanigans dual-accelerometer Bluetooth meltybrain

1. **Name / author / links / activity:** [Shay-Nanigans dual-accelerometer Bluetooth meltybrain](https://github.com/Shay-Nanigans/Meltybrain-Combat-Robot); push 2025-04-10 UTC. [metadata](https://api.github.com/repos/Shay-Nanigans/Meltybrain-Combat-Robot).

2. **Source type and actual inspection:** Code; meltybrain.ino read; empty README. [meltybrain.ino](https://github.com/Shay-Nanigans/Meltybrain-Combat-Robot/blob/master/meltybrain.ino)

3. **Robot context:** not found.

4. **Hardware:** ESP32 BluetoothSerial, two LIS331-family sensors at 0x18/19 in400 g range, 1 kHzODR; 4 kHz OneShot125-style LEDC; motor GPIO4/16, LED5. Exact motors/ESC/robot dimensions not found. [meltybrain.ino](https://github.com/Shay-Nanigans/Meltybrain-Combat-Robot/blob/master/meltybrain.ino)

5. **Heading sensing and placement:** Selected Z-axis on both; signed sum/difference chosen with accelSame; accelDist8.23 appears in cm-formula denominator (unit inferred from coefficient). [meltybrain.ino](https://github.com/Shay-Nanigans/Meltybrain-Combat-Robot/blob/master/meltybrain.ino)

6. **Angle / RPM algorithm, filtering and rate:** 10-sample running averages; RPM=sqrt(abs(sum or difference)/(accelDist*.00001118)); lead-like update newest*1.25-oldest/4; period60000000/RPM; angle in tenths-degree integrates micros. Accelerometer reader pinned core0. [meltybrain.ino](https://github.com/Shay-Nanigans/Meltybrain-Combat-Robot/blob/master/meltybrain.ino)

7. **Drift handling:** Manual radius increments1/.1/.01/.001 and LED phase changes; no external reference found. [meltybrain.ino](https://github.com/Shay-Nanigans/Meltybrain-Combat-Robot/blob/master/meltybrain.ino)

8. **Translation timing and mapping:** 45° drive windows180° apart; one motor zero and other full, otherwise opposing spin powers; guide90°, drive indicator10°, LED offset-45°. Bluetooth commanded angle, speed and spin. [meltybrain.ino](https://github.com/Shay-Nanigans/Meltybrain-Combat-Robot/blob/master/meltybrain.ino)

9. **Heading indicator:** Guide arc plus narrower commanded-drive arc. [meltybrain.ino](https://github.com/Shay-Nanigans/Meltybrain-Combat-Robot/blob/master/meltybrain.ino)

10. **Calibration:** Startup sample offsets and serial/Bluetooth radius/phase commands. [meltybrain.ino](https://github.com/Shay-Nanigans/Meltybrain-Combat-Robot/blob/master/meltybrain.ino)

11. **Controls, modes and failsafes:** 3000 ms heartbeat timeout calls freeze and zeros motors; nonspinning cosine/sine arcade mixing; watchdog explicitly disabled. Includes hardcoded startup right-motor pulse—inspection is not a validation of safe arming. [meltybrain.ino](https://github.com/Shay-Nanigans/Meltybrain-Combat-Robot/blob/master/meltybrain.ino)

12. **Notable ideas:** Separate sensor core and acceleration-limit parameters gThrottle370/gMax390. [meltybrain.ino](https://github.com/Shay-Nanigans/Meltybrain-Combat-Robot/blob/master/meltybrain.ino)

13. **Problems, failures and evidence limits:** Author comments mention watchdog needing repair, pulleys melting during spinup, and replacing a restricted sensor-read window with multithreading. [meltybrain.ino](https://github.com/Shay-Nanigans/Meltybrain-Combat-Robot/blob/master/meltybrain.ino)

14. **License:** not found.

<a id="p044"></a>

## P044. Dylan Mays — Personal Meltybrain

1. **Name / author / links / activity:** [Dylan Mays — Personal Meltybrain](https://github.com/Dylan-Mays/Personal-Meltybrain); push 2026-10-16 UTC. [metadata](https://api.github.com/repos/Dylan-Mays/Personal-Meltybrain).

2. **Source type and actual inspection:** Both; code audit/devlog and OpenMelt spin/config files inspected. [docs/code_audit.md](https://github.com/Dylan-Mays/Personal-Meltybrain/blob/main/docs/code_audit.md) [docs/devlog.md](https://github.com/Dylan-Mays/Personal-Meltybrain/blob/main/docs/devlog.md)

3. **Robot context:** Class/full robot size not found; printed spin-test chassis/CAD, full spin/motor test not reported completed by cited devlog. [docs/devlog.md](https://github.com/Dylan-Mays/Personal-Meltybrain/blob/main/docs/devlog.md)

4. **Hardware:** SparkFun Pro Micro ATmega32U4, FlySky FS-iA6B, Adafruit H3LIS331DL, 3S850 mAh battery (changed from planned650 mAh), standard LED; exact motor/ESC models not found in inspected notes. [docs/devlog.md](https://github.com/Dylan-Mays/Personal-Meltybrain/blob/main/docs/devlog.md) [docs/code_audit.md](https://github.com/Dylan-Mays/Personal-Meltybrain/blob/main/docs/code_audit.md)

5. **Heading sensing and placement:** X-axis high-g sensor over I2C; radius EEPROM parameter, exact installed value not found. [docs/code_audit.md](https://github.com/Dylan-Mays/Personal-Meltybrain/blob/main/docs/code_audit.md)

6. **Angle / RPM algorithm, filtering and rate:** OpenMelt-derived centripetal period estimator with integrated rotation scheduler; independent new algorithm not established. Bench author reports±.7 g noise at 400 g range,±.3 g at 200 g. [openmelt/spin_control.cpp](https://github.com/Dylan-Mays/Personal-Meltybrain/blob/main/openmelt/spin_control.cpp) [docs/devlog.md](https://github.com/Dylan-Mays/Personal-Meltybrain/blob/main/docs/devlog.md)

7. **Drift handling:** Effective radius/heading offset calibration and manual trim inherited from OpenMelt code. [openmelt/spin_control.cpp](https://github.com/Dylan-Mays/Personal-Meltybrain/blob/main/openmelt/spin_control.cpp)

8. **Translation timing and mapping:** Rotation-synchronous motor-power scheduling in inherited spin_control; author flags binary throttle must change for brushless and 490 Hz PWM pulse bounds need testing. No validated full-robot translation result found. [docs/code_audit.md](https://github.com/Dylan-Mays/Personal-Meltybrain/blob/main/docs/code_audit.md) [openmelt/spin_control.cpp](https://github.com/Dylan-Mays/Personal-Meltybrain/blob/main/openmelt/spin_control.cpp)

9. **Heading indicator:** Standard LED retained over5V strip; author tested basic LED and noted488 Hz shimmer visibility question. [docs/devlog.md](https://github.com/Dylan-Mays/Personal-Meltybrain/blob/main/docs/devlog.md) [docs/code_audit.md](https://github.com/Dylan-Mays/Personal-Meltybrain/blob/main/docs/code_audit.md)

10. **Calibration:** EEPROM radius/zero offset/LED offset; 0.75s back-stick config entry. [docs/code_audit.md](https://github.com/Dylan-Mays/Personal-Meltybrain/blob/main/docs/code_audit.md)

11. **Controls, modes and failsafes:** Three separate PWM RC channels, not iBus. Author turned transmitter off and observed throttle immediately0; receiver continues pulses after prior binding so freshness alone cannot establish RF link. [docs/devlog.md](https://github.com/Dylan-Mays/Personal-Meltybrain/blob/main/docs/devlog.md)

12. **Notable ideas:** Development log separates bench sensor/RC/LED tests from unrun motor test. [docs/devlog.md](https://github.com/Dylan-Mays/Personal-Meltybrain/blob/main/docs/devlog.md)

13. **Problems, failures and evidence limits:** Possible800 us coast signal may stop ESC initialization; LED shimmer interpretation unresolved; motor sketch written but unrun in Sept7 entry. [docs/code_audit.md](https://github.com/Dylan-Mays/Personal-Meltybrain/blob/main/docs/code_audit.md) [docs/devlog.md](https://github.com/Dylan-Mays/Personal-Meltybrain/blob/main/docs/devlog.md)

14. **License:** Inherited OpenMelt attribution/license text exists; standalone new license not found in inspected documents. [README.md](https://github.com/Dylan-Mays/Personal-Meltybrain/blob/main/README.md)

<a id="p045"></a>

## P045. Unscheduled Disassembly — Dylan and Luke

1. **Name / author / links / activity:** [Unscheduled Disassembly — Dylan and Luke](https://github.com/DylM0nster22/3lb-Melty); push 2025-08-15 UTC. [metadata](https://api.github.com/repos/DylM0nster22/3lb-Melty).

2. **Source type and actual inspection:** Both; README, JOURNAL and spin_control/config inspected. [README.md](https://github.com/DylM0nster22/3lb-Melty/blob/main/README.md) [JOURNAL.md](https://github.com/DylM0nster22/3lb-Melty/blob/main/JOURNAL.md)

3. **Robot context:** 3 lb; 5000 RPM appears as explanatory/target claim, not verified test; competition use not found. [README.md](https://github.com/DylM0nster22/3lb-Melty/blob/main/README.md)

4. **Hardware:** ItsyBitsy32U4 reference progressed to custom ATmega32U4-AU board; H3LIS331, FS2A, PROPDRIVE v2 3542 1250 KV, HGLRC Specter90A8S ESCs, 4S3500 mAh pack in BOM, blueLED. These are listed design choices, not verified assembled hardware. [README.md](https://github.com/DylM0nster22/3lb-Melty/blob/main/README.md) [JOURNAL.md](https://github.com/DylM0nster22/3lb-Melty/blob/main/JOURNAL.md)

5. **Heading sensing and placement:** Single accelerometer/OpenMelt effective radius method; actual installed radius not found. [openmelt/melty_config.h](https://github.com/DylM0nster22/3lb-Melty/blob/main/openmelt/melty_config.h)

6. **Angle / RPM algorithm, filtering and rate:** OpenMelt-derived spin_control rotation-period algorithm; independent modified math not established. [openmelt/spin_control.cpp](https://github.com/DylM0nster22/3lb-Melty/blob/main/openmelt/spin_control.cpp)

7. **Drift handling:** Inherited radius/heading adjustment/manual RC trim. [openmelt/spin_control.cpp](https://github.com/DylM0nster22/3lb-Melty/blob/main/openmelt/spin_control.cpp)

8. **Translation timing and mapping:** OpenMelt rotation-synchronous motor windows; actual ESC waveform validation not found. [openmelt/spin_control.cpp](https://github.com/DylM0nster22/3lb-Melty/blob/main/openmelt/spin_control.cpp) [openmelt/melty_config.h](https://github.com/DylM0nster22/3lb-Melty/blob/main/openmelt/melty_config.h)

9. **Heading indicator:** Blue heading LED in BOM; inherited heading timing. [README.md](https://github.com/DylM0nster22/3lb-Melty/blob/main/README.md) [openmelt/spin_control.cpp](https://github.com/DylM0nster22/3lb-Melty/blob/main/openmelt/spin_control.cpp)

10. **Calibration:** Inherited EEPROM/configuration workflow; calibration results not found. [openmelt/spin_control.cpp](https://github.com/DylM0nster22/3lb-Melty/blob/main/openmelt/spin_control.cpp)

11. **Controls, modes and failsafes:** Inherited OpenMelt controller; own board pin mapping required. Failsafe testing not found. [JOURNAL.md](https://github.com/DylM0nster22/3lb-Melty/blob/main/JOURNAL.md)

12. **Notable ideas:** Custom2oz-copper PCB doubles as power distribution; MOSFET reverse-polarity protection for electronics excluding ESCs. [README.md](https://github.com/DylM0nster22/3lb-Melty/blob/main/README.md)

13. **Problems, failures and evidence limits:** Journal documents multiple PCB attempts, initial wrong MCU selection, receiver pin/mapping corrections and budget/time pressure; code reuse does not establish built/fought status. [JOURNAL.md](https://github.com/DylM0nster22/3lb-Melty/blob/main/JOURNAL.md)

14. **License:** Standalone license not found; inherited OpenMelt licensing text must be checked in source. [openmelt/spin_control.cpp](https://github.com/DylM0nster22/3lb-Melty/blob/main/openmelt/spin_control.cpp)

<a id="p046"></a>

## P046. Rust'N'Roll — lorenzoGT2007

1. **Name / author / links / activity:** [Rust'N'Roll — lorenzoGT2007](https://github.com/lorenzoGT2007/RustnRoll-150g-meltybrain-teensy-4.0); push 2026-08-29 UTC. [metadata](https://api.github.com/repos/lorenzoGT2007/RustnRoll-150g-meltybrain-teensy-4.0).

2. **Source type and actual inspection:** Code; main_Degrees_Singlemotor_Sinusoidal.cpp and README read, not executed. [src/main_Degrees_Singlemotor_Sinusoidal.cpp](https://github.com/lorenzoGT2007/RustnRoll-150g-meltybrain-teensy-4.0/blob/main/src/main_Degrees_Singlemotor_Sinusoidal.cpp)

3. **Robot context:** 150 g in title; author code header reports maximum measured3500 RPM; event/size not found. [src/main_Degrees_Singlemotor_Sinusoidal.cpp](https://github.com/lorenzoGT2007/RustnRoll-150g-meltybrain-teensy-4.0/blob/main/src/main_Degrees_Singlemotor_Sinusoidal.cpp)

4. **Hardware:** Teensy 4.0, H3LIS331 via SPI400 g/1 kHz, PPM input PulsePosition, two ESC outputs, transistor-drivenLED. Motor/ESC part numbers not found. [src/main_Degrees_Singlemotor_Sinusoidal.cpp](https://github.com/lorenzoGT2007/RustnRoll-150g-meltybrain-teensy-4.0/blob/main/src/main_Degrees_Singlemotor_Sinusoidal.cpp)

5. **Heading sensing and placement:** 45° XY average magnitude sqrt2*abs((ax+ay)/2), radius default.0473m, RC trim .02–.07m. [src/main_Degrees_Singlemotor_Sinusoidal.cpp](https://github.com/lorenzoGT2007/RustnRoll-150g-meltybrain-teensy-4.0/blob/main/src/main_Degrees_Singlemotor_Sinusoidal.cpp)

6. **Angle / RPM algorithm, filtering and rate:** sqrt(a/r) angular rate with measured micros interval; RPM from period. Motor-output ISR period100 us (10 kHz); sensor ODR1 kHz distinct. [src/main_Degrees_Singlemotor_Sinusoidal.cpp](https://github.com/lorenzoGT2007/RustnRoll-150g-meltybrain-teensy-4.0/blob/main/src/main_Degrees_Singlemotor_Sinusoidal.cpp)

7. **Drift handling:** CH1 moves virtual heading; CH5 radius adjusts drift. No absolute reference found. [src/main_Degrees_Singlemotor_Sinusoidal.cpp](https://github.com/lorenzoGT2007/RustnRoll-150g-meltybrain-teensy-4.0/blob/main/src/main_Degrees_Singlemotor_Sinusoidal.cpp)

8. **Translation timing and mapping:** PID sets base RPM throttle; only motor1 gets shaped sine, motor2 base. Pulse width increases15°→345° withRPM; sine is shifted/scaled by width and clipped, phase linearly interpolated from RPM/advance table. Translation activates/deactivates at waveform peaks using derivative sign, gated by |CH2|>200. [src/main_Degrees_Singlemotor_Sinusoidal.cpp](https://github.com/lorenzoGT2007/RustnRoll-150g-meltybrain-teensy-4.0/blob/main/src/main_Degrees_Singlemotor_Sinusoidal.cpp)

9. **Heading indicator:** 40° heading line; calibration varies line width with RPM error or active PID coefficient. [src/main_Degrees_Singlemotor_Sinusoidal.cpp](https://github.com/lorenzoGT2007/RustnRoll-150g-meltybrain-teensy-4.0/blob/main/src/main_Degrees_Singlemotor_Sinusoidal.cpp)

10. **Calibration:** CH4 held middle3s starts motor phase calibration; low3s startsPID tuning; four nonzero phase points1375/1750/2125/2500 RPM plus zero; CH5 chooses angle/gains, EEPROM saves. [src/main_Degrees_Singlemotor_Sinusoidal.cpp](https://github.com/lorenzoGT2007/RustnRoll-150g-meltybrain-teensy-4.0/blob/main/src/main_Degrees_Singlemotor_Sinusoidal.cpp)

11. **Controls, modes and failsafes:** CH1 steering/heading, CH2 forward-back, CH3 RPM/zero tank mode, CH4 cal, CH5 trim, CH6 spin direction/inversion. After1s missingPPM controls neutralize. [src/main_Degrees_Singlemotor_Sinusoidal.cpp](https://github.com/lorenzoGT2007/RustnRoll-150g-meltybrain-teensy-4.0/blob/main/src/main_Degrees_Singlemotor_Sinusoidal.cpp)

12. **Notable ideas:** RPM-dependent pulse-width and phase advance plus switching calibration encoded byLED width. [src/main_Degrees_Singlemotor_Sinusoidal.cpp](https://github.com/lorenzoGT2007/RustnRoll-150g-meltybrain-teensy-4.0/blob/main/src/main_Degrees_Singlemotor_Sinusoidal.cpp)

13. **Problems, failures and evidence limits:** Notes constrain maximum width below 355° to avoid numerical overflow of modulation; no separate failure narrative found. [src/main_Degrees_Singlemotor_Sinusoidal.cpp](https://github.com/lorenzoGT2007/RustnRoll-150g-meltybrain-teensy-4.0/blob/main/src/main_Degrees_Singlemotor_Sinusoidal.cpp)

14. **License:** not found.

<a id="p047"></a>

## P047. Sweati — Liam Long

1. **Name / author / links / activity:** [Sweati — Liam Long](https://github.com/LiamLong360/Sweati---3lb-MeltyBrain-Combat-Robot-Manipulating-Translational-Drift); push 2026-05-01 UTC. [metadata](https://api.github.com/repos/LiamLong360/Sweati---3lb-MeltyBrain-Combat-Robot-Manipulating-Translational-Drift).

2. **Source type and actual inspection:** Both; implementation and AccelH3LIS331.cpp read. [README.md](https://github.com/LiamLong360/Sweati---3lb-MeltyBrain-Combat-Robot-Manipulating-Translational-Drift/blob/main/README.md)

3. **Robot context:** 3 lb; README links demonstration video, not independently viewed; event/size not found. [README.md](https://github.com/LiamLong360/Sweati---3lb-MeltyBrain-Combat-Robot-Manipulating-Translational-Drift/blob/main/README.md)

4. **Hardware:** Teensy 4.0 per README (diagram mentions4.1), two H3LIS331DL SPI, NeoPixel/WS2812Serial LEDs, PWM ESCs, 3S LiPo. Sensor code actually sets100 g, despite README describing400 g parts; version distinction retained. [README.md](https://github.com/LiamLong360/Sweati---3lb-MeltyBrain-Combat-Robot-Manipulating-Translational-Drift/blob/main/README.md) [AccelH3LIS331.cpp](https://github.com/LiamLong360/Sweati---3lb-MeltyBrain-Combat-Robot-Manipulating-Translational-Drift/blob/main/AccelH3LIS331.cpp)

5. **Heading sensing and placement:** TwoXY magnitudes, assumes equal distance from spin center; SENSOR_RADIUS .0508m. Top-level calls same parameter sensor separation, but calculation uses it as each sensor radius. [AccelH3LIS331.cpp](https://github.com/LiamLong360/Sweati---3lb-MeltyBrain-Combat-Robot-Manipulating-Translational-Drift/blob/main/AccelH3LIS331.cpp) [00_Implementation.ino](https://github.com/LiamLong360/Sweati---3lb-MeltyBrain-Combat-Robot-Manipulating-Translational-Drift/blob/main/00_Implementation.ino)

6. **Angle / RPM algorithm, filtering and rate:** 1 kHz cap; per-sensor omega=sqrt(sqrt(ax²+ay²)/radius), average omegas; trapezoidal measured-dt integration; below 60 RPM resets angle. No subtractive common-mode cancellation implemented in this code. [AccelH3LIS331.cpp](https://github.com/LiamLong360/Sweati---3lb-MeltyBrain-Combat-Robot-Manipulating-Translational-Drift/blob/main/AccelH3LIS331.cpp)

7. **Drift handling:** Aileron manually changes headingOffset up to 180°/s; radius calibration persists. [00_Implementation.ino](https://github.com/LiamLong360/Sweati---3lb-MeltyBrain-Combat-Robot-Manipulating-Translational-Drift/blob/main/00_Implementation.ino)

8. **Translation timing and mapping:** Above60 RPM, mix=cos(currentAngle-headingOffset)*translationScale*200 us, motor1=thr+mix, motor2=thr-mix, clamped1016–2016 us. Below threshold equal passthrough. [00_Implementation.ino](https://github.com/LiamLong360/Sweati---3lb-MeltyBrain-Combat-Robot-Manipulating-Translational-Drift/blob/main/00_Implementation.ino)

9. **Heading indicator:** Heading-synchronized NeoPixel updater; idle/calibration/locked status colors; exact heading arc width not found in inspected files. [00_Implementation.ino](https://github.com/LiamLong360/Sweati---3lb-MeltyBrain-Combat-Robot-Manipulating-Translational-Drift/blob/main/00_Implementation.ino)

10. **Calibration:** Idle throttle+max elevon3s enters cal; aileron adjusts radius1 mm/s, EEPROM saves; exit elevon minimum. Motors at 1040 us in calibration, labelled idle in source—actual ESC behavior unverified. [00_Implementation.ino](https://github.com/LiamLong360/Sweati---3lb-MeltyBrain-Combat-Robot-Manipulating-Translational-Drift/blob/main/00_Implementation.ino)

11. **Controls, modes and failsafes:** Throttle/elevon/aileron PWM snapshots.30s with no channel changing>=100 us locks until power cycle. This is inactivity detection, not confirmed immediate radio-loss detection. Other RX freshness handling not established. [00_Implementation.ino](https://github.com/LiamLong360/Sweati---3lb-MeltyBrain-Combat-Robot-Manipulating-Translational-Drift/blob/main/00_Implementation.ino)

12. **Notable ideas:** Explicit trapezoidal integration and persisted single geometry parameter. [AccelH3LIS331.cpp](https://github.com/LiamLong360/Sweati---3lb-MeltyBrain-Combat-Robot-Manipulating-Translational-Drift/blob/main/AccelH3LIS331.cpp)

13. **Problems, failures and evidence limits:** README discusses current/thermal limitations; source/README100 g-vs400 g and radius-vs-separation mismatches are confirmed by inspection, not author-tested diagnoses. [README.md](https://github.com/LiamLong360/Sweati---3lb-MeltyBrain-Combat-Robot-Manipulating-Translational-Drift/blob/main/README.md) [AccelH3LIS331.cpp](https://github.com/LiamLong360/Sweati---3lb-MeltyBrain-Combat-Robot-Manipulating-Translational-Drift/blob/main/AccelH3LIS331.cpp)

14. **License:** not found.

<a id="p048"></a>

## P048. q314tracy — CircuitPython melty robot

1. **Name / author / links / activity:** [q314tracy — CircuitPython melty robot](https://github.com/q314tracy/melty_robot); push 2025-06-01 UTC. [metadata](https://api.github.com/repos/q314tracy/melty_robot).

2. **Source type and actual inspection:** Code; code.py read. [code.py](https://github.com/q314tracy/melty_robot/blob/main/code.py)

3. **Robot context:** not found.

4. **Hardware:** CircuitPython board unspecified, RFM69HCW915 MHz, H3LIS331 I2C400 g/1 kHz. Motor hardware not found. [code.py](https://github.com/q314tracy/melty_robot/blob/main/code.py)

5. **Heading sensing and placement:** X acceleration, mounting offset.05m explicitly assumed in source. [code.py](https://github.com/q314tracy/melty_robot/blob/main/code.py)

6. **Angle / RPM algorithm, filtering and rate:** 5000-sample offsets, IIRalpha.03, RPM=sqrt(abs(ax)/.05)*60/(2pi), below 100 RPM forced0; angular_dir remains initialized0. No working heading integration found. [code.py](https://github.com/q314tracy/melty_robot/blob/main/code.py)

7. **Drift handling:** not found.

8. **Translation timing and mapping:** Four motor angle offsets±pi/4,±3pi/4 declared but power output/translation scheduling not found. [code.py](https://github.com/q314tracy/melty_robot/blob/main/code.py)

9. **Heading indicator:** Onboard debug LED; heading indicator not found. [code.py](https://github.com/q314tracy/melty_robot/blob/main/code.py)

10. **Calibration:** 5000-sample startup zero-axis calibration. [code.py](https://github.com/q314tracy/melty_robot/blob/main/code.py)

11. **Controls, modes and failsafes:** JSON commands tx, ty, en, sp; receive task commented out in main, telemetry nominal 100 Hz; radio receive absence leaves old state unchanged. End-to-end failsafe not found. [code.py](https://github.com/q314tracy/melty_robot/blob/main/code.py)

12. **Notable ideas:** Separate telemetry transmitter and simulation repositories. [code.py](https://github.com/q314tracy/melty_robot/blob/main/code.py)

13. **Problems, failures and evidence limits:** Comments mention64-byte radio payload limit; no hardware validation found. [code.py](https://github.com/q314tracy/melty_robot/blob/main/code.py)

14. **License:** not found.

<a id="p049"></a>

## P049. q314tracy — melty transmitter

1. **Name / author / links / activity:** [q314tracy — melty transmitter](https://github.com/q314tracy/melty_transmitter); push 2025-06-01 UTC. [metadata](https://api.github.com/repos/q314tracy/melty_transmitter).

2. **Source type and actual inspection:** Code; code.py read; companion controller, not independently established robot. [code.py](https://github.com/q314tracy/melty_transmitter/blob/main/code.py)

3. **Robot context:** not found.

4. **Hardware:** CircuitPython, Nunchuk, I2C SSD1306 128×64OLED, RFM69HCW915 MHz. Board model not found. [code.py](https://github.com/q314tracy/melty_transmitter/blob/main/code.py)

5. **Heading sensing and placement:** not found.

6. **Angle / RPM algorithm, filtering and rate:** not found.

7. **Drift handling:** not found.

8. **Translation timing and mapping:** not found.

9. **Heading indicator:** not found.

10. **Calibration:** not found.

11. **Controls, modes and failsafes:** Joystick normalized±1 with.05deadband; Z enable, C fast/slow; 100 ms IO/display task, JSON tx/ty/en/sp. Actual transmit scheduling commented out; receive telemetry active. Robot shutdown not implemented here. [code.py](https://github.com/q314tracy/melty_transmitter/blob/main/code.py)

12. **Notable ideas:** Displays angular velocity/direction, battery and loop timing. [code.py](https://github.com/q314tracy/melty_transmitter/blob/main/code.py)

13. **Problems, failures and evidence limits:** Payload must stay within~62bytes; catches overflow assertions. [code.py](https://github.com/q314tracy/melty_transmitter/blob/main/code.py)

14. **License:** not found.

<a id="p050"></a>

## P050. q314tracy — Melty Simulations

1. **Name / author / links / activity:** [q314tracy — Melty Simulations](https://github.com/q314tracy/Melty-Simulations); push 2025-05-27 UTC. [metadata](https://api.github.com/repos/q314tracy/Melty-Simulations).

2. **Source type and actual inspection:** Code; meltysim.py and toflocalizationsim.py read, not executed. [meltysim.py](https://github.com/q314tracy/Melty-Simulations/blob/main/meltysim.py) [toflocalizationsim.py](https://github.com/q314tracy/Melty-Simulations/blob/main/toflocalizationsim.py)

3. **Robot context:** Simulated10m-square arena; built robot class/size not found. [toflocalizationsim.py](https://github.com/q314tracy/Melty-Simulations/blob/main/toflocalizationsim.py)

4. **Hardware:** Python/Pygame, NumPy, SciPy; ToF model only, exact physical sensor not found. [toflocalizationsim.py](https://github.com/q314tracy/Melty-Simulations/blob/main/toflocalizationsim.py)

5. **Heading sensing and placement:** Three simulated wall-range rays at 0°, 120°,-120°, with1 cm Gaussian noise. [toflocalizationsim.py](https://github.com/q314tracy/Melty-Simulations/blob/main/toflocalizationsim.py)

6. **Angle / RPM algorithm, filtering and rate:** SciPy minimize solves x, y, theta by minimizing squared distances of inferred endpoints to nearest square wall, bounded0..L and 0..2pi, initial guess arena center.30FPS visualization; not high-RPM hardware proof. [toflocalizationsim.py](https://github.com/q314tracy/Melty-Simulations/blob/main/toflocalizationsim.py)

7. **Drift handling:** Arena wall geometry used as external pose constraint in simulation. [toflocalizationsim.py](https://github.com/q314tracy/Melty-Simulations/blob/main/toflocalizationsim.py)

8. **Translation timing and mapping:** Five equally spaced tangential force points; per-point max(0, sin(relative bearing))*stick magnitude. WASD desired atan2 heading, 60FPS animation. [meltysim.py](https://github.com/q314tracy/Melty-Simulations/blob/main/meltysim.py)

9. **Heading indicator:** Drawn desired vector, net force, torque arc; physicalLED not found. [meltysim.py](https://github.com/q314tracy/Melty-Simulations/blob/main/meltysim.py)

10. **Calibration:** not found.

11. **Controls, modes and failsafes:** not found.

12. **Notable ideas:** Explores environmental range references separately from inertial acceleration. [toflocalizationsim.py](https://github.com/q314tracy/Melty-Simulations/blob/main/toflocalizationsim.py)

13. **Problems, failures and evidence limits:** not found.

14. **License:** not found.

<a id="p051"></a>

## P051. UCR/HCR — Melty Brain

1. **Name / author / links / activity:** [UCR/HCR — Melty Brain](https://github.com/Combat-Robotics-UCR/Melty-Brain); push 2026-10-18 UTC. [metadata](https://api.github.com/repos/Combat-Robotics-UCR/Melty-Brain).

2. **Source type and actual inspection:** Code; Melty.h and Melty_Brain.ino read; function implementations not found in inspected tree (declarations alone do not establish math). [Melty.h](https://github.com/Combat-Robotics-UCR/Melty-Brain/blob/main/Melty.h) [Melty_Brain.ino](https://github.com/Combat-Robotics-UCR/Melty-Brain/blob/main/Melty_Brain.ino)

3. **Robot context:** not found.

4. **Hardware:** ESP32, BNO08x-family IMU overSPI, SD card, LED25. Exact BNO part variant, radio, motors/ESCs not found. [Melty.h](https://github.com/Combat-Robotics-UCR/Melty-Brain/blob/main/Melty.h)

5. **Heading sensing and placement:** gyroZ and accelerationXY fields; radius.037282m. Exact selection/fusion algorithm not found in inspected declarations. [Melty.h](https://github.com/Combat-Robotics-UCR/Melty-Brain/blob/main/Melty.h)

6. **Angle / RPM algorithm, filtering and rate:** Calls read_IMU/update_heading/pulse_LED/write_SD_card; math/update rate not found. [Melty_Brain.ino](https://github.com/Combat-Robotics-UCR/Melty-Brain/blob/main/Melty_Brain.ino)

7. **Drift handling:** not found.

8. **Translation timing and mapping:** not found.

9. **Heading indicator:** Declared.5rad blink range and once-per-turn pulse intent, implementation not found. [Melty.h](https://github.com/Combat-Robotics-UCR/Melty-Brain/blob/main/Melty.h)

10. **Calibration:** Radius/LED configuration declarations commented out. [Melty.h](https://github.com/Combat-Robotics-UCR/Melty-Brain/blob/main/Melty.h)

11. **Controls, modes and failsafes:** ErrorLED patterns coverIMU connection, SD mount/open/append; motor/radio failsafes not found. [README.md](https://github.com/Combat-Robotics-UCR/Melty-Brain/blob/main/README.md)

12. **Notable ideas:** not found.

13. **Problems, failures and evidence limits:** Author log says IMU stops logging; switched toSPI, solution stillTBD; gyro/accel need independent performance characterization. [Melty_Brain.ino](https://github.com/Combat-Robotics-UCR/Melty-Brain/blob/main/Melty_Brain.ino)

14. **License:** not found.

<a id="p052"></a>

## P052. StanBeru77 — UCR Melty Brain fork

1. **Name / author / links / activity:** [StanBeru77 — UCR Melty Brain fork](https://github.com/StanBeru77/Melty-Brain); push 2026-11-04 UTC. [metadata](https://api.github.com/repos/StanBeru77/Melty-Brain).

2. **Source type and actual inspection:** GitHub fork ofCombat-Robotics-UCR/Melty-Brain; README and matching tree inspected. [metadata](https://api.github.com/repos/StanBeru77/Melty-Brain)

3. **Robot context:** not found.

4. **Hardware:** ESP32/BNO08x interface, SD card, LED25 in fork header. [Melty.h](https://github.com/StanBeru77/Melty-Brain/blob/main/Melty.h)

5. **Heading sensing and placement:** Header contains gyroZ/XY acceleration, radius.037282m; mount not found. [Melty.h](https://github.com/StanBeru77/Melty-Brain/blob/main/Melty.h)

6. **Angle / RPM algorithm, filtering and rate:** Source tree matched UCR tree91860cd1f92f40880ddfbee53efc9d3c8f21d460 at research time; control-function bodies not found. [tree](https://api.github.com/repos/StanBeru77/Melty-Brain/git/trees/main?recursive=1)

7. **Drift handling:** not found.

8. **Translation timing and mapping:** not found.

9. **Heading indicator:** Declared.5rad LED window; implementation not found. [Melty.h](https://github.com/StanBeru77/Melty-Brain/blob/main/Melty.h)

10. **Calibration:** not found.

11. **Controls, modes and failsafes:** Same fourSD/IMU error blink categories. [README.md](https://github.com/StanBeru77/Melty-Brain/blob/main/README.md)

12. **Notable ideas:** Separate fork; tree matching establishes no content changes in observed snapshot, despite later repository push timestamp. Source: [StanBeru77 — UCR Melty Brain fork](https://github.com/StanBeru77/Melty-Brain).

13. **Problems, failures and evidence limits:** Retains IMU stops logging/SPI change unresolved note. [Melty_Brain.ino](https://github.com/StanBeru77/Melty-Brain/blob/main/Melty_Brain.ino)

14. **License:** not found.

<a id="p053"></a>

## P053. Doomba — yahirconejo-cpu

1. **Name / author / links / activity:** [Doomba — yahirconejo-cpu](https://github.com/yahirconejo-cpu/Melty-Brain); push 2025-06-17 UTC. [metadata](https://api.github.com/repos/yahirconejo-cpu/Melty-Brain).

2. **Source type and actual inspection:** Code; DoombaReciver.ino and sender source read. [DoombaReciver/DoombaReciver.ino](https://github.com/yahirconejo-cpu/Melty-Brain/blob/main/DoombaReciver/DoombaReciver.ino)

3. **Robot context:** not found.

4. **Hardware:** ESP32, ESP-NOW, Adafruit LIS3DH4 g, ESP32Servo ESCs GPIO13/12, LED23; exact drive hardware not found. [DoombaReciver/DoombaReciver.ino](https://github.com/yahirconejo-cpu/Melty-Brain/blob/main/DoombaReciver/DoombaReciver.ino)

5. **Heading sensing and placement:** LIS3DH X, radius11 cm; sensor 4 g setting confirmed by code, not assumed suitable at combat RPM. [DoombaReciver/DoombaReciver.ino](https://github.com/yahirconejo-cpu/Melty-Brain/blob/main/DoombaReciver/DoombaReciver.ino)

6. **Angle / RPM algorithm, filtering and rate:** RPM=sqrt(abs(g-offset)*89445.43828/11); micros-based estimated rotation-progress loop adjusts estimated period. No measured rate/filter beyond offset found. [DoombaReciver/DoombaReciver.ino](https://github.com/yahirconejo-cpu/Melty-Brain/blob/main/DoombaReciver/DoombaReciver.ino)

7. **Drift handling:** not found.

8. **Translation timing and mapping:** Despite heading timing, loop writes equal incoming throttle to both ESCs; no directional spin-phase motor modulation found. Tank mix entirely commented as bad/example code. [DoombaReciver/DoombaReciver.ino](https://github.com/yahirconejo-cpu/Melty-Brain/blob/main/DoombaReciver/DoombaReciver.ino)

9. **Heading indicator:** LED on near first/last10% rotation. [DoombaReciver/DoombaReciver.ino](https://github.com/yahirconejo-cpu/Melty-Brain/blob/main/DoombaReciver/DoombaReciver.ino)

10. **Calibration:** 200 readings, 1 ms apart, zero offset. [DoombaReciver/DoombaReciver.ino](https://github.com/yahirconejo-cpu/Melty-Brain/blob/main/DoombaReciver/DoombaReciver.ino)

11. **Controls, modes and failsafes:** ESP-NOW struct throttle, leftRight, tankMode; no freshness timeout found. [DoombaReciver/DoombaReciver.ino](https://github.com/yahirconejo-cpu/Melty-Brain/blob/main/DoombaReciver/DoombaReciver.ino)

12. **Notable ideas:** not found.

13. **Problems, failures and evidence limits:** Author explicitly requests better tank mode; current code incomplete. [DoombaReciver/DoombaReciver.ino](https://github.com/yahirconejo-cpu/Melty-Brain/blob/main/DoombaReciver/DoombaReciver.ino)

14. **License:** not found.

<a id="p054"></a>

## P054. Max-Med — Melty Brain Code

1. **Name / author / links / activity:** [Max-Med — Melty Brain Code](https://github.com/Max-Med/Melty-Brain-Code); push 2015-04-18 UTC. [metadata](https://api.github.com/repos/Max-Med/Melty-Brain-Code).

2. **Source type and actual inspection:** Code; melty_brains.ino read. [melty_brains/melty_brains.ino](https://github.com/Max-Med/Melty-Brain-Code/blob/master/melty_brains/melty_brains.ino)

3. **Robot context:** not found.

4. **Hardware:** AVR/Arduino Nano pins referenced; analog accelerometer A0, 3 motor PWM outputs 3/5/6, LED2, six RC channels. Exact sensor/drive parts not found. [melty_brains/melty_brains.ino](https://github.com/Max-Med/Melty-Brain-Code/blob/master/melty_brains/melty_brains.ino)

5. **Heading sensing and placement:** Analog acceleration mapped 0..1000→-4934..9707, configured radius.03m; physical mounting not found. [melty_brains/melty_brains.ino](https://github.com/Max-Med/Melty-Brain-Code/blob/master/melty_brains/melty_brains.ino)

6. **Angle / RPM algorithm, filtering and rate:** Timer1 ticks 4 us, nominal 100 ms control frame; currentAngleSet adds sqrt(accel/(100*r))*elapsed_ms, wrap 6283mrad; unit treatment unvalidated. headingSet manual quadrant arctan from RC0/2. [melty_brains/melty_brains.ino](https://github.com/Max-Med/Melty-Brain-Code/blob/master/melty_brains/melty_brains.ino)

7. **Drift handling:** Rudder correction fraction exists but default 0; no automatic anchor found. [melty_brains/melty_brains.ino](https://github.com/Max-Med/Melty-Brain-Code/blob/master/melty_brains/melty_brains.ino)

8. **Translation timing and mapping:** Three motor phase offsets 0/2.094/4.188rad; switches motors off in approximately180° direction windows, else base throttle. Small translation input <50 gives all-on. [melty_brains/melty_brains.ino](https://github.com/Max-Med/Melty-Brain-Code/blob/master/melty_brains/melty_brains.ino)

9. **Heading indicator:** LED ±45° about zero. [melty_brains/melty_brains.ino](https://github.com/Max-Med/Melty-Brain-Code/blob/master/melty_brains/melty_brains.ino)

10. **Calibration:** Hardcoded acceleration/radius/RC mapping; calibration procedure not found. [melty_brains/melty_brains.ino](https://github.com/Max-Med/Melty-Brain-Code/blob/master/melty_brains/melty_brains.ino)

11. **Controls, modes and failsafes:** RC pin-change interrupts decode six channels; throttle RC5, direction RC0/2, trim RC4. Explicit stale-signal shutdown not found. [melty_brains/melty_brains.ino](https://github.com/Max-Med/Melty-Brain-Code/blob/master/melty_brains/melty_brains.ino)

12. **Notable ideas:** Three-wheel120° phased gates. [melty_brains/melty_brains.ino](https://github.com/Max-Med/Melty-Brain-Code/blob/master/melty_brains/melty_brains.ino)

13. **Problems, failures and evidence limits:** No author narrative; inspected previousRc[5] access on a 5-element array and zero/negative-root possibilities mean working behavior not established. These are inspection concerns, not reproduced failures. [melty_brains/melty_brains.ino](https://github.com/Max-Med/Melty-Brain-Code/blob/master/melty_brains/melty_brains.ino)

14. **License:** not found.

<a id="p055"></a>

## P055. jjrreett — melty-brain planning project

1. **Name / author / links / activity:** [jjrreett — melty-brain planning project](https://github.com/jjrreett/melty-brain); push 2023-07-05 UTC. [metadata](https://api.github.com/repos/jjrreett/melty-brain).

2. **Source type and actual inspection:** Design notes, not implementation read. [design/notes.md](https://github.com/jjrreett/melty-brain/blob/main/design/notes.md)

3. **Robot context:** Beetleweight considered after antweight target deemed difficult; no built robot/event found. [design/notes.md](https://github.com/jjrreett/melty-brain/blob/main/design/notes.md)

4. **Hardware:** One/three-wheel and standard/omni choices considered; components not found. [design/notes.md](https://github.com/jjrreett/melty-brain/blob/main/design/notes.md)

5. **Heading sensing and placement:** not found.

6. **Angle / RPM algorithm, filtering and rate:** Kalman filtering and model-based SIL are planning goals only. [design/notes.md](https://github.com/jjrreett/melty-brain/blob/main/design/notes.md)

7. **Drift handling:** not found.

8. **Translation timing and mapping:** not found.

9. **Heading indicator:** not found.

10. **Calibration:** not found.

11. **Controls, modes and failsafes:** not found.

12. **Notable ideas:** Explores sword, hammer, ring layouts and one/three-wheel alternatives. [design/notes.md](https://github.com/jjrreett/melty-brain/blob/main/design/notes.md)

13. **Problems, failures and evidence limits:** not found.

14. **License:** not found.

<a id="p056"></a>

## P056. Sarcophilus — negativeview

1. **Name / author / links / activity:** [Sarcophilus — negativeview](https://github.com/negativeview/sarcophilus); push 2023-11-29 UTC. [metadata](https://api.github.com/repos/negativeview/sarcophilus).

2. **Source type and actual inspection:** Repository/README inspected; control code not read. [README.md](https://github.com/negativeview/sarcophilus/blob/main/README.md)

3. **Robot context:** README says Melty Brain Battle Bot; class, size, competition not found. [README.md](https://github.com/negativeview/sarcophilus/blob/main/README.md)

4. **Hardware:** not found.

5. **Heading sensing and placement:** not found.

6. **Angle / RPM algorithm, filtering and rate:** not found.

7. **Drift handling:** not found.

8. **Translation timing and mapping:** not found.

9. **Heading indicator:** not found.

10. **Calibration:** not found.

11. **Controls, modes and failsafes:** not found.

12. **Notable ideas:** not found.

13. **Problems, failures and evidence limits:** not found.

14. **License:** not found.

<a id="p057"></a>

## P057. Redline — matt-nolan11

1. **Name / author / links / activity:** [Redline — matt-nolan11](https://github.com/matt-nolan11/Redline); push 2026-04-29 UTC. [metadata](https://api.github.com/repos/matt-nolan11/Redline).

2. **Source type and actual inspection:** Design repository/README read; control code not read. [README.md](https://github.com/matt-nolan11/Redline/blob/main/README.md)

3. **Robot context:** Insect class, exact weight undecided; size, competition not found. [README.md](https://github.com/matt-nolan11/Redline/blob/main/README.md)

4. **Hardware:** not found.

5. **Heading sensing and placement:** not found.

6. **Angle / RPM algorithm, filtering and rate:** not found.

7. **Drift handling:** not found.

8. **Translation timing and mapping:** not found.

9. **Heading indicator:** not found.

10. **Calibration:** not found.

11. **Controls, modes and failsafes:** not found.

12. **Notable ideas:** not found.

13. **Problems, failures and evidence limits:** not found.

14. **License:** AGPL-3.0. [LICENSE](https://github.com/matt-nolan11/Redline/blob/main/LICENSE)

<a id="p058"></a>

## P058. Tunamelt — Joe Earlam

1. **Name / author / links / activity:** [Tunamelt — Joe Earlam](https://github.com/JoeEarlam/tunamelt); push 2026-08-02 UTC. [metadata](https://api.github.com/repos/JoeEarlam/tunamelt).

2. **Source type and actual inspection:** Repository metadata inspected; GitHub contents/tree returns repository empty; no code read. [contents](https://api.github.com/repos/JoeEarlam/tunamelt/contents)

3. **Robot context:** not found.

4. **Hardware:** not found.

5. **Heading sensing and placement:** not found.

6. **Angle / RPM algorithm, filtering and rate:** not found.

7. **Drift handling:** not found.

8. **Translation timing and mapping:** not found.

9. **Heading indicator:** not found.

10. **Calibration:** not found.

11. **Controls, modes and failsafes:** not found.

12. **Notable ideas:** Description only; claimed implementation not established. [metadata](https://api.github.com/repos/JoeEarlam/tunamelt)

13. **Problems, failures and evidence limits:** not found.

14. **License:** not found.

<a id="p059"></a>

## P059. MeltyMind — fks-2702

1. **Name / author / links / activity:** [MeltyMind — fks-2702](https://github.com/fks-2702/MeltyMind); push 2026-08-04 UTC. [metadata](https://api.github.com/repos/fks-2702/MeltyMind).

2. **Source type and actual inspection:** Repository metadata inspected; GitHub contents/tree returns repository empty; no code read. [contents](https://api.github.com/repos/fks-2702/MeltyMind/contents)

3. **Robot context:** not found.

4. **Hardware:** not found.

5. **Heading sensing and placement:** not found.

6. **Angle / RPM algorithm, filtering and rate:** not found.

7. **Drift handling:** not found.

8. **Translation timing and mapping:** not found.

9. **Heading indicator:** not found.

10. **Calibration:** not found.

11. **Controls, modes and failsafes:** not found.

12. **Notable ideas:** Description only; claimed implementation not established. [metadata](https://api.github.com/repos/fks-2702/MeltyMind)

13. **Problems, failures and evidence limits:** not found.

14. **License:** not found.

<a id="p060"></a>

## P060. Trick V2 — Gaantry88

1. **Name / author / links / activity:** [Trick V2 — Gaantry88](https://github.com/Gaantry88/TrickV2); push 2026-06-24 UTC. [metadata](https://api.github.com/repos/Gaantry88/TrickV2).

2. **Source type and actual inspection:** Repository metadata inspected; GitHub contents/tree returns repository empty; no code read. [contents](https://api.github.com/repos/Gaantry88/TrickV2/contents)

3. **Robot context:** not found.

4. **Hardware:** not found.

5. **Heading sensing and placement:** not found.

6. **Angle / RPM algorithm, filtering and rate:** not found.

7. **Drift handling:** not found.

8. **Translation timing and mapping:** not found.

9. **Heading indicator:** not found.

10. **Calibration:** not found.

11. **Controls, modes and failsafes:** not found.

12. **Notable ideas:** Description only; claimed implementation not established. [metadata](https://api.github.com/repos/Gaantry88/TrickV2)

13. **Problems, failures and evidence limits:** not found.

14. **License:** not found.

<a id="p061"></a>

## P061. Multybrain — peterhenryd

1. **Name / author / links / activity:** [Multybrain — peterhenryd](https://github.com/peterhenryd/multybrain); push 2026-05-13 UTC. [metadata](https://api.github.com/repos/peterhenryd/multybrain).

2. **Source type and actual inspection:** Repository description and root listing inspected; onlyLICENSE present, no control code read. [contents](https://api.github.com/repos/peterhenryd/multybrain/contents)

3. **Robot context:** 12 lb, titanium chassis per description; actual size/competition not found. [metadata](https://api.github.com/repos/peterhenryd/multybrain)

4. **Hardware:** Teensy 4.1 per repository description; other hardware not found. [metadata](https://api.github.com/repos/peterhenryd/multybrain)

5. **Heading sensing and placement:** not found.

6. **Angle / RPM algorithm, filtering and rate:** not found.

7. **Drift handling:** not found.

8. **Translation timing and mapping:** not found.

9. **Heading indicator:** not found.

10. **Calibration:** not found.

11. **Controls, modes and failsafes:** Autonomous and manual override are described goals; implementation/failsafe not found. [metadata](https://api.github.com/repos/peterhenryd/multybrain)

12. **Notable ideas:** not found.

13. **Problems, failures and evidence limits:** not found.

14. **License:** MIT. [LICENSE](https://github.com/peterhenryd/multybrain/blob/main/LICENSE)

<a id="p062"></a>

## P062. DONUT — ManasAgrawal05

1. **Name / author / links / activity:** [DONUT — ManasAgrawal05](https://github.com/ManasAgrawal05/DONUT); push 2025-04-11 UTC. [metadata](https://api.github.com/repos/ManasAgrawal05/DONUT).

2. **Source type and actual inspection:** Code; src/meltybrain.cpp, Accelerometer.cpp, Comms.cpp read. GitHub parent MeltyHalo. [metadata](https://api.github.com/repos/ManasAgrawal05/DONUT)

3. **Robot context:** not found.

4. **Hardware:** Arduino/SparkFun-LIS331-style sensor interface, I2C, analogWrite motor outputs; exact MCU/motor/radio models not found. [src/Accelerometer.cpp](https://github.com/ManasAgrawal05/DONUT/blob/master/src/Accelerometer.cpp) [src/meltybrain.cpp](https://github.com/ManasAgrawal05/DONUT/blob/master/src/meltybrain.cpp)

5. **Heading sensing and placement:** Z radial, X tangential, Y axial per comments; calibration coefficients copied from Halo article, not independently established for DONUT. [src/Accelerometer.cpp](https://github.com/ManasAgrawal05/DONUT/blob/master/src/Accelerometer.cpp)

6. **Angle / RPM algorithm, filtering and rate:** 10 ms reading interval; robotPeriod=726/sqrt((zAccel−225)/522), trapezoidal angle increment between stored periods, linear extrapolation between samples. Sensor config symbol says 50 Hz while comment says 1000 Hz; actual ODR not established without header. [src/Accelerometer.cpp](https://github.com/ManasAgrawal05/DONUT/blob/master/src/Accelerometer.cpp)

7. **Drift handling:** accelTrim added to angle; no active external reference in runMeltyBrain. [src/meltybrain.cpp](https://github.com/ManasAgrawal05/DONUT/blob/master/src/meltybrain.cpp)

8. **Translation timing and mapping:** Active runMeltyBrain only updates acceleration-derived angle. Motor-direction modulation and full-rotation OpenMelt schedule are commented out. Do not count comments as working translation. [src/meltybrain.cpp](https://github.com/ManasAgrawal05/DONUT/blob/master/src/meltybrain.cpp)

9. **Heading indicator:** LED timing exists in commented scheduling block; active heading LED not found. [src/meltybrain.cpp](https://github.com/ManasAgrawal05/DONUT/blob/master/src/meltybrain.cpp)

10. **Calibration:** Inherited fixed 726/225/522 calibration; matching physical geometry not established. [src/Accelerometer.cpp](https://github.com/ManasAgrawal05/DONUT/blob/master/src/Accelerometer.cpp)

11. **Controls, modes and failsafes:** setMotorSpeed clamp ±100, deadband 5, motor1 inversion; full end-to-end failsafe not established from inspected files. [src/meltybrain.cpp](https://github.com/ManasAgrawal05/DONUT/blob/master/src/meltybrain.cpp)

12. **Notable ideas:** Separate fork includes large commented alternative rotation scheduler; changes are experimentation rather than verified behavior. [src/meltybrain.cpp](https://github.com/ManasAgrawal05/DONUT/blob/master/src/meltybrain.cpp)

13. **Problems, failures and evidence limits:** No author test narrative found; translation-disabled state directly observed in source. [src/meltybrain.cpp](https://github.com/ManasAgrawal05/DONUT/blob/master/src/meltybrain.cpp)

14. **License:** not found.

<a id="p063"></a>

## P063. Jeremiah FBS — NURobotics

1. **Name / author / links / activity:** [Jeremiah FBS — NURobotics](https://github.com/NURobotics/Jeremiah-FBS); push 2020-02-19 UTC. [metadata](https://api.github.com/repos/NURobotics/Jeremiah-FBS).

2. **Source type and actual inspection:** Code fork; Jeremiah-FBS.ino, meltybrain.ino, Comms.ino read. [Jeremiah-FBS.ino](https://github.com/NURobotics/Jeremiah-FBS/blob/master/Jeremiah-FBS.ino)

3. **Robot context:** not found.

4. **Hardware:** ESP32, PS4Controller Bluetooth, SparkFun LIS331, IR GPIO15, motor GPIO3/4, enable22, battery A13. Exact sensor/ESC/motor parts not found. [Jeremiah-FBS.ino](https://github.com/NURobotics/Jeremiah-FBS/blob/master/Jeremiah-FBS.ino)

5. **Heading sensing and placement:** Beacon/acceleration/hybrid modes; IR edge debounce 2000 us. Hybrid accepts reference only after ~270° expected rotation and applies 40° phase correction. [meltybrain.ino](https://github.com/NURobotics/Jeremiah-FBS/blob/master/meltybrain.ino)

6. **Angle / RPM algorithm, filtering and rate:** Beacon-only linear time interpolation from two edges; acceleration-period path inherited, full sensor file not analyzed here. [meltybrain.ino](https://github.com/NURobotics/Jeremiah-FBS/blob/master/meltybrain.ino)

7. **Drift handling:** Hybrid resets accelTrim from IR; separate sensing modes retained. [meltybrain.ino](https://github.com/NURobotics/Jeremiah-FBS/blob/master/meltybrain.ino)

8. **Translation timing and mapping:** For command >10, each half-turn swaps which motor receives throttle or throttle−20; inversion flag reverses signs. Critical port gap: actual analogWrite motor output is commented for ESP32 compatibility. [meltybrain.ino](https://github.com/NURobotics/Jeremiah-FBS/blob/master/meltybrain.ino) [Jeremiah-FBS.ino](https://github.com/NURobotics/Jeremiah-FBS/blob/master/Jeremiah-FBS.ino)

9. **Heading indicator:** PS4 controller LED indicates idle/tank/spin, gray/yellow/red; body heading strobe not found in inspected files. [Jeremiah-FBS.ino](https://github.com/NURobotics/Jeremiah-FBS/blob/master/Jeremiah-FBS.ino)

10. **Calibration:** not found; inherited sensor constants not separately validated. Source: [Jeremiah FBS — NURobotics](https://github.com/NURobotics/Jeremiah-FBS).

11. **Controls, modes and failsafes:** Idle/tank/spin; >1 s without packet calls goIdle; 1 s watchdog ESTOP. Hardware enable pin set HIGH in idle. Low-battery check exists with scaled threshold, but voltage calibration is unverified. [Jeremiah-FBS.ino](https://github.com/NURobotics/Jeremiah-FBS/blob/master/Jeremiah-FBS.ino)

12. **Notable ideas:** PS4 controller connection/telemetry adaptation. [Jeremiah-FBS.ino](https://github.com/NURobotics/Jeremiah-FBS/blob/master/Jeremiah-FBS.ino)

13. **Problems, failures and evidence limits:** Comments explicitly mark PWM output and frequency porting unfinished; running motor control not established. [Jeremiah-FBS.ino](https://github.com/NURobotics/Jeremiah-FBS/blob/master/Jeremiah-FBS.ino)

14. **License:** MIT. [LICENSE](https://github.com/NURobotics/Jeremiah-FBS/blob/master/LICENSE)

<a id="p064"></a>

## P064. AnthonyMichaelTDM — Rust battlebot firmware experiments

1. **Name / author / links / activity:** [AnthonyMichaelTDM — Rust battlebot firmware experiments](https://github.com/AnthonyMichaelTDM/battlebots-firmware); push 2025-09-30 UTC. [metadata](https://api.github.com/repos/AnthonyMichaelTDM/battlebots-firmware).

2. **Source type and actual inspection:** Code; accelerometer.rs and brushless_motor.rs read; repository contains diagnostics, not confirmed complete translational-drift firmware. [README.md](https://github.com/AnthonyMichaelTDM/battlebots-firmware/blob/main/README.md)

3. **Robot context:** not found.

4. **Hardware:** ESP-HAL Rust, H3LIS331 driver I2C GPIO1/2, DShot600 on RMT GPIO14; exact board, motor/ESC/radio not found. [bins/src/bin/accelerometer.rs](https://github.com/AnthonyMichaelTDM/battlebots-firmware/blob/main/bins/src/bin/accelerometer.rs) [bins/src/bin/brushless_motor.rs](https://github.com/AnthonyMichaelTDM/battlebots-firmware/blob/main/bins/src/bin/brushless_motor.rs)

5. **Heading sensing and placement:** Logs all acceleration axes/magnitude; mounting radius not found. [bins/src/bin/accelerometer.rs](https://github.com/AnthonyMichaelTDM/battlebots-firmware/blob/main/bins/src/bin/accelerometer.rs)

6. **Angle / RPM algorithm, filtering and rate:** Accelerometer test sets 100 g range, 50 Hz ODR, polls 100 ms. Rotation estimator not found in inspected test. [bins/src/bin/accelerometer.rs](https://github.com/AnthonyMichaelTDM/battlebots-firmware/blob/main/bins/src/bin/accelerometer.rs)

7. **Drift handling:** not found.

8. **Translation timing and mapping:** Motor diagnostic ramps 40% over 4 s then back down, 20 ms command interval; rotation-synchronous modulation not found. [bins/src/bin/brushless_motor.rs](https://github.com/AnthonyMichaelTDM/battlebots-firmware/blob/main/bins/src/bin/brushless_motor.rs)

9. **Heading indicator:** Separate LED diagnostics named in repo tree; heading strobe not found. [repository](https://github.com/AnthonyMichaelTDM/battlebots-firmware)

10. **Calibration:** not found.

11. **Controls, modes and failsafes:** Author proposes dedicated async task with 2 s stale-throttle ramp-down; proposal is not active RC failsafe in inspected test. [bins/src/bin/brushless_motor.rs](https://github.com/AnthonyMichaelTDM/battlebots-firmware/blob/main/bins/src/bin/brushless_motor.rs)

12. **Notable ideas:** Custom embedded Rust sensor and DShot driver experiments. [README.md](https://github.com/AnthonyMichaelTDM/battlebots-firmware/blob/main/README.md)

13. **Problems, failures and evidence limits:** Author observes ESC stops after short command gap (estimated <=20 ms) and needs rearming; 1500 ms startup wait necessary but cause unknown. [bins/src/bin/brushless_motor.rs](https://github.com/AnthonyMichaelTDM/battlebots-firmware/blob/main/bins/src/bin/brushless_motor.rs)

14. **License:** not found.

<a id="p065"></a>

## P065. Melontype — zenith-parsec

1. **Name / author / links / activity:** [Melontype — zenith-parsec](https://github.com/zenith-parsec/melontype); push 2025-11-07 UTC. [metadata](https://api.github.com/repos/zenith-parsec/melontype).

2. **Source type and actual inspection:** Both; README, config.h, accel.cpp, melontype.ino and dynamic calibration code inspected. [README.md](https://github.com/zenith-parsec/melontype/blob/main/README.md)

3. **Robot context:** Author reports 2 ft translation in 4 ft test box; NHRL 2025 functionality test intended, actual event result/class not found. [README.md](https://github.com/zenith-parsec/melontype/blob/main/README.md)

4. **Hardware:** Teensy 4.x, H3LIS331 I2C, FlySky iBus, NeoPixel strip, two ESCs with 400 Hz PWM. Exact motors/ESC models not found. [config.h](https://github.com/zenith-parsec/melontype/blob/main/config.h)

5. **Heading sensing and placement:** 400 g/400 Hz sensor; XY magnitude with manually measured three-axis offsets. [accel.cpp](https://github.com/zenith-parsec/melontype/blob/main/accel.cpp)

6. **Angle / RPM algorithm, filtering and rate:** 400 Hz IntervalTimer, sqrt(ax²+ay²), LPF alpha .05; calculateRPS=sqrt(a/r)/(2pi) or interpolated acceleration→RPS lookup. Phase integrates rotation rate. [accel.cpp](https://github.com/zenith-parsec/melontype/blob/main/accel.cpp) [melontype.ino](https://github.com/zenith-parsec/melontype/blob/main/melontype.ino)

7. **Drift handling:** User tunes virtual radius and stores piecewise mapping over many speeds; heading-offset dial sets front. No geomagnetic/IR anchor found. [README.md](https://github.com/zenith-parsec/melontype/blob/main/README.md)

8. **Translation timing and mapping:** Two opposed cosine phase values and PID spin setpoint; phase adjusted by stick angle/headingOffset; motor2 phase offset .5 turn. [melontype.ino](https://github.com/zenith-parsec/melontype/blob/main/melontype.ino)

9. **Heading indicator:** POV RPM and other numeric display, blue front arc, RGB status. [README.md](https://github.com/zenith-parsec/melontype/blob/main/README.md) [melontype.ino](https://github.com/zenith-parsec/melontype/blob/main/melontype.ino)

10. **Calibration:** CH5 virtual radius, CH6 front offset; three-position switch manual/table/capture modes; serial c clears, p dumps map. Source and README channel indices differ; zero-based source indices explicit. [README.md](https://github.com/zenith-parsec/melontype/blob/main/README.md) [melontype.ino](https://github.com/zenith-parsec/melontype/blob/main/melontype.ino)

11. **Controls, modes and failsafes:** iBus 0/1 stick, 2 power, 4 radius, 5 offset, 6/9 motor reversal, 8 three-position switch, 7 text direction. rc_signal_is_healthy guard zeros motors; exact timeout not established here. [melontype.ino](https://github.com/zenith-parsec/melontype/blob/main/melontype.ino)

12. **Notable ideas:** Lookup curve accounts for nonlinearity rather than a single fixed radius; author states code collaboratively written with ChatGPT. [README.md](https://github.com/zenith-parsec/melontype/blob/main/README.md)

13. **Problems, failures and evidence limits:** Author warns not production quality; heading looks steady but translation requires continual aim rotation, possible bugs; testing still incomplete. [README.md](https://github.com/zenith-parsec/melontype/blob/main/README.md)

14. **License:** not found.

<a id="p066"></a>

## P066. Beyblade Melty Brain Kit — AriM224

1. **Name / author / links / activity:** [Beyblade Melty Brain Kit — AriM224](https://github.com/AriM224/Beyblade-Melty-Brain-Kit); push 2026-10-06 UTC. [metadata](https://api.github.com/repos/AriM224/Beyblade-Melty-Brain-Kit).

2. **Source type and actual inspection:** Both; Heading.ino, Motor_Control.ino, RC_Handler.ino, main IDF5 sketch read. [README.md](https://github.com/AriM224/Beyblade-Melty-Brain-Kit/blob/main/README.md)

3. **Robot context:** Described as 1 lb plastic kit; competition, size not found. [README.md](https://github.com/AriM224/Beyblade-Melty-Brain-Kit/blob/main/README.md)

4. **Hardware:** ESP32 Arduino IDF5, H3LIS331 interface 400 g, I2C 0x19, DShotRMT600, two 10-NeoPixel strips, iBus 6 channels, 4S battery setting. Exact board/motors/ESC models not found. [Code/IDF_5_compatible/IDF_5_compatible.ino](https://github.com/AriM224/Beyblade-Melty-Brain-Kit/blob/main/Code/IDF_5_compatible/IDF_5_compatible.ino)

5. **Heading sensing and placement:** Y-axis sensor, configured 22 mm radius. [Code/IDF_5_compatible/Heading.ino](https://github.com/AriM224/Beyblade-Melty-Brain-Kit/blob/main/Code/IDF_5_compatible/Heading.ino) [Code/IDF_5_compatible/IDF_5_compatible.ino](https://github.com/AriM224/Beyblade-Melty-Brain-Kit/blob/main/Code/IDF_5_compatible/IDF_5_compatible.ino)

6. **Angle / RPM algorithm, filtering and rate:** Three-sample average at >10 ms interval (~100 Hz); RPM=round(sqrt(g)/sqrt(.000001118*r_mm)/offset); period=60000000/RPM*heading factor above 400 RPM; elapsed-time phase. [Code/IDF_5_compatible/Heading.ino](https://github.com/AriM224/Beyblade-Melty-Brain-Kit/blob/main/Code/IDF_5_compatible/Heading.ino)

7. **Drift handling:** Steering modifies period factor; offset adjusted ±.004 with switch action and saved to EEPROM. [Code/IDF_5_compatible/Heading.ino](https://github.com/AriM224/Beyblade-Melty-Brain-Kit/blob/main/Code/IDF_5_compatible/Heading.ino)

8. **Translation timing and mapping:** Two 15%-rotation deceleration windows starting near 0°/180°; stick maps boost/coast to one or other motor with spin-direction sign; spin-up cap acc_rate*RPM+200. [Code/IDF_5_compatible/Motor_Control.ino](https://github.com/AriM224/Beyblade-Melty-Brain-Kit/blob/main/Code/IDF_5_compatible/Motor_Control.ino)

9. **Heading indicator:** Heading center 315°; actual call isAngleInRange(...,20) means ±20° despite comment ±10°. Status/motor-pulse LED modes. [Code/IDF_5_compatible/IDF_5_compatible.ino](https://github.com/AriM224/Beyblade-Melty-Brain-Kit/blob/main/Code/IDF_5_compatible/IDF_5_compatible.ino)

10. **Calibration:** Saved offset and zero g; single current-measurement zero calibration, RC switch trim. [Code/IDF_5_compatible/Heading.ino](https://github.com/AriM224/Beyblade-Melty-Brain-Kit/blob/main/Code/IDF_5_compatible/Heading.ino)

11. **Controls, modes and failsafes:** iBus update every 10 ms; counter stale >500 ms neutralizes channels, marks RC bad; 2 s task watchdog. Tank/low-RPM mode and reverse branches. [Code/IDF_5_compatible/RC_Handler.ino](https://github.com/AriM224/Beyblade-Melty-Brain-Kit/blob/main/Code/IDF_5_compatible/RC_Handler.ino) [Code/IDF_5_compatible/IDF_5_compatible.ino](https://github.com/AriM224/Beyblade-Melty-Brain-Kit/blob/main/Code/IDF_5_compatible/IDF_5_compatible.ino)

12. **Notable ideas:** 3D bidirectional DShot packing, WiFi diagnostics and kit delivery. [Code/IDF_5_compatible/Motor_Control.ino](https://github.com/AriM224/Beyblade-Melty-Brain-Kit/blob/main/Code/IDF_5_compatible/Motor_Control.ino) [Code/IDF_5_compatible/IDF_5_compatible.ino](https://github.com/AriM224/Beyblade-Melty-Brain-Kit/blob/main/Code/IDF_5_compatible/IDF_5_compatible.ino)

13. **Problems, failures and evidence limits:** Code comments acknowledge reversal-branch complexity; hardware validation not found. Source: [Beyblade Melty Brain Kit — AriM224](https://github.com/AriM224/Beyblade-Melty-Brain-Kit).

14. **License:** AGPL-3.0, repository LICENSE. [LICENSE](https://github.com/AriM224/Beyblade-Melty-Brain-Kit/blob/main/LICENSE)

<a id="p067"></a>

## P067. anba9306-ai — Melty-Brain placeholder

1. **Name / author / links / activity:** [anba9306-ai — Melty-Brain placeholder](https://github.com/anba9306-ai/Melty-Brain); push 2026-02-24 UTC. [metadata](https://api.github.com/repos/anba9306-ai/Melty-Brain).

2. **Source type and actual inspection:** Code repository; src/main.cpp read. [src/main.cpp](https://github.com/anba9306-ai/Melty-Brain/blob/main/src/main.cpp)

3. **Robot context:** not found.

4. **Hardware:** not found.

5. **Heading sensing and placement:** not found.

6. **Angle / RPM algorithm, filtering and rate:** not found; active example only adds 2+3 in setup and has an empty loop. [src/main.cpp](https://github.com/anba9306-ai/Melty-Brain/blob/main/src/main.cpp)

7. **Drift handling:** not found.

8. **Translation timing and mapping:** not found.

9. **Heading indicator:** not found.

10. **Calibration:** not found.

11. **Controls, modes and failsafes:** not found.

12. **Notable ideas:** Retained as unfinished repository identity, not working robot. [src/main.cpp](https://github.com/anba9306-ai/Melty-Brain/blob/main/src/main.cpp)

13. **Problems, failures and evidence limits:** not found.

14. **License:** not found.

<a id="p068"></a>

## P068. Candas1 — Melty Brain Simulator

1. **Name / author / links / activity:** [Candas1 — Melty Brain Simulator](https://github.com/Candas1/Melty-Brain-Simulator); push 2022-12-14 UTC. [metadata](https://api.github.com/repos/Candas1/Melty-Brain-Simulator).

2. **Source type and actual inspection:** Code and README; index.html read, not executed. [readme.md](https://github.com/Candas1/Melty-Brain-Simulator/blob/master/readme.md) [index.html](https://github.com/Candas1/Melty-Brain-Simulator/blob/master/index.html)

3. **Robot context:** Adjustable wheel geometry, no identified built robot or competition. [index.html](https://github.com/Candas1/Melty-Brain-Simulator/blob/master/index.html)

4. **Hardware:** P5.js browser simulation; physical parts not found. [index.html](https://github.com/Candas1/Melty-Brain-Simulator/blob/master/index.html)

5. **Heading sensing and placement:** Uses simulated internal angle, no heading-sensor model found. [index.html](https://github.com/Candas1/Melty-Brain-Simulator/blob/master/index.html)

6. **Angle / RPM algorithm, filtering and rate:** Differential-wheel model integrates position and angle; RPM slider sets nominal wheel speed; acceleration/deceleration sliders limit command response. [index.html](https://github.com/Candas1/Melty-Brain-Simulator/blob/master/index.html)

7. **Drift handling:** not found.

8. **Translation timing and mapping:** Relative commanded bearing selects high/low wheel speeds for opposite half-turns; click ring/arrows command drift. [index.html](https://github.com/Candas1/Melty-Brain-Simulator/blob/master/index.html) [readme.md](https://github.com/Candas1/Melty-Brain-Simulator/blob/master/readme.md)

9. **Heading indicator:** Simulated red heading LED at 350°–10°, heading/command graphs. [index.html](https://github.com/Candas1/Melty-Brain-Simulator/blob/master/index.html)

10. **Calibration:** Geometry, high/low speed and response sliders; physical calibration not found. [index.html](https://github.com/Candas1/Melty-Brain-Simulator/blob/master/index.html)

11. **Controls, modes and failsafes:** Mouse/keyboard controls; RC failsafe model not found. [readme.md](https://github.com/Candas1/Melty-Brain-Simulator/blob/master/readme.md)

12. **Notable ideas:** Explicit wheel-response lag model and real/commanded speed plots. [index.html](https://github.com/Candas1/Melty-Brain-Simulator/blob/master/index.html)

13. **Problems, failures and evidence limits:** not found.

14. **License:** not found.

<a id="p069"></a>

## P069. OPRobots — H3LIS331 demo

1. **Name / author / links / activity:** [OPRobots — H3LIS331 demo](https://github.com/OPRobots/H3LIS-demo); push 2026-06-29 UTC. [metadata](https://api.github.com/repos/OPRobots/H3LIS-demo).

2. **Source type and actual inspection:** Both; README, src/h3lis.c and known-issues document read. [README.md](https://github.com/OPRobots/H3LIS-demo/blob/main/README.md) [src/h3lis.c](https://github.com/OPRobots/H3LIS-demo/blob/main/src/h3lis.c)

3. **Robot context:** Sensor/kinematics demo, no built combat robot class/competition found. [README.md](https://github.com/OPRobots/H3LIS-demo/blob/main/README.md)

4. **Hardware:** STM32F401CC BlackPill 84 MHz, H3LIS331DL 400 g, libopencm3,  SPI1 5.25 MHz, USART 115200, PC13 activity LED. [README.md](https://github.com/OPRobots/H3LIS-demo/blob/main/README.md)

5. **Heading sensing and placement:** XY acceleration magnitude, sensor radius10 mm configurable; Z excluded. [README.md](https://github.com/OPRobots/H3LIS-demo/blob/main/README.md)

6. **Angle / RPM algorithm, filtering and rate:** 1 kHz SysTick calls update, burst 6-byte SPI, g scaling 400/32768, a=sqrt(ax²+ay²)*9.80665, omega=sqrt(a/r), RPM=omega*60/(2pi); fixed 1 ms Euler integration and wrap. Below .5m/s² suppressed. [src/h3lis.c](https://github.com/OPRobots/H3LIS-demo/blob/main/src/h3lis.c) [README.md](https://github.com/OPRobots/H3LIS-demo/blob/main/README.md)

7. **Drift handling:** No absolute correction; README acknowledges integrated drift and proposes future reference fusion. [README.md](https://github.com/OPRobots/H3LIS-demo/blob/main/README.md)

8. **Translation timing and mapping:** not found; no motor modulation in inspected demo. Source: [OPRobots — H3LIS331 demo](https://github.com/OPRobots/H3LIS-demo).

9. **Heading indicator:** Activity LED only; heading indicator not found. [README.md](https://github.com/OPRobots/H3LIS-demo/blob/main/README.md)

10. **Calibration:** Set MPU_SENSOR_OFFSET_M to actual radius; automatic calibration not found. [README.md](https://github.com/OPRobots/H3LIS-demo/blob/main/README.md)

11. **Controls, modes and failsafes:** Sensor ID error path; radio/motor failsafes not found. [README.md](https://github.com/OPRobots/H3LIS-demo/blob/main/README.md)

12. **Notable ideas:** Standalone reusable sensing demonstration, not a full robot controller. [README.md](https://github.com/OPRobots/H3LIS-demo/blob/main/README.md)

13. **Problems, failures and evidence limits:** Author audit lists blocking SPI in ISR, expected WHO_AM_I 0x33 vs datasheet 0x32 mismatch, floating-point interrupt overhead and minor maintenance issues. These are author's audit findings, not reproduced hardware failures. [docs/05-known-issues.md](https://github.com/OPRobots/H3LIS-demo/blob/main/docs/05-known-issues.md)

14. **License:** PolyForm Noncommercial 1.0.0. [LICENSE](https://github.com/OPRobots/H3LIS-demo/blob/main/LICENSE)

<a id="p070"></a>

## P070. Homer — Zac Q Howard

1. **Name / author / links / activity:** [Homer — Zac Q Howard](https://github.com/ZacQHoward/Homer); push 2026-06-03 UTC. [metadata](https://api.github.com/repos/ZacQHoward/Homer).

2. **Source type and actual inspection:** Both; README, movement_control.cpp, accel_handler.cpp and config inspected. [README.md](https://github.com/ZacQHoward/Homer/blob/main/README.md)

3. **Robot context:** Competitive robot per metadata; exact class/size/event results not found. [metadata](https://api.github.com/repos/ZacQHoward/Homer)

4. **Hardware:** ESP32-C3 per metadata; LIS331 high-g interface, I2C, two motor PWM outputs, RGB heading pins. Exact sensor variant/ESC/motors/radio not found. [include/homer_config.h](https://github.com/ZacQHoward/Homer/blob/main/include/homer_config.h)

5. **Heading sensing and placement:** Selected single sensor axis, configured 5.2 cm radius and 3.7 g zero offset. [include/homer_config.h](https://github.com/ZacQHoward/Homer/blob/main/include/homer_config.h) [src/accel_handler.cpp](https://github.com/ZacQHoward/Homer/blob/main/src/accel_handler.cpp)

6. **Angle / RPM algorithm, filtering and rate:** RPM=sqrt(abs(g-offset)*89445/r_cm); no active phase estimator shown in movement control. [src/movement_control.cpp](https://github.com/ZacQHoward/Homer/blob/main/src/movement_control.cpp)

7. **Drift handling:** not found.

8. **Translation timing and mapping:** apply_diff_drive combines spin and body-frame forward/turn; apply_meltybrain_drive is empty. Direction vector normalized and atan2 computed, but translation while spinning not implemented through this function. [src/movement_control.cpp](https://github.com/ZacQHoward/Homer/blob/main/src/movement_control.cpp)

9. **Heading indicator:** RGB heading pin definitions; synchronized strobe not found in inspected files. [include/homer_config.h](https://github.com/ZacQHoward/Homer/blob/main/include/homer_config.h)

10. **Calibration:** Hardcoded 5.2 cm/3.7 g parameters; completed calibration procedure not found. [include/homer_config.h](https://github.com/ZacQHoward/Homer/blob/main/include/homer_config.h)

11. **Controls, modes and failsafes:** CH1 turn, CH2 forward/back, CH3 spin; configured manual/differential/melty modes; README says signal loss neutralizes both motors, config timeout 100000 us. [README.md](https://github.com/ZacQHoward/Homer/blob/main/README.md) [include/homer_config.h](https://github.com/ZacQHoward/Homer/blob/main/include/homer_config.h)

12. **Notable ideas:** Clear separation of vector mapping, RPM tracking and drive modes. [src/movement_control.cpp](https://github.com/ZacQHoward/Homer/blob/main/src/movement_control.cpp)

13. **Problems, failures and evidence limits:** Melty algorithm gap directly observed in code; author's hardware-failure report not found. [src/movement_control.cpp](https://github.com/ZacQHoward/Homer/blob/main/src/movement_control.cpp)

14. **License:** not found.

<a id="p071"></a>

## P071. Stuffed Crust — Wildcat Robotics / buttonbugs

1. **Name / author / links / activity:** [Stuffed Crust — Wildcat Robotics / buttonbugs](https://github.com/buttonbugs/Stuffed-Crust); push 2026-10-20 UTC. [metadata](https://api.github.com/repos/buttonbugs/Stuffed-Crust).

2. **Source type and actual inspection:** Both; README, spin_control.cpp, board acceleration/config files read. [README.md](https://github.com/buttonbugs/Stuffed-Crust/blob/main/README.md)

3. **Robot context:** Class/size/event results not found. Source: [Stuffed Crust — Wildcat Robotics / buttonbugs](https://github.com/buttonbugs/Stuffed-Crust).

4. **Hardware:** ESP32 and Teensy 4.0 targets, H3LIS331-family sensor, watchdog adaptation WDT_T4. Exact ESC/motor/radio parts not found. [README.md](https://github.com/buttonbugs/Stuffed-Crust/blob/main/README.md) [src/esp32/melty_config.h](https://github.com/buttonbugs/Stuffed-Crust/blob/main/src/esp32/melty_config.h) [src/teensy40/melty_config.h](https://github.com/buttonbugs/Stuffed-Crust/blob/main/src/teensy40/melty_config.h)

5. **Heading sensing and placement:** Single radial acceleration and stored effective radius/zero offset. [src/spin_control.cpp](https://github.com/buttonbugs/Stuffed-Crust/blob/main/src/spin_control.cpp)

6. **Angle / RPM algorithm, filtering and rate:** omega=sqrt(abs(g-zero)*9.8/r_m); trapezoidal frequency integration using actual micros interval, sign flips by facing_up; wraps heading in turns. No fixed control-loop rate claimed. [src/spin_control.cpp](https://github.com/buttonbugs/Stuffed-Crust/blob/main/src/spin_control.cpp)

7. **Drift handling:** Manual revolution_ratio changes heading at max 1.4rev/s; radius and LED ratio configurable, no external anchor found. [src/spin_control.cpp](https://github.com/buttonbugs/Stuffed-Crust/blob/main/src/spin_control.cpp)

8. **Translation timing and mapping:** Stick magnitude sets angular half-width .25*magnitude turns around target and antipode. Selected motor reduced to .05, opposite boosted to 1.95 before multiplying spin throttle and clamping±1; atan2 sets direction. Nonblocking function called each loop. [src/spin_control.cpp](https://github.com/buttonbugs/Stuffed-Crust/blob/main/src/spin_control.cpp)

9. **Heading indicator:** update_led(robot_direction); exact LED arc in separate driver not analyzed here. [src/spin_control.cpp](https://github.com/buttonbugs/Stuffed-Crust/blob/main/src/spin_control.cpp)

10. **Calibration:** EEPROM radius/zero; config changes radius by .00002 cm per call and LED ratio by .0004, so adjustment rate depends on loop rate. Teensy branch excludes those config changes. [src/spin_control.cpp](https://github.com/buttonbugs/Stuffed-Crust/blob/main/src/spin_control.cpp)

11. **Controls, modes and failsafes:** Service watchdog in high-speed loop; separate low-speed module exists. Full channel map and radio-loss timing not found in inspected snippets. [src/spin_control.cpp](https://github.com/buttonbugs/Stuffed-Crust/blob/main/src/spin_control.cpp)

12. **Notable ideas:** Repository explicitly credits OpenMelt2 and watchdog library; authored translation scheduling avoids whole-rotation blocking loops. [README.md](https://github.com/buttonbugs/Stuffed-Crust/blob/main/README.md) [src/spin_control.cpp](https://github.com/buttonbugs/Stuffed-Crust/blob/main/src/spin_control.cpp)

13. **Problems, failures and evidence limits:** No author hardware failure narrative found. Source: [Stuffed Crust — Wildcat Robotics / buttonbugs](https://github.com/buttonbugs/Stuffed-Crust).

14. **License:** MIT repository license; credited upstream/license compatibility not independently adjudicated. [LICENSE](https://github.com/buttonbugs/Stuffed-Crust/blob/main/LICENSE) [README.md](https://github.com/buttonbugs/Stuffed-Crust/blob/main/README.md)

<a id="p072"></a>

## P072. Hamachi — Griswald Brooks

1. **Name / author / links / activity:** [Hamachi — Griswald Brooks](https://github.com/griswaldbrooks/hamachi); push 2026-06-06 UTC. [metadata](https://api.github.com/repos/griswaldbrooks/hamachi).

2. **Source type and actual inspection:** Both; decision record, build log and inherited spin/config files inspected. [docs/decisions/0006-throttle-neutral-at-trigger-center.md](https://github.com/griswaldbrooks/hamachi/blob/main/docs/decisions/0006-throttle-neutral-at-trigger-center.md) [docs/competition-2026-06-06-build-log.md](https://github.com/griswaldbrooks/hamachi/blob/main/docs/competition-2026-06-06-build-log.md)

3. **Robot context:** Plans include competing underweight in 1 kg class; actual completed combat result/max RPM not found. [decision](https://github.com/griswaldbrooks/hamachi/blob/main/docs/decisions/0003-compete-underweight-in-1kg-class.md)

4. **Hardware:** ItsyBitsy 32U4, H3LIS331, MEUS ME-8B transmitter, receiver PWM, one motor D9, IRLB8721PBF FET, Schottky, 4700 uF cap, heading LED. Exact drive motor not found in inspected log. [docs/competition-2026-06-06-build-log.md](https://github.com/griswaldbrooks/hamachi/blob/main/docs/competition-2026-06-06-build-log.md)

5. **Heading sensing and placement:** OpenMelt single radial sensor; startup raw offset around −4.9 g reported before calibration. Installed radius not recorded. [docs/competition-2026-06-06-build-log.md](https://github.com/griswaldbrooks/hamachi/blob/main/docs/competition-2026-06-06-build-log.md)

6. **Angle / RPM algorithm, filtering and rate:** Inherited OpenMelt centripetal period scheduler; new estimation math not established. [openmelt/spin_control.cpp](https://github.com/griswaldbrooks/hamachi/blob/main/openmelt/spin_control.cpp)

7. **Drift handling:** Inherited manual heading/radius trim. [openmelt/spin_control.cpp](https://github.com/griswaldbrooks/hamachi/blob/main/openmelt/spin_control.cpp)

8. **Translation timing and mapping:** Binary motor power windows on one connected motor; phase2 signal exists but unconnected, second BOM motor is spare. [docs/competition-2026-06-06-build-log.md](https://github.com/griswaldbrooks/hamachi/blob/main/docs/competition-2026-06-06-build-log.md)

9. **Heading indicator:** Single 5 mm heading LED plus 100 ohm resistor; inherited timing. [docs/competition-2026-06-06-build-log.md](https://github.com/griswaldbrooks/hamachi/blob/main/docs/competition-2026-06-06-build-log.md)

10. **Calibration:** Idle pulse raised 1250→1550 us to make trigger center 1507 us command 0; full threshold 1850 us. Author reports 16/16 bench samples at 0 and 100. [docs/decisions/0006-throttle-neutral-at-trigger-center.md](https://github.com/griswaldbrooks/hamachi/blob/main/docs/decisions/0006-throttle-neutral-at-trigger-center.md)

11. **Controls, modes and failsafes:** CH1 steering→D7, CH2 trigger→D0, CH4 three-position F/B→D1. Author reports TX-off while throttle high drops throttle to 0, although receiver continues failsafe pulses and RCHealth stays 1. [docs/competition-2026-06-06-build-log.md](https://github.com/griswaldbrooks/hamachi/blob/main/docs/competition-2026-06-06-build-log.md)

12. **Notable ideas:** Concrete correction for spring-centered throttle and documentation that continuing RC pulses do not prove RF connection. [docs/decisions/0006-throttle-neutral-at-trigger-center.md](https://github.com/griswaldbrooks/hamachi/blob/main/docs/decisions/0006-throttle-neutral-at-trigger-center.md)

13. **Problems, failures and evidence limits:** Wrong receiver mapping, 2-state CH3 unsuitable for F/B neutral, radio trim insufficient, absent sensor still returns plausible reading, USB-backfed battery reading. Final spin/config/max RPM blanks remain. [docs/competition-2026-06-06-build-log.md](https://github.com/griswaldbrooks/hamachi/blob/main/docs/competition-2026-06-06-build-log.md)

14. **License:** Inherited OpenMelt licensing stated in README; new standalone grant not found in inspected files. [readme.md](https://github.com/griswaldbrooks/hamachi/blob/main/readme.md)

<a id="p073"></a>

## P073. D.O.N.U.T. — Cameron Cox

1. **Name / author / links / activity:** [D.O.N.U.T. — Cameron Cox](https://github.com/CameronCox123/D.O.N.U.T); push 2025-02-24 UTC. [metadata](https://api.github.com/repos/CameronCox123/D.O.N.U.T).

2. **Source type and actual inspection:** Both; README read and repository tree inspected; implementation not independently port-validated. [fork metadata](https://api.github.com/repos/CameronCox123/D.O.N.U.T)

3. **Robot context:** not found.

4. **Hardware:** README lists ESP32, SparkFun H3LIS331DL, FlySky FS-i6/iA6, 45 A LANRC BLHeli_S ESC, 4S 650 mAh 100C, PROPDRIVE v2 2836 1000 KV, heading LED. [readme.md](https://github.com/CameronCox123/D.O.N.U.T/blob/main/readme.md)

5. **Heading sensing and placement:** Centripetal acceleration with effective sensor radius; actual placement not found. [readme.md](https://github.com/CameronCox123/D.O.N.U.T/blob/main/readme.md)

6. **Angle / RPM algorithm, filtering and rate:** README describes OpenMelt g/r→RPM method; filtering/update rate specific to this build not found. [readme.md](https://github.com/CameronCox123/D.O.N.U.T/blob/main/readme.md)

7. **Drift handling:** Driver left/right heading and trim. [readme.md](https://github.com/CameronCox123/D.O.N.U.T/blob/main/readme.md)

8. **Translation timing and mapping:** README repeats OpenMelt binary-throttle windows, 180° phase alternation and 490 Hz PWM option. This description is inherited and not verification of a working ESP32/brushless port. [readme.md](https://github.com/CameronCox123/D.O.N.U.T/blob/main/readme.md)

9. **Heading indicator:** Once-per-rotation heading LED. [readme.md](https://github.com/CameronCox123/D.O.N.U.T/blob/main/readme.md)

10. **Calibration:** Interactive zero/radius/LED offset, EEPROM inherited setup. [readme.md](https://github.com/CameronCox123/D.O.N.U.T/blob/main/readme.md)

11. **Controls, modes and failsafes:** Three RC channels; README repeats watchdog, zero-throttle boot and ~1 s stale-signal stop. Own-build failsafe test not found. [readme.md](https://github.com/CameronCox123/D.O.N.U.T/blob/main/readme.md)

12. **Notable ideas:** Distinct named project with expanded hardware list; other upstream changes not established. [readme.md](https://github.com/CameronCox123/D.O.N.U.T/blob/main/readme.md)

13. **Problems, failures and evidence limits:** Inherited cautions about LED visibility, power/I2C issues do not establish this author's own observed failures. [readme.md](https://github.com/CameronCox123/D.O.N.U.T/blob/main/readme.md)

14. **License:** Specific new license not found; upstream OpenMelt2 license remains relevant. [readme.md](https://github.com/CameronCox123/D.O.N.U.T/blob/main/readme.md)

<a id="p074"></a>

## P074. Dark Melty — ssharp-source

1. **Name / author / links / activity:** [Dark Melty — ssharp-source](https://github.com/ssharp-source/dark_melty); push 2023-10-18 UTC. [metadata](https://api.github.com/repos/ssharp-source/dark_melty).

2. **Source type and actual inspection:** Code repository with written plans; README read, changed firmware not inspected. [README.md](https://github.com/ssharp-source/dark_melty/blob/master/README.md)

3. **Robot context:** not found.

4. **Hardware:** Planned STM32 Blue Pill, backup ATmega328; author bought EVAL-ADXL375 after ADXL193 obsolescence; FingerTech brushless controller mentioned. Other exact parts not found. [README.md](https://github.com/ssharp-source/dark_melty/blob/master/README.md)

5. **Heading sensing and placement:** High-g acceleration planned; installed radius not found. [README.md](https://github.com/ssharp-source/dark_melty/blob/master/README.md)

6. **Angle / RPM algorithm, filtering and rate:** FIR filtering is a stated goal; coefficients, rate and implemented math not found. [README.md](https://github.com/ssharp-source/dark_melty/blob/master/README.md)

7. **Drift handling:** External frame reference considered but not established. [README.md](https://github.com/ssharp-source/dark_melty/blob/master/README.md)

8. **Translation timing and mapping:** Author proposes continuous two-wheel operation with opposite signs in different 180° sectors; no verified implementation found in inspected text. [README.md](https://github.com/ssharp-source/dark_melty/blob/master/README.md)

9. **Heading indicator:** POV text/shape proposed, not confirmed implemented. [README.md](https://github.com/ssharp-source/dark_melty/blob/master/README.md)

10. **Calibration:** not found.

11. **Controls, modes and failsafes:** not found.

12. **Notable ideas:** Hardware retargeting and signed half-turn drive concept preserved as planned. [README.md](https://github.com/ssharp-source/dark_melty/blob/master/README.md)

13. **Problems, failures and evidence limits:** Author says intended September completion was missed and rewrite scaled back toward Arduino; foam/hard-wheel notes partly inherited, not established as own measured results. [README.md](https://github.com/ssharp-source/dark_melty/blob/master/README.md)

14. **License:** New license not found; upstream OpenMelt provenance confirmed by fork metadata. [metadata](https://api.github.com/repos/ssharp-source/dark_melty)

<a id="p075"></a>

## P075. Eyeliner / Eyeliner Evo — Caleb012711

1. **Name / author / links / activity:** [Eyeliner / Eyeliner Evo — Caleb012711](https://github.com/Caleb012711/meltybrain-3lb); push 2026-10-04 UTC. [metadata](https://api.github.com/repos/Caleb012711/meltybrain-3lb).

2. **Source type and actual inspection:** Both repository code and documentation exist; README/checkpoint inspected, control firmware not read. Do not treat generated CAD/bench/software claims as completed combat testing. [README.md](https://github.com/Caleb012711/meltybrain-3lb/blob/main/README.md) [HANDOFF-CHECKPOINT.md](https://github.com/Caleb012711/meltybrain-3lb/blob/main/HANDOFF-CHECKPOINT.md)

3. **Robot context:** 3 lb target, 140 mm TPU body, 229.76 mm weapon reach in README. Reported model mass 1240.8 g in checkpoint vs 1252.4 g in README; not verified weighing. Competition result not found. [README.md](https://github.com/Caleb012711/meltybrain-3lb/blob/main/README.md) [HANDOFF-CHECKPOINT.md](https://github.com/Caleb012711/meltybrain-3lb/blob/main/HANDOFF-CHECKPOINT.md)

4. **Hardware:** Teensy 4.0, dual H3LIS331DLTR, PROPDRIVE v2 2836 1200 KV hubs, dual 4S packs, AM32/DShot600, ELRS, VL53L4CD ToF, Cree XML-2 heading LED, titanium cleats/AR500 teeth described. Orange Pi/Pi supervisor references vary by design stage. [README.md](https://github.com/Caleb012711/meltybrain-3lb/blob/main/README.md) [HANDOFF-CHECKPOINT.md](https://github.com/Caleb012711/meltybrain-3lb/blob/main/HANDOFF-CHECKPOINT.md)

5. **Heading sensing and placement:** Planned opposed sensors at ±25 mm, clocked 45°; radial common-mode cancellation described. [README.md](https://github.com/Caleb012711/meltybrain-3lb/blob/main/README.md)

6. **Angle / RPM algorithm, filtering and rate:** README equation omega=sqrt((ar1+ar2)/(2Rnom)); claimed 8 kHz motor updates. Actual code path/filtering not inspected, so implementation not established. [README.md](https://github.com/Caleb012711/meltybrain-3lb/blob/main/README.md)

7. **Drift handling:** Opposed accelerometers and spin-scan ToF autonomy described; operational heading/drift measurements not found. [README.md](https://github.com/Caleb012711/meltybrain-3lb/blob/main/README.md)

8. **Translation timing and mapping:** Directional motor modulation stated; exact waveform/phase not found in inspected text. Source: [Eyeliner / Eyeliner Evo — Caleb012711](https://github.com/Caleb012711/meltybrain-3lb).

9. **Heading indicator:** Planned 15° green heading window. [README.md](https://github.com/Caleb012711/meltybrain-3lb/blob/main/README.md)

10. **Calibration:** Calibration procedure/results not found in inspected material. Source: [Eyeliner / Eyeliner Evo — Caleb012711](https://github.com/Caleb012711/meltybrain-3lb).

11. **Controls, modes and failsafes:** ELRS/CRSF manual and AUTO_AI_HUNT described; actual failsafe tests not found. [README.md](https://github.com/Caleb012711/meltybrain-3lb/blob/main/README.md)

12. **Notable ideas:** Extensive model/CAD/manufacturing assets, shared web test lab and autonomous opponent-bearing concept. [README.md](https://github.com/Caleb012711/meltybrain-3lb/blob/main/README.md)

13. **Problems, failures and evidence limits:** Checkpoint next actions include procurement/fabrication; published energy, speed, balance precision and vibration percentages are design/calculation claims, not verified physical performance. [HANDOFF-CHECKPOINT.md](https://github.com/Caleb012711/meltybrain-3lb/blob/main/HANDOFF-CHECKPOINT.md)

14. **License:** not found.

<a id="p076"></a>

## P076. Jackson Gray — MIT inertial measurement hardware study

1. **Name / author / links / activity:** Jackson Gray, MIT6.101, spring2020. [Final report](https://web.mit.edu/6.101/www/s2020/projects/jackmaxg_Project_Final_Report.pdf).

2. **Source type and actual inspection:** Technical report with circuit simulations read; separate from jackmaxg/melty code entry. [report](https://web.mit.edu/6.101/www/s2020/projects/jackmaxg_Project_Final_Report.pdf).

3. **Robot context:** Class/size/event: not found. [report](https://web.mit.edu/6.101/www/s2020/projects/jackmaxg_Project_Final_Report.pdf).

4. **Hardware:** Teensy mentioned; BLDC phase sensing,940nm photodiode,1kHz IR beacon; exact device part numbers not found. [report](https://web.mit.edu/6.101/www/s2020/projects/jackmaxg_Project_Final_Report.pdf).

5. **Heading sensing and placement:** Radially outward photodiode detects driver-side beacon; wheel/motor rotation assists frequency estimation. [report](https://web.mit.edu/6.101/www/s2020/projects/jackmaxg_Project_Final_Report.pdf).

6. **Angle / RPM algorithm, filtering and rate:** Filter phase voltages, compare phase pairs with hysteresis and XOR; IR transimpedance/difference amplifier plus carrier extractor. [report](https://web.mit.edu/6.101/www/s2020/projects/jackmaxg_Project_Final_Report.pdf).

7. **Drift handling:** IR supplies absolute reference; motor velocity integration proposed fallback when IR unavailable. [report](https://web.mit.edu/6.101/www/s2020/projects/jackmaxg_Project_Final_Report.pdf).

8. **Translation timing and mapping:** Sinusoidal torque modulation explained; implemented controller pulse parameters not found. [report](https://web.mit.edu/6.101/www/s2020/projects/jackmaxg_Project_Final_Report.pdf).

9. **Heading indicator:** not found.

10. **Calibration:** not found.

11. **Controls, modes and failsafes:** not found.

12. **Notable ideas:** Nonlinear slew-rate limiter explored instead of simpleRC for motor phase filtering. [report](https://web.mit.edu/6.101/www/s2020/projects/jackmaxg_Project_Final_Report.pdf).

13. **Problems, failures and evidence limits:** Report describes SPICE evidence, uncertain photodiode-current estimates, reflection harmonics and mechanical limits near30Hz; assembled-system validation not established. [report](https://web.mit.edu/6.101/www/s2020/projects/jackmaxg_Project_Final_Report.pdf).

14. **License:** not found.

<a id="p077"></a>

## P077. MagnetoMelty — Team Mind Melt (GitLab)

1. **Name / author / links / activity:** [MagnetoMelty](https://gitlab.com/team-mind-melt/magnetomelty), created14May2022; page showed20commits,3branches,1tag.

2. **Source type and actual inspection:** Code repository; code not read because GitLab returned a loading shell and raw retrieval failed. Spencer Allen directly links this repository and magnetometer-investigation branch from his Meltycompass posts. [Theory link](https://www.swallenhardware.io/battlebots/2023/4/20/magnetometers-way-forward), [implementation link](https://www.swallenhardware.io/battlebots/2023/7/22/magnetometers-software-implementation), [branch](https://gitlab.com/team-mind-melt/magnetomelty/-/tree/magnetometer-investigation).

3. **Robot context:** not found.

4. **Hardware:** Related Spencer Allen2026 forum post names RP2040→RP2350 custom-board migration; identity link to this GitLab revision not conclusively established. [firsthand forum](https://forums.raspberrypi.com/viewtopic.php?t=397759).

5. **Heading sensing and placement:** Associated Meltycompass method is documented separately in the Spencer Allen source entry; repository code and mounting configuration were not inspected. Source: [MagnetoMelty](https://gitlab.com/team-mind-melt/magnetomelty).

6. **Angle / RPM algorithm, filtering and rate:** Related forum code discusses fixed-point FFT bin phase via atan2f and16-bit fixed-point radians; exact GitLab algorithm not established. Source: [MagnetoMelty](https://gitlab.com/team-mind-melt/magnetomelty).

7. **Drift handling:** not found.

8. **Translation timing and mapping:** not found.

9. **Heading indicator:** not found.

10. **Calibration:** not found.

11. **Controls, modes and failsafes:** not found.

12. **Notable ideas:** Crosslinked from another melty project's references; preserved as access-limited lead. Source: [MagnetoMelty](https://gitlab.com/team-mind-melt/magnetomelty).

13. **Problems, failures and evidence limits:** Forum author reports mixedC/C++ Pico float builtin compilation/linking problems, resolved byC helper file plus extern-C declarations; not proof of heading performance. Source: [MagnetoMelty](https://gitlab.com/team-mind-melt/magnetomelty).

14. **License:** not found.

<a id="p078"></a>

## P078. John Aduroja — MTSU meltybrain/autonomy thesis

1. **Name / author / links / activity:** John Aduroja, spring 2026, MTSU. [Thesis](https://jewlscholar.mtsu.edu/server/api/core/bitstreams/dce8a342-afca-4b0f-a525-21ab3b1e5d78/content).

2. **Source type and actual inspection:** Written thesis; design, Arduino listing and test passage read. Code not executed. Source: [Thesis](https://jewlscholar.mtsu.edu/server/api/core/bitstreams/dce8a342-afca-4b0f-a525-21ab3b1e5d78/content).

3. **Robot context:** Reported: 3lb, 10-inch TPU body; National Robotics Challenge, Marion Ohio. Source: [Thesis](https://jewlscholar.mtsu.edu/server/api/core/bitstreams/dce8a342-afca-4b0f-a525-21ab3b1e5d78/content).

4. **Hardware:** FlySky radio; schematic discusses MPU6050 and generic MCU. Autonomous listing: Arduino Uno, Sharp GP2Y0A21YK0F, bidirectional ESCs. Jetson/vision discussed separately. Source: [Thesis](https://jewlscholar.mtsu.edu/server/api/core/bitstreams/dce8a342-afca-4b0f-a525-21ab3b1e5d78/content).

5. **Heading sensing and placement:** Sensor placement: not found. Source: [Thesis](https://jewlscholar.mtsu.edu/server/api/core/bitstreams/dce8a342-afca-4b0f-a525-21ab3b1e5d78/content).

6. **Angle / RPM algorithm, filtering and rate:** Working phase/RPM estimator: not found in autonomous listing. Source: [Thesis](https://jewlscholar.mtsu.edu/server/api/core/bitstreams/dce8a342-afca-4b0f-a525-21ab3b1e5d78/content).

7. **Drift handling:** Implemented drift correction: not found. Source: [Thesis](https://jewlscholar.mtsu.edu/server/api/core/bitstreams/dce8a342-afca-4b0f-a525-21ab3b1e5d78/content).

8. **Translation timing and mapping:** Listing alternates scanning spin, straight charge, timed spin attack; rotation-synchronous translation not established. Source: [Thesis](https://jewlscholar.mtsu.edu/server/api/core/bitstreams/dce8a342-afca-4b0f-a525-21ab3b1e5d78/content).

9. **Heading indicator:** not found.

10. **Calibration:** Neutral ESC arming for 3s. Source: [Thesis](https://jewlscholar.mtsu.edu/server/api/core/bitstreams/dce8a342-afca-4b0f-a525-21ab3b1e5d78/content).

11. **Controls, modes and failsafes:** Scan/charge/attack state machine; verified radio-loss policy not found. Source: [Thesis](https://jewlscholar.mtsu.edu/server/api/core/bitstreams/dce8a342-afca-4b0f-a525-21ab3b1e5d78/content).

12. **Notable ideas:** Separates human control and autonomy/ethics discussion. Source: [Thesis](https://jewlscholar.mtsu.edu/server/api/core/bitstreams/dce8a342-afca-4b0f-a525-21ab3b1e5d78/content).

13. **Problems, failures and evidence limits:** Author reports functional NRC prototype, axle imbalance and tire wear reducing capacity over 40%; metric definition and independent verification not found. Source: [Thesis](https://jewlscholar.mtsu.edu/server/api/core/bitstreams/dce8a342-afca-4b0f-a525-21ab3b1e5d78/content).

14. **License:** not found.

<a id="p079"></a>

## P079. Beyblade of Death — Minhaz Abedin

1. **Name / author / links / activity:** Minhaz Abedin,[project journal](https://blueprint.hackclub.com/projects/1039); retrieved journal entries26November2025 and12January2026.

2. **Source type and actual inspection:** Build journal/search-indexed page text read; linked repository code not retrieved. Source: [project journal](https://blueprint.hackclub.com/projects/1039).

3. **Robot context:** Weight,size and competition: not found. Source: [project journal](https://blueprint.hackclub.com/projects/1039).

4. **Hardware:** RaspberryPi proposed for tracking; prototype3Dprint reported; other hardware not found. Source: [project journal](https://blueprint.hackclub.com/projects/1039).

5. **Heading sensing and placement:** not found.

6. **Angle / RPM algorithm, filtering and rate:** not found.

7. **Drift handling:** not found.

8. **Translation timing and mapping:** not found.

9. **Heading indicator:** not found.

10. **Calibration:** not found.

11. **Controls, modes and failsafes:** not found.

12. **Notable ideas:** Author reports writingC++ opponent-trackingAI withAI assistance. Source: [project journal](https://blueprint.hackclub.com/projects/1039).

13. **Problems, failures and evidence limits:** Hardware funds/access pending; schoolprinter bed too small forfullbuild; successful tracking ormeltytranslation not established. Source: [project journal](https://blueprint.hackclub.com/projects/1039).

14. **License:** not found.

<a id="p080"></a>

## P080. Gentry Clark — PocketBeagle meltybrain circuit

1. **Name / author / links / activity:** Gentry Clark,3May2018. [Project](https://www.hackster.io/gentry-clark2/melty-brain-combat-robot-circuit-ecbf2f).

2. **Source type and actual inspection:** Both; article and portions of attached C listing read. Source: [Project](https://www.hackster.io/gentry-clark2/melty-brain-combat-robot-circuit-ecbf2f).

3. **Robot context:** 3lb target; chassis/testing still next steps. Source: [Project](https://www.hackster.io/gentry-clark2/melty-brain-combat-robot-circuit-ecbf2f).

4. **Hardware:** PocketBeagle,ADXL193,930KV brushless,Hobbywing18A,FutabaR2004GF,3S,5Vregulator,headingLED. Source: [Project](https://www.hackster.io/gentry-clark2/melty-brain-combat-robot-circuit-ecbf2f).

5. **Heading sensing and placement:** Accelerometer radius/orientation: not found for prototype. Source: [Project](https://www.hackster.io/gentry-clark2/melty-brain-combat-robot-circuit-ecbf2f).

6. **Angle / RPM algorithm, filtering and rate:** Attached OpenMelt code estimates rotation from acceleration; listing retains AVR headers/registers,so working PocketBeagle port not established. Source: [Project](https://www.hackster.io/gentry-clark2/melty-brain-combat-robot-circuit-ecbf2f).

7. **Drift handling:** Driver heading trim inherited. Source: [Project](https://www.hackster.io/gentry-clark2/melty-brain-combat-robot-circuit-ecbf2f).

8. **Translation timing and mapping:** Half-turn on/off motor timing described. Source: [Project](https://www.hackster.io/gentry-clark2/melty-brain-combat-robot-circuit-ecbf2f).

9. **Heading indicator:** LED indicates intended direction. Source: [Project](https://www.hackster.io/gentry-clark2/melty-brain-combat-robot-circuit-ecbf2f).

10. **Calibration:** Attached inherited OpenMelt configuration; own calibration result not found. Source: [Project](https://www.hackster.io/gentry-clark2/melty-brain-combat-robot-circuit-ecbf2f).

11. **Controls, modes and failsafes:** Forward/back,left/right,throttle; tested own failsafe not found. Source: [Project](https://www.hackster.io/gentry-clark2/melty-brain-combat-robot-circuit-ecbf2f).

12. **Notable ideas:** PocketBeagle circuit concept distinct from unchanged AVR listing. Source: [Project](https://www.hackster.io/gentry-clark2/melty-brain-combat-robot-circuit-ecbf2f).

13. **Problems, failures and evidence limits:** Combat wiring,test chassis and tests incomplete in article. Source: [Project](https://www.hackster.io/gentry-clark2/melty-brain-combat-robot-circuit-ecbf2f).

14. **License:** Attached code statesCC BY-NC-SA3.0; own modifications' separate terms not found. Source: [Project](https://www.hackster.io/gentry-clark2/melty-brain-combat-robot-circuit-ecbf2f).

<a id="p081"></a>

## P081. OscarGRG14/TesselateF

1. **Identity, authorship, URLs and visible dates.** Repository owner: OscarGRG14. Inspected latest default-branch commit credited to Luke Ueda. Repository created 2025-08-13T11:01:08Z (UTC). Inspected commit e2af1fab3db0bd39c53b9b25013cac8b54c96240 dated 2025-08-05T20:58:02Z (UTC). GitHub identifies parent LukeUeda/TesselateF. [repository metadata](https://api.github.com/repos/OscarGRG14/TesselateF); [inspected commit](https://github.com/OscarGRG14/TesselateF/commit/e2af1fab3db0bd39c53b9b25013cac8b54c96240).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [teensy/include/Config.hpp](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/include/Config.hpp), [teensy/include/Constants.hpp](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/include/Constants.hpp), [teensy/src/LedController.cpp](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/src/LedController.cpp), [teensy/src/Receiver.cpp](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/src/Receiver.cpp), [teensy/src/Meltylock.cpp](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/src/Meltylock.cpp), [teensy/src/RobotState.cpp](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/src/RobotState.cpp), [teensy/src/Motor.cpp](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/src/Motor.cpp), [teensy/teensy.ino](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/teensy.ino), [README.md](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/README.md). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: behind, 0 commit(s) ahead and 2 behind at inspection. No fork-specific commits appear in that comparison; no new fork implementation is inferred. [upstream comparison](https://api.github.com/repos/LukeUeda/TesselateF/compare/main...OscarGRG14:main).

3. **Robot context and reported status.** Reported: featherweight meltybrain code. A named built robot, measured performance, competition results and wheel dimensions are not found. [README.md](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/README.md).

4. **Hardware and exact parts.** Confirmed in code: Teensy-targeted Arduino sketch, LIS331 interface and two motor outputs; the sketch describes the outputs as PPM for VESCs. Exact Teensy revision, motor, ESC model, battery and receiver model: not found. [teensy/teensy.ino](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/teensy.ino), [teensy/src/Meltylock.cpp](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/src/Meltylock.cpp).

5. **Heading sensing and mounting.** Confirmed: I2C accelerometer at0x19, interpreted ±400 g, X/Y magnitude; configured radius108.3943252563 mm. Relative heading comes from speed integration. Actual physical mounting metrology: not found. [teensy/src/Meltylock.cpp](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/src/Meltylock.cpp), [teensy/include/Constants.hpp](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/include/Constants.hpp).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed in code: Meltylock::calculateAngularVelocity computes a=sqrt(ax²+ay²), then angular speed=sqrt(a×1000/abs(radius))×RAD_TO_DEG×(1+translation×translation_offset_adjust). update() integrates this plus steering using micros() elapsed time and wraps heading to ±180°. Sensor ODR is configured to 400 Hz; a high-pass coefficient is selected, but an independently verified effective filter response and measured loop rate are not found. [teensy/src/Meltylock.cpp](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/src/Meltylock.cpp).

7. **Drift and correction.** Confirmed in code: steering adds a heading-rate term; radius and translation-offset adjustment inputs modify model parameters over elapsed time. Measured drift, automatic long-term absolute correction and validation of the translation compensation term: not found. [teensy/src/Meltylock.cpp](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/src/Meltylock.cpp).

8. **Translation timing, phase width and stick mapping.** Confirmed in code: translation uses clamped sqrt(stickX²+stickY²) magnitude and atan2(stickX,stickY) direction. Heading plus target angle selects one of two 180° halves; one motor is increased and the other decreased, swapping roles each half. There is no separately configured narrow pulse window in this inspected path. Exact coefficients are defined outside the main sketch. [teensy/teensy.ino](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/teensy.ino), [teensy/src/Meltylock.cpp](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/src/Meltylock.cpp).

9. **Heading LED/display.** Confirmed: five digital LEDs on pins5–9; SIMPLE_ARC turns all on within ±25° heading; tank uses loading animation and failsafe all-on. Physical placement/brightness/visibility tests: not found. [teensy/src/LedController.cpp](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/src/LedController.cpp), [teensy/include/Constants.hpp](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/include/Constants.hpp).

10. **Calibration and persistence.** Confirmed in code: RADIUS_ADJUST changes radius when the translation stick is centered and translation-offset adjustment when translating. Persistence and a documented setup procedure: not found in the inspected files. [teensy/teensy.ino](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/teensy.ino), [teensy/src/Meltylock.cpp](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/src/Meltylock.cpp).

11. **Controls, modes, arming and failsafe.** Confirmed: six interrupt-captured RC inputs; Receiver::inFailsafe tests age of the last pulse against1000 ms. Any channel edge refreshes that shared timestamp. Failsafe disables motors; tank/melty/calibration modes use two switches. This is source behavior, not a verified independent timeout per channel. [teensy/src/Receiver.cpp](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/src/Receiver.cpp), [teensy/include/Constants.hpp](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/include/Constants.hpp), [teensy/teensy.ino](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/teensy.ino).

12. **Distinctive ideas and implementation.** Distinctive implementation: two-axis acceleration magnitude and a continuously integrated model with a stick-selected translation direction. Runtime parameter adjustment is part of the control path; no experiment proving its accuracy is supplied in the inspected material. [teensy/src/Meltylock.cpp](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/src/Meltylock.cpp), [teensy/teensy.ino](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/teensy.ino).

13. **Author-reported problems, failures and evidence limits.** Reported in the inspected latest-commit history: accelerometer timeout recovery was being attempted. Code resets Wire after a slow read. Confirmed successful recovery testing, impact testing and drift measurements: not found. [inspected commit](https://github.com/OscarGRG14/TesselateF/commit/e2af1fab3db0bd39c53b9b25013cac8b54c96240), [teensy/src/Meltylock.cpp](https://github.com/OscarGRG14/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/src/Meltylock.cpp).

14. **License and reuse notice.** GitHub repository metadata identifies MIT. This survey did not audit all dependency or asset licenses. [repository metadata](https://api.github.com/repos/OscarGRG14/TesselateF).

<a id="p082"></a>

## P082. mechovation/TesselateF

1. **Identity, authorship, URLs and visible dates.** Repository owner: mechovation. Inspected latest default-branch commit credited to Luke Ueda. Repository created 2025-08-11T10:00:06Z (UTC). Inspected commit e2af1fab3db0bd39c53b9b25013cac8b54c96240 dated 2025-08-05T20:58:02Z (UTC). GitHub identifies parent LukeUeda/TesselateF. [repository metadata](https://api.github.com/repos/mechovation/TesselateF); [inspected commit](https://github.com/mechovation/TesselateF/commit/e2af1fab3db0bd39c53b9b25013cac8b54c96240).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [teensy/src/Meltylock.cpp](https://github.com/mechovation/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/src/Meltylock.cpp), [teensy/src/RobotState.cpp](https://github.com/mechovation/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/src/RobotState.cpp), [teensy/src/Motor.cpp](https://github.com/mechovation/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/src/Motor.cpp), [teensy/teensy.ino](https://github.com/mechovation/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/teensy.ino), [README.md](https://github.com/mechovation/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/README.md). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: behind, 0 commit(s) ahead and 2 behind at inspection. No fork-specific commits appear in that comparison; no new fork implementation is inferred. [upstream comparison](https://api.github.com/repos/LukeUeda/TesselateF/compare/main...mechovation:main).

3. **Robot context and reported status.** Reported: featherweight meltybrain code. A named built robot, measured performance, competition results and wheel dimensions are not found. [README.md](https://github.com/mechovation/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/README.md).

4. **Hardware and exact parts.** Confirmed in code: Teensy-targeted Arduino sketch, LIS331 interface and two motor outputs; the sketch describes the outputs as PPM for VESCs. Exact Teensy revision, motor, ESC model, battery and receiver model: not found. [teensy/teensy.ino](https://github.com/mechovation/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/teensy.ino), [teensy/src/Meltylock.cpp](https://github.com/mechovation/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/src/Meltylock.cpp).

5. **Heading sensing and mounting.** Confirmed in code: I2C accelerometer at 0x19, high range interpreted as 400 g, using X/Y acceleration magnitude. Heading is inferred from angular speed and elapsed time; no absolute heading reference is used in the inspected path. Actual physical mounting measurements: not found. [teensy/src/Meltylock.cpp](https://github.com/mechovation/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/src/Meltylock.cpp).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed in code: Meltylock::calculateAngularVelocity computes a=sqrt(ax²+ay²), then angular speed=sqrt(a×1000/abs(radius))×RAD_TO_DEG×(1+translation×translation_offset_adjust). update() integrates this plus steering using micros() elapsed time and wraps heading to ±180°. Sensor ODR is configured to 400 Hz; a high-pass coefficient is selected, but an independently verified effective filter response and measured loop rate are not found. [teensy/src/Meltylock.cpp](https://github.com/mechovation/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/src/Meltylock.cpp).

7. **Drift and correction.** Confirmed in code: steering adds a heading-rate term; radius and translation-offset adjustment inputs modify model parameters over elapsed time. Measured drift, automatic long-term absolute correction and validation of the translation compensation term: not found. [teensy/src/Meltylock.cpp](https://github.com/mechovation/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/src/Meltylock.cpp).

8. **Translation timing, phase width and stick mapping.** Confirmed in code: translation uses clamped sqrt(stickX²+stickY²) magnitude and atan2(stickX,stickY) direction. Heading plus target angle selects one of two 180° halves; one motor is increased and the other decreased, swapping roles each half. There is no separately configured narrow pulse window in this inspected path. Exact coefficients are defined outside the main sketch. [teensy/teensy.ino](https://github.com/mechovation/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/teensy.ino), [teensy/src/Meltylock.cpp](https://github.com/mechovation/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/src/Meltylock.cpp).

9. **Heading LED/display.** Confirmed in code: MELTY and RADIUS_ADJUST request SIMPLE_ARC; tank drive requests LOADING; failsafe requests FAILSAFE_PATTERN. Mechanical placement, brightness and visibility tests: not found. [teensy/teensy.ino](https://github.com/mechovation/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/teensy.ino).

10. **Calibration and persistence.** Confirmed in code: RADIUS_ADJUST changes radius when the translation stick is centered and translation-offset adjustment when translating. Persistence and a documented setup procedure: not found in the inspected files. [teensy/teensy.ino](https://github.com/mechovation/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/teensy.ino), [teensy/src/Meltylock.cpp](https://github.com/mechovation/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/src/Meltylock.cpp).

11. **Controls, modes, arming and failsafe.** Confirmed in code: six interrupt-driven receiver inputs; RobotState selects failsafe, tank, melty, radius adjustment, translation-offset adjustment or LED pattern selection. The main switch handles failsafe/tank/melty/radius adjustment and disables both motors in its default branch; names in the mode enum alone do not establish working modes. Receiver failure selects motor disable. [teensy/teensy.ino](https://github.com/mechovation/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/teensy.ino), [teensy/src/RobotState.cpp](https://github.com/mechovation/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/src/RobotState.cpp).

12. **Distinctive ideas and implementation.** Distinctive implementation: two-axis acceleration magnitude and a continuously integrated model with a stick-selected translation direction. Runtime parameter adjustment is part of the control path; no experiment proving its accuracy is supplied in the inspected material. [teensy/src/Meltylock.cpp](https://github.com/mechovation/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/src/Meltylock.cpp), [teensy/teensy.ino](https://github.com/mechovation/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/teensy.ino).

13. **Author-reported problems, failures and evidence limits.** Reported in the inspected latest-commit history: accelerometer timeout recovery was being attempted. Code resets Wire after a slow read. Confirmed successful recovery testing, impact testing and drift measurements: not found. [inspected commit](https://github.com/mechovation/TesselateF/commit/e2af1fab3db0bd39c53b9b25013cac8b54c96240), [teensy/src/Meltylock.cpp](https://github.com/mechovation/TesselateF/blob/e2af1fab3db0bd39c53b9b25013cac8b54c96240/teensy/src/Meltylock.cpp).

14. **License and reuse notice.** GitHub repository metadata identifies MIT. This survey did not audit all dependency or asset licenses. [repository metadata](https://api.github.com/repos/mechovation/TesselateF).

<a id="p083"></a>

## P083. 13djwright/TesselateMeltyFork

1. **Identity, authorship, URLs and visible dates.** Repository owner: 13djwright. Inspected latest default-branch commit credited to Luke Ueda. Repository created 2025-11-10T02:32:48Z (UTC). Inspected commit be723a45c5e1ce119b98b6c251c9d3bd641fe22f dated 2025-08-14T10:52:44Z (UTC). GitHub identifies parent LukeUeda/TesselateF. [repository metadata](https://api.github.com/repos/13djwright/TesselateMeltyFork); [inspected commit](https://github.com/13djwright/TesselateMeltyFork/commit/be723a45c5e1ce119b98b6c251c9d3bd641fe22f).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [teensy/src/Meltylock.cpp](https://github.com/13djwright/TesselateMeltyFork/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/src/Meltylock.cpp), [teensy/src/RobotState.cpp](https://github.com/13djwright/TesselateMeltyFork/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/src/RobotState.cpp), [teensy/src/Motor.cpp](https://github.com/13djwright/TesselateMeltyFork/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/src/Motor.cpp), [teensy/teensy.ino](https://github.com/13djwright/TesselateMeltyFork/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/teensy.ino), [README.md](https://github.com/13djwright/TesselateMeltyFork/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/README.md). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: identical, 0 commit(s) ahead and 0 behind at inspection. No fork-specific commits appear in that comparison; no new fork implementation is inferred. [upstream comparison](https://api.github.com/repos/LukeUeda/TesselateF/compare/main...13djwright:main).

3. **Robot context and reported status.** Reported: featherweight meltybrain code. A named built robot, measured performance, competition results and wheel dimensions are not found. [README.md](https://github.com/13djwright/TesselateMeltyFork/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/README.md).

4. **Hardware and exact parts.** Confirmed in code: Teensy-targeted Arduino sketch, LIS331 interface and two motor outputs; the sketch describes the outputs as PPM for VESCs. Exact Teensy revision, motor, ESC model, battery and receiver model: not found. [teensy/teensy.ino](https://github.com/13djwright/TesselateMeltyFork/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/teensy.ino), [teensy/src/Meltylock.cpp](https://github.com/13djwright/TesselateMeltyFork/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/src/Meltylock.cpp).

5. **Heading sensing and mounting.** Confirmed in code: I2C accelerometer at 0x19, high range interpreted as 400 g, using X/Y acceleration magnitude. Heading is inferred from angular speed and elapsed time; no absolute heading reference is used in the inspected path. Actual physical mounting measurements: not found. [teensy/src/Meltylock.cpp](https://github.com/13djwright/TesselateMeltyFork/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/src/Meltylock.cpp).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed in code: Meltylock::calculateAngularVelocity computes a=sqrt(ax²+ay²), then angular speed=sqrt(a×1000/abs(radius))×RAD_TO_DEG×(1+translation×translation_offset_adjust). update() integrates this plus steering using micros() elapsed time and wraps heading to ±180°. Sensor ODR is configured to 400 Hz; a high-pass coefficient is selected, but an independently verified effective filter response and measured loop rate are not found. [teensy/src/Meltylock.cpp](https://github.com/13djwright/TesselateMeltyFork/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/src/Meltylock.cpp).

7. **Drift and correction.** Confirmed in code: steering adds a heading-rate term; radius and translation-offset adjustment inputs modify model parameters over elapsed time. Measured drift, automatic long-term absolute correction and validation of the translation compensation term: not found. [teensy/src/Meltylock.cpp](https://github.com/13djwright/TesselateMeltyFork/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/src/Meltylock.cpp).

8. **Translation timing, phase width and stick mapping.** Confirmed in code: translation uses clamped sqrt(stickX²+stickY²) magnitude and atan2(stickX,stickY) direction. Heading plus target angle selects one of two 180° halves; one motor is increased and the other decreased, swapping roles each half. There is no separately configured narrow pulse window in this inspected path. Exact coefficients are defined outside the main sketch. [teensy/teensy.ino](https://github.com/13djwright/TesselateMeltyFork/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/teensy.ino), [teensy/src/Meltylock.cpp](https://github.com/13djwright/TesselateMeltyFork/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/src/Meltylock.cpp).

9. **Heading LED/display.** Confirmed in code: MELTY and RADIUS_ADJUST request SIMPLE_ARC; tank drive requests LOADING; failsafe requests FAILSAFE_PATTERN. Mechanical placement, brightness and visibility tests: not found. [teensy/teensy.ino](https://github.com/13djwright/TesselateMeltyFork/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/teensy.ino).

10. **Calibration and persistence.** Confirmed in code: RADIUS_ADJUST changes radius when the translation stick is centered and translation-offset adjustment when translating. Persistence and a documented setup procedure: not found in the inspected files. [teensy/teensy.ino](https://github.com/13djwright/TesselateMeltyFork/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/teensy.ino), [teensy/src/Meltylock.cpp](https://github.com/13djwright/TesselateMeltyFork/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/src/Meltylock.cpp).

11. **Controls, modes, arming and failsafe.** Confirmed in code: six interrupt-driven receiver inputs; RobotState selects failsafe, tank, melty, radius adjustment, translation-offset adjustment or LED pattern selection. The main switch handles failsafe/tank/melty/radius adjustment and disables both motors in its default branch; names in the mode enum alone do not establish working modes. Receiver failure selects motor disable. [teensy/teensy.ino](https://github.com/13djwright/TesselateMeltyFork/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/teensy.ino), [teensy/src/RobotState.cpp](https://github.com/13djwright/TesselateMeltyFork/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/src/RobotState.cpp).

12. **Distinctive ideas and implementation.** Distinctive implementation: two-axis acceleration magnitude and a continuously integrated model with a stick-selected translation direction. Runtime parameter adjustment is part of the control path; no experiment proving its accuracy is supplied in the inspected material. [teensy/src/Meltylock.cpp](https://github.com/13djwright/TesselateMeltyFork/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/src/Meltylock.cpp), [teensy/teensy.ino](https://github.com/13djwright/TesselateMeltyFork/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/teensy.ino).

13. **Author-reported problems, failures and evidence limits.** Reported in the inspected latest-commit history: accelerometer timeout recovery was being attempted. Code resets Wire after a slow read. Confirmed successful recovery testing, impact testing and drift measurements: not found. [inspected commit](https://github.com/13djwright/TesselateMeltyFork/commit/be723a45c5e1ce119b98b6c251c9d3bd641fe22f), [teensy/src/Meltylock.cpp](https://github.com/13djwright/TesselateMeltyFork/blob/be723a45c5e1ce119b98b6c251c9d3bd641fe22f/teensy/src/Meltylock.cpp).

14. **License and reuse notice.** GitHub repository metadata identifies MIT. This survey did not audit all dependency or asset licenses. [repository metadata](https://api.github.com/repos/13djwright/TesselateMeltyFork).

<a id="p084"></a>

## P084. 13djwright/MeltyBrain

1. **Identity, authorship, URLs and visible dates.** Repository owner: 13djwright. Inspected latest default-branch commit credited to Danielle Skysdottir. Repository created 2025-11-09T17:31:51Z (UTC). Inspected commit 71cd20fc82610c7a3dd203e88907d089d40dcd2d dated 2024-05-17T00:25:02Z (UTC). GitHub identifies parent skysdottir/PotatoMelt. [repository metadata](https://api.github.com/repos/13djwright/MeltyBrain); [inspected commit](https://github.com/13djwright/MeltyBrain/commit/71cd20fc82610c7a3dd203e88907d089d40dcd2d).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [potatomelt/accel_handler.h](https://github.com/13djwright/MeltyBrain/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/accel_handler.h), [potatomelt/accel_handler.cpp](https://github.com/13djwright/MeltyBrain/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/accel_handler.cpp), [potatomelt/spin_control.cpp](https://github.com/13djwright/MeltyBrain/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/spin_control.cpp), [potatomelt/melty_config.h](https://github.com/13djwright/MeltyBrain/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/melty_config.h), [potatomelt/rc_handler.cpp](https://github.com/13djwright/MeltyBrain/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/rc_handler.cpp), [README.md](https://github.com/13djwright/MeltyBrain/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/README.md). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: identical, 0 commit(s) ahead and 0 behind at inspection. No fork-specific commits appear in that comparison; no new fork implementation is inferred. [upstream comparison](https://api.github.com/repos/skysdottir/PotatoMelt/compare/main...13djwright:main).

3. **Robot context and reported status.** Reported: PotatoMelt-derived translational-drift controller. The inherited README describes development hardware, not a verified robot built by this fork owner. Weight, wheel geometry and event results for this fork: not found. [README.md](https://github.com/13djwright/MeltyBrain/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/README.md).

4. **Hardware and exact parts.** Reported development parts: Adafruit ItsyBitsy 32u4, 16 MHz/5 V; Adafruit LIS331 I2C board; generic iBus receiver; Repeat Robotics dual AM32 ESC. Exact motors, battery and receiver model: not found. [README.md](https://github.com/13djwright/MeltyBrain/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/README.md).

5. **Heading sensing and mounting.** Confirmed in code: radial sensing uses LIS331 Y-axis force converted to g. Default effective radius is 2.91 cm; actual measured mounting geometry is not supplied. Heading is a relative phase estimated from rotational speed. [potatomelt/accel_handler.cpp](https://github.com/13djwright/MeltyBrain/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/accel_handler.cpp), [potatomelt/melty_config.h](https://github.com/13djwright/MeltyBrain/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/melty_config.h).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed in code: get_uncorrected_rpm computes sqrt(abs(g−zero)×89445/radius_cm). A table of eight RPM/correction pairs supports linear interpolation. spin_control converts corrected/steered RPM to a revolution interval; Timer3 compare ISR is configured at 2 kHz, while spin_one_iteration updates parameters then delays 20 ms. PID uses a 20 ms sample interval. A measured achieved rate or noise spectrum: not found. [potatomelt/accel_handler.cpp](https://github.com/13djwright/MeltyBrain/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/accel_handler.cpp), [potatomelt/spin_control.cpp](https://github.com/13djwright/MeltyBrain/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/spin_control.cpp).

7. **Drift and correction.** Confirmed in code and described in README: driver steering changes the estimated rotation interval; an RPM-dependent correction table is tuned until the beacon stops precessing. PID input remains uncorrected RPM in this snapshot, explicitly to avoid calibration bugs changing spin control. Residual drift measurements: not found. [potatomelt/spin_control.cpp](https://github.com/13djwright/MeltyBrain/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/spin_control.cpp), [README.md](https://github.com/13djwright/MeltyBrain/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/README.md).

8. **Translation timing, phase width and stick mapping.** Confirmed in code: forward/back translation exchanges high/low DShot commands over opposing 180° half rotations. Offset scales with signed forward/back stick displacement, base throttle and translation trim, with limits before DShot conversion. Left/right input steers the relative heading; omnidirectional translation is not implemented in this inspected path. [potatomelt/spin_control.cpp](https://github.com/13djwright/MeltyBrain/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/spin_control.cpp).

9. **Heading LED/display.** Confirmed in code: LED start/stop wrap around a calibrated percentage offset; width follows raw RPM/MAX_TARGET_RPM, clamped to 10–90% of a revolution. README describes fast idle blink, double config blink and precession-based adjustment. Physical beacon mounting and brightness: not found. [potatomelt/spin_control.cpp](https://github.com/13djwright/MeltyBrain/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/spin_control.cpp), [README.md](https://github.com/13djwright/MeltyBrain/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/README.md).

10. **Calibration and persistence.** Reported procedure: at rest hold the right stick backward for 1 s; entering config snapshots zero g. At eight stable speeds adjust until beacon precession stops, then toggle channel 6 to save points. Backward stick with rotation adjusts beacon offset; exit while stopped. EEPROM support is enabled. Independent successful calibration evidence: not found. [README.md](https://github.com/13djwright/MeltyBrain/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/README.md), [potatomelt/melty_config.h](https://github.com/13djwright/MeltyBrain/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/melty_config.h).

11. **Controls, modes, arming and failsafe.** Confirmed in code: iBus channel handling, tank mode, spin direction and translation-trim inputs. Config enables a 2 s watchdog, battery warning/critical-halt features, and a 3 s control-motion timeout. These are configured safeguards; a complete end-to-end failsafe test is not supplied. [potatomelt/rc_handler.cpp](https://github.com/13djwright/MeltyBrain/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/rc_handler.cpp), [potatomelt/melty_config.h](https://github.com/13djwright/MeltyBrain/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/melty_config.h).

12. **Distinctive ideas and implementation.** Distinctive inherited implementation: eight-point speed correction, separate raw-RPM speed PID and corrected phase estimate, and interrupt-driven DShot updates. No fork-owner-specific experiment or new control feature is established by the inspected default branch. [potatomelt/accel_handler.cpp](https://github.com/13djwright/MeltyBrain/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/accel_handler.cpp), [potatomelt/spin_control.cpp](https://github.com/13djwright/MeltyBrain/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/spin_control.cpp).

13. **Author-reported problems, failures and evidence limits.** Reported limitations: README calls this an early Arduino project and provides no fitness guarantee. Code comments explicitly distrust the correction-factor code enough to keep it out of the speed PID. A fork-owner-specific failure log or quantified test result: not found. [README.md](https://github.com/13djwright/MeltyBrain/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/README.md), [potatomelt/spin_control.cpp](https://github.com/13djwright/MeltyBrain/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/spin_control.cpp).

14. **License and reuse notice.** GitHub repository metadata identifies LGPL-2.1. This survey did not audit all dependency or asset licenses. [repository metadata](https://api.github.com/repos/13djwright/MeltyBrain).

<a id="p085"></a>

## P085. dinoceros/The-Wheel-of-Power

1. **Identity, authorship, URLs and visible dates.** Repository owner: dinoceros. Inspected latest default-branch commit credited to kakhtar. Repository created 2020-05-20T03:48:45Z (UTC). Inspected commit 42a2af3797f58ce75a015c7d00d09d00d2195d71 dated 2021-09-25T20:48:00Z (UTC). [repository metadata](https://api.github.com/repos/dinoceros/The-Wheel-of-Power); [inspected commit](https://github.com/dinoceros/The-Wheel-of-Power/commit/42a2af3797f58ce75a015c7d00d09d00d2195d71).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [WheelOfPower.ino](https://github.com/dinoceros/The-Wheel-of-Power/blob/42a2af3797f58ce75a015c7d00d09d00d2195d71/WheelOfPower.ino), [driver_station.py](https://github.com/dinoceros/The-Wheel-of-Power/blob/42a2af3797f58ce75a015c7d00d09d00d2195d71/driver_station.py). Hardware tests/builds/simulations were not run by this survey. Changes from upstream not established; no verified parent-branch comparison was available/performed.

3. **Robot context and reported status.** Reported repository context: antweight combat robot The Wheel of Power. The source has two independently controlled motors and melty/tank modes. Exact dimensions, mass measurements and event outcomes: not found in the inspected files. [repository metadata](https://api.github.com/repos/dinoceros/The-Wheel-of-Power), [WheelOfPower.ino](https://github.com/dinoceros/The-Wheel-of-Power/blob/42a2af3797f58ce75a015c7d00d09d00d2195d71/WheelOfPower.ino).

4. **Hardware and exact parts.** Confirmed: LIS331-family accelerometer over SPI, RadioHead RH_RF95 LoRa at 915 MHz, TimerOne motor output at 4 kHz, and a Python gamepad-to-RFM9x driver station. Exact MCU board, motor/ESC/battery and gamepad models: not found. [WheelOfPower.ino](https://github.com/dinoceros/The-Wheel-of-Power/blob/42a2af3797f58ce75a015c7d00d09d00d2195d71/WheelOfPower.ino), [driver_station.py](https://github.com/dinoceros/The-Wheel-of-Power/blob/42a2af3797f58ce75a015c7d00d09d00d2195d71/driver_station.py).

5. **Heading sensing and mounting.** Confirmed constants: forward radius 0.061755 m, reverse radius 0.06333 m; LED offset 2.67035 rad (comment: 153°). Actual mounting metrology: not found. [WheelOfPower.ino](https://github.com/dinoceros/The-Wheel-of-Power/blob/42a2af3797f58ce75a015c7d00d09d00d2195d71/WheelOfPower.ino).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed in melty_drive: X/Y magnitude gives a; signed omega is ±sqrt(abs(a/(radius+trim))); delta angle is the trapezoidal mean of current/previous omega times elapsed micros. Sensor is configured at 1 kHz, SPI at 1 MHz; actual estimator loop frequency is not measured here. [WheelOfPower.ino](https://github.com/dinoceros/The-Wheel-of-Power/blob/42a2af3797f58ce75a015c7d00d09d00d2195d71/WheelOfPower.ino).

7. **Drift and correction.** Confirmed: D-pad radius trim and right-stick heading-rate input provide manual correction. No measured cumulative drift or automatic absolute realignment is established. [WheelOfPower.ino](https://github.com/dinoceros/The-Wheel-of-Power/blob/42a2af3797f58ce75a015c7d00d09d00d2195d71/WheelOfPower.ino).

8. **Translation timing, phase width and stick mapping.** Confirmed: parser forces left_x=0, so live translation is forward/back despite vector math. Stick magnitude sets deflection=base_power×0.5×magnitude; the chosen motor receives +3×deflection and the other −deflection, swapping across half-turn error sign. stick_angle subtracts a signed 0.6 rad MOTOR_LAG_ANGLE. [WheelOfPower.ino](https://github.com/dinoceros/The-Wheel-of-Power/blob/42a2af3797f58ce75a015c7d00d09d00d2195d71/WheelOfPower.ino).

9. **Heading LED/display.** Confirmed: digital heading LED on pin 8, lit over an approximately 90° angular arc using a configured offset; separate power LED on A0. Physical viewing arrangement and brightness tests: not found. [WheelOfPower.ino](https://github.com/dinoceros/The-Wheel-of-Power/blob/42a2af3797f58ce75a015c7d00d09d00d2195d71/WheelOfPower.ino).

10. **Calibration and persistence.** Confirmed: radius trim is adjusted through D-pad controls; LED offset is hard-coded. An interactive zero-offset/EEPROM calibration procedure or complete setup guide: not found. [WheelOfPower.ino](https://github.com/dinoceros/The-Wheel-of-Power/blob/42a2af3797f58ce75a015c7d00d09d00d2195d71/WheelOfPower.ino).

11. **Controls, modes, arming and failsafe.** Confirmed: melty/tank/no-PWM modes; gamepad commands arrive through a framed LoRa packet. Melty control checks packet age over 1 s and sets spin power to zero. A comparable stale-data stop inside the inspected curvature/tank routine is not established. [WheelOfPower.ino](https://github.com/dinoceros/The-Wheel-of-Power/blob/42a2af3797f58ce75a015c7d00d09d00d2195d71/WheelOfPower.ino), [driver_station.py](https://github.com/dinoceros/The-Wheel-of-Power/blob/42a2af3797f58ce75a015c7d00d09d00d2195d71/driver_station.py).

12. **Distinctive ideas and implementation.** Distinctive implementation: custom radio driver station rather than a standard RC pulse receiver, SPI transaction protection between radio and accelerometer, and tank curvature drive alongside melty control. [WheelOfPower.ino](https://github.com/dinoceros/The-Wheel-of-Power/blob/42a2af3797f58ce75a015c7d00d09d00d2195d71/WheelOfPower.ino), [driver_station.py](https://github.com/dinoceros/The-Wheel-of-Power/blob/42a2af3797f58ce75a015c7d00d09d00d2195d71/driver_station.py).

13. **Author-reported problems, failures and evidence limits.** Author reports in latest commit: forward/reverse radii tuned after HBB 2021; motor-lag compensation appears reversed and may be compensating for something else; a radius-trimming bug was fixed. Source also describes a hang caused by radio SPI interference. These are reported observations, not reproduced tests. [inspected commit](https://github.com/dinoceros/The-Wheel-of-Power/commit/42a2af3797f58ce75a015c7d00d09d00d2195d71), [WheelOfPower.ino](https://github.com/dinoceros/The-Wheel-of-Power/blob/42a2af3797f58ce75a015c7d00d09d00d2195d71/WheelOfPower.ino).

14. **License and reuse notice.** License: not found in inspected repository metadata/material. Reuse terms are unresolved; a public repository alone is not treated as a license. [repository metadata](https://api.github.com/repos/dinoceros/The-Wheel-of-Power).

<a id="p086"></a>

## P086. SaintSampo/The-Wheel-of-Power

1. **Identity, authorship, URLs and visible dates.** Repository owner: SaintSampo. Inspected latest default-branch commit credited to kakhtar. Repository created 2021-03-25T09:05:14Z (UTC). Inspected commit 0fed1aa878872777ad0bc79a0350a65bae3e2b1e dated 2021-03-24T05:04:46Z (UTC). GitHub identifies parent dinoceros/The-Wheel-of-Power. [repository metadata](https://api.github.com/repos/SaintSampo/The-Wheel-of-Power); [inspected commit](https://github.com/SaintSampo/The-Wheel-of-Power/commit/0fed1aa878872777ad0bc79a0350a65bae3e2b1e).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [WheelOfPower.ino](https://github.com/SaintSampo/The-Wheel-of-Power/blob/0fed1aa878872777ad0bc79a0350a65bae3e2b1e/WheelOfPower.ino), [driver_station.py](https://github.com/SaintSampo/The-Wheel-of-Power/blob/0fed1aa878872777ad0bc79a0350a65bae3e2b1e/driver_station.py). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: behind, 0 commit(s) ahead and 12 behind at inspection. No fork-specific commits appear in that comparison; no new fork implementation is inferred. [upstream comparison](https://api.github.com/repos/dinoceros/The-Wheel-of-Power/compare/master...SaintSampo:master).

3. **Robot context and reported status.** Reported repository context: antweight combat robot The Wheel of Power. The source has two independently controlled motors and melty/tank modes. Exact dimensions, mass measurements and event outcomes: not found in the inspected files. [repository metadata](https://api.github.com/repos/SaintSampo/The-Wheel-of-Power), [WheelOfPower.ino](https://github.com/SaintSampo/The-Wheel-of-Power/blob/0fed1aa878872777ad0bc79a0350a65bae3e2b1e/WheelOfPower.ino).

4. **Hardware and exact parts.** Confirmed: LIS331-family accelerometer over SPI, RadioHead RH_RF95 LoRa at 915 MHz, TimerOne motor output at 4 kHz, and a Python gamepad-to-RFM9x driver station. Exact MCU board, motor/ESC/battery and gamepad models: not found. [WheelOfPower.ino](https://github.com/SaintSampo/The-Wheel-of-Power/blob/0fed1aa878872777ad0bc79a0350a65bae3e2b1e/WheelOfPower.ino), [driver_station.py](https://github.com/SaintSampo/The-Wheel-of-Power/blob/0fed1aa878872777ad0bc79a0350a65bae3e2b1e/driver_station.py).

5. **Heading sensing and mounting.** Confirmed constants: effective radius 0.06108 m; commented reverse value 0.06033 m; LED offset −1.0210177 rad described as CAD angle with a 27° clockwise fudge. Physical validation: not found. [WheelOfPower.ino](https://github.com/SaintSampo/The-Wheel-of-Power/blob/0fed1aa878872777ad0bc79a0350a65bae3e2b1e/WheelOfPower.ino).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed: angular velocity is sqrt(abs(centripetal_accel/effective_radius)); elapsed micros() advances phase. The main loop reads sensor and radio each pass; 4 kHz is motor pulse frequency, not a demonstrated heading-estimator rate. Additional temporal acceleration filter and measured loop rate: not found. [WheelOfPower.ino](https://github.com/SaintSampo/The-Wheel-of-Power/blob/0fed1aa878872777ad0bc79a0350a65bae3e2b1e/WheelOfPower.ino).

7. **Drift and correction.** Confirmed: Start/Back change effective-radius trim by 0.00025 m and together reset it; right stick changes integrated heading at a configured rate. Measured cumulative drift and automatic absolute realignment: not found. [WheelOfPower.ino](https://github.com/SaintSampo/The-Wheel-of-Power/blob/0fed1aa878872777ad0bc79a0350a65bae3e2b1e/WheelOfPower.ino).

8. **Translation timing, phase width and stick mapping.** Confirmed: direction is deliberately forward/back using atan2(0,−leftY), while magnitude is clamped sqrt(leftX²+leftY²). Deflection=(power−neutral)×0.5×magnitude; selected motor adds 3×deflection and other subtracts deflection across opposing half-turn sectors. PWM outputs clamp between neutral and maximum. No separate narrow pulse-width setting is found. [WheelOfPower.ino](https://github.com/SaintSampo/The-Wheel-of-Power/blob/0fed1aa878872777ad0bc79a0350a65bae3e2b1e/WheelOfPower.ino).

9. **Heading LED/display.** Confirmed: digital heading LED on pin 8, lit over an approximately 90° angular arc using a configured offset; separate power LED on A0. Physical viewing arrangement and brightness tests: not found. [WheelOfPower.ino](https://github.com/SaintSampo/The-Wheel-of-Power/blob/0fed1aa878872777ad0bc79a0350a65bae3e2b1e/WheelOfPower.ino).

10. **Calibration and persistence.** Confirmed: Start/Back radius trim, fixed radius/LED constants and commented reverse-direction tuning notes. Interactive zero/EEPROM calibration and a complete successful calibration log: not found. [WheelOfPower.ino](https://github.com/SaintSampo/The-Wheel-of-Power/blob/0fed1aa878872777ad0bc79a0350a65bae3e2b1e/WheelOfPower.ino).

11. **Controls, modes, arming and failsafe.** Confirmed: melty/tank/no-PWM modes; gamepad commands arrive through a framed LoRa packet. Melty control checks packet age over 1 s and sets spin power to zero. A comparable stale-data stop inside the inspected curvature/tank routine is not established. [WheelOfPower.ino](https://github.com/SaintSampo/The-Wheel-of-Power/blob/0fed1aa878872777ad0bc79a0350a65bae3e2b1e/WheelOfPower.ino), [driver_station.py](https://github.com/SaintSampo/The-Wheel-of-Power/blob/0fed1aa878872777ad0bc79a0350a65bae3e2b1e/driver_station.py).

12. **Distinctive ideas and implementation.** Distinctive implementation: custom radio driver station rather than a standard RC pulse receiver, SPI transaction protection between radio and accelerometer, and tank curvature drive alongside melty control. [WheelOfPower.ino](https://github.com/SaintSampo/The-Wheel-of-Power/blob/0fed1aa878872777ad0bc79a0350a65bae3e2b1e/WheelOfPower.ino), [driver_station.py](https://github.com/SaintSampo/The-Wheel-of-Power/blob/0fed1aa878872777ad0bc79a0350a65bae3e2b1e/driver_station.py).

13. **Author-reported problems, failures and evidence limits.** Source starts with a LoRa investigation plan: inspect corrupted packets, experiment with CRC and monitor speed before binary transmission. This is planned troubleshooting; a completed error-rate validation is not found in the inspected source. [WheelOfPower.ino](https://github.com/SaintSampo/The-Wheel-of-Power/blob/0fed1aa878872777ad0bc79a0350a65bae3e2b1e/WheelOfPower.ino).

14. **License and reuse notice.** License: not found in inspected repository metadata/material. Reuse terms are unresolved; a public repository alone is not treated as a license. [repository metadata](https://api.github.com/repos/SaintSampo/The-Wheel-of-Power).

<a id="p087"></a>

## P087. teamhappybots/MeltyHalo

1. **Identity, authorship, URLs and visible dates.** Repository owner: teamhappybots. Inspected latest default-branch commit credited to swallenhardware. Repository created 2025-02-02T20:30:48Z (UTC). Inspected commit 8728d60a406723eba0ffa8731a02fe69b4399611 dated 2018-10-06T17:20:10Z (UTC). GitHub identifies parent swallenhardware/MeltyHalo. [repository metadata](https://api.github.com/repos/teamhappybots/MeltyHalo); [inspected commit](https://github.com/teamhappybots/MeltyHalo/commit/8728d60a406723eba0ffa8731a02fe69b4399611).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [Accelerometer.ino](https://github.com/teamhappybots/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/Accelerometer.ino), [haloBot.ino](https://github.com/teamhappybots/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/haloBot.ino), [meltybrain.ino](https://github.com/teamhappybots/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/meltybrain.ino), [README.md](https://github.com/teamhappybots/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/README.md). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: identical, 0 commit(s) ahead and 0 behind at inspection. No fork-specific commits appear in that comparison; no new fork implementation is inferred. [upstream comparison](https://api.github.com/repos/swallenhardware/MeltyHalo/compare/master...teamhappybots:master).

3. **Robot context and reported status.** Reported in inherited README: Halo is a beetleweight battlebot designed by Spencer Allen and Pierce Jensen. A separate robot or competition record for this fork owner: not found. [README.md](https://github.com/teamhappybots/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/README.md).

4. **Hardware and exact parts.** Confirmed in code: Teensy-specific watchdog/i2c_t3 implementation, H3LIS331DL at I2C 0x18, infrared input, two Servo-driven ESC outputs and a five-pixel Adafruit DotStar display. Exact motor/ESC/battery/radio models: not found in the inspected files. [haloBot.ino](https://github.com/teamhappybots/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/haloBot.ino), [Accelerometer.ino](https://github.com/teamhappybots/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/Accelerometer.ino).

5. **Heading sensing and mounting.** Confirmed in code: sensor Z axis is radial to the ring; Y is axial and associated with inversion. Beacon, accelerometer-only and hybrid modes exist; hybrid beacon detections adjust accelerometer trim. Sensor radius and exact IR component/mount dimensions: not found. [Accelerometer.ino](https://github.com/teamhappybots/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/Accelerometer.ino), [meltybrain.ino](https://github.com/teamhappybots/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/meltybrain.ino).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed in code: H3LIS331DL configuration is described as 1 kHz/400 g, sampled every 10000 µs (100 Hz). robotPeriod=726/sqrt((rawZ−225)/522), in microseconds per degree. Two samples support trapezoidal integration and linear extrapolation between measurements. Beacon-only heading uses consecutive edge intervals. A measured achieved control rate: not found. [Accelerometer.ino](https://github.com/teamhappybots/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/Accelerometer.ino), [meltybrain.ino](https://github.com/teamhappybots/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/meltybrain.ino).

7. **Drift and correction.** Confirmed in code: accelTrim separates integrated phase from beacon/manual correction; hybrid correction includes a 40° beacon pickup offset. Accelerometer read failure selects beacon-only sensing. No measured long-term heading error or independent fallback test is supplied. [Accelerometer.ino](https://github.com/teamhappybots/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/Accelerometer.ino), [meltybrain.ino](https://github.com/teamhappybots/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/meltybrain.ino).

8. **Translation timing, phase width and stick mapping.** Confirmed in code: for translation demand above 10, angular difference below 90° selects one 180° half; the selected motor runs at max(throttle−20,0), the other at throttle, swapping opposite the target heading. No translation demand gives equal spin power. A tunable narrow impulse width is not found in this path. [meltybrain.ino](https://github.com/teamhappybots/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/meltybrain.ino).

9. **Heading LED/display.** Reported: POV display while spinning. Code distinguishes static idle/tank animations from angular spin animations on five DotStars; exact display artwork and physical placement are not established here because Animations.ino was not inspected. [README.md](https://github.com/teamhappybots/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/README.md), [haloBot.ino](https://github.com/teamhappybots/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/haloBot.ino).

10. **Calibration and persistence.** Reported in code: calibration constants are robot-specific and link to the author’s accelerometer-calibration article. README still lists finishing manual-trim support as TODO. A complete new calibration procedure for this fork: not found. [Accelerometer.ino](https://github.com/teamhappybots/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/Accelerometer.ino), [README.md](https://github.com/teamhappybots/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/README.md).

11. **Controls, modes, arming and failsafe.** Reported: two-way serial controller, arcade ram-bot mode, spin mode, dead-man control, communication shutdown and watchdog. Code includes idle/tank/spin states and watchdog motor-enable shutdown. These are inherited claims/code paths, not fresh hardware safety tests. [README.md](https://github.com/teamhappybots/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/README.md), [haloBot.ino](https://github.com/teamhappybots/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/haloBot.ino).

12. **Distinctive ideas and implementation.** Distinctive inherited design: an IR absolute index and acceleration-derived phase can compensate for each other’s failures; accelerometer-only operation is selectable. Fork-specific additions are not established by this default branch. [README.md](https://github.com/teamhappybots/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/README.md), [meltybrain.ino](https://github.com/teamhappybots/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/meltybrain.ino).

13. **Author-reported problems, failures and evidence limits.** Author-reported problem handling: unreliable beacon and failed accelerometer are anticipated through fallback paths; manual trim remains unfinished in the README. A separate failure diary or measured fault-injection result for this fork: not found. [README.md](https://github.com/teamhappybots/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/README.md), [Accelerometer.ino](https://github.com/teamhappybots/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/Accelerometer.ino).

14. **License and reuse notice.** GitHub repository metadata identifies MIT. This survey did not audit all dependency or asset licenses. [repository metadata](https://api.github.com/repos/teamhappybots/MeltyHalo).

<a id="p088"></a>

## P088. sicktastic/MeltyHalo

1. **Identity, authorship, URLs and visible dates.** Repository owner: sicktastic. Inspected latest default-branch commit credited to swallenhardware. Repository created 2025-02-02T20:28:46Z (UTC). Inspected commit 8728d60a406723eba0ffa8731a02fe69b4399611 dated 2018-10-06T17:20:10Z (UTC). GitHub identifies parent swallenhardware/MeltyHalo. [repository metadata](https://api.github.com/repos/sicktastic/MeltyHalo); [inspected commit](https://github.com/sicktastic/MeltyHalo/commit/8728d60a406723eba0ffa8731a02fe69b4399611).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [Accelerometer.ino](https://github.com/sicktastic/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/Accelerometer.ino), [haloBot.ino](https://github.com/sicktastic/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/haloBot.ino), [meltybrain.ino](https://github.com/sicktastic/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/meltybrain.ino), [README.md](https://github.com/sicktastic/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/README.md). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: identical, 0 commit(s) ahead and 0 behind at inspection. No fork-specific commits appear in that comparison; no new fork implementation is inferred. [upstream comparison](https://api.github.com/repos/swallenhardware/MeltyHalo/compare/master...sicktastic:master).

3. **Robot context and reported status.** Reported in inherited README: Halo is a beetleweight battlebot designed by Spencer Allen and Pierce Jensen. A separate robot or competition record for this fork owner: not found. [README.md](https://github.com/sicktastic/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/README.md).

4. **Hardware and exact parts.** Confirmed in code: Teensy-specific watchdog/i2c_t3 implementation, H3LIS331DL at I2C 0x18, infrared input, two Servo-driven ESC outputs and a five-pixel Adafruit DotStar display. Exact motor/ESC/battery/radio models: not found in the inspected files. [haloBot.ino](https://github.com/sicktastic/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/haloBot.ino), [Accelerometer.ino](https://github.com/sicktastic/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/Accelerometer.ino).

5. **Heading sensing and mounting.** Confirmed in code: sensor Z axis is radial to the ring; Y is axial and associated with inversion. Beacon, accelerometer-only and hybrid modes exist; hybrid beacon detections adjust accelerometer trim. Sensor radius and exact IR component/mount dimensions: not found. [Accelerometer.ino](https://github.com/sicktastic/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/Accelerometer.ino), [meltybrain.ino](https://github.com/sicktastic/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/meltybrain.ino).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed in code: H3LIS331DL configuration is described as 1 kHz/400 g, sampled every 10000 µs (100 Hz). robotPeriod=726/sqrt((rawZ−225)/522), in microseconds per degree. Two samples support trapezoidal integration and linear extrapolation between measurements. Beacon-only heading uses consecutive edge intervals. A measured achieved control rate: not found. [Accelerometer.ino](https://github.com/sicktastic/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/Accelerometer.ino), [meltybrain.ino](https://github.com/sicktastic/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/meltybrain.ino).

7. **Drift and correction.** Confirmed in code: accelTrim separates integrated phase from beacon/manual correction; hybrid correction includes a 40° beacon pickup offset. Accelerometer read failure selects beacon-only sensing. No measured long-term heading error or independent fallback test is supplied. [Accelerometer.ino](https://github.com/sicktastic/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/Accelerometer.ino), [meltybrain.ino](https://github.com/sicktastic/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/meltybrain.ino).

8. **Translation timing, phase width and stick mapping.** Confirmed in code: for translation demand above 10, angular difference below 90° selects one 180° half; the selected motor runs at max(throttle−20,0), the other at throttle, swapping opposite the target heading. No translation demand gives equal spin power. A tunable narrow impulse width is not found in this path. [meltybrain.ino](https://github.com/sicktastic/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/meltybrain.ino).

9. **Heading LED/display.** Reported: POV display while spinning. Code distinguishes static idle/tank animations from angular spin animations on five DotStars; exact display artwork and physical placement are not established here because Animations.ino was not inspected. [README.md](https://github.com/sicktastic/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/README.md), [haloBot.ino](https://github.com/sicktastic/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/haloBot.ino).

10. **Calibration and persistence.** Reported in code: calibration constants are robot-specific and link to the author’s accelerometer-calibration article. README still lists finishing manual-trim support as TODO. A complete new calibration procedure for this fork: not found. [Accelerometer.ino](https://github.com/sicktastic/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/Accelerometer.ino), [README.md](https://github.com/sicktastic/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/README.md).

11. **Controls, modes, arming and failsafe.** Reported: two-way serial controller, arcade ram-bot mode, spin mode, dead-man control, communication shutdown and watchdog. Code includes idle/tank/spin states and watchdog motor-enable shutdown. These are inherited claims/code paths, not fresh hardware safety tests. [README.md](https://github.com/sicktastic/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/README.md), [haloBot.ino](https://github.com/sicktastic/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/haloBot.ino).

12. **Distinctive ideas and implementation.** Distinctive inherited design: an IR absolute index and acceleration-derived phase can compensate for each other’s failures; accelerometer-only operation is selectable. Fork-specific additions are not established by this default branch. [README.md](https://github.com/sicktastic/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/README.md), [meltybrain.ino](https://github.com/sicktastic/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/meltybrain.ino).

13. **Author-reported problems, failures and evidence limits.** Author-reported problem handling: unreliable beacon and failed accelerometer are anticipated through fallback paths; manual trim remains unfinished in the README. A separate failure diary or measured fault-injection result for this fork: not found. [README.md](https://github.com/sicktastic/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/README.md), [Accelerometer.ino](https://github.com/sicktastic/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/Accelerometer.ino).

14. **License and reuse notice.** GitHub repository metadata identifies MIT. This survey did not audit all dependency or asset licenses. [repository metadata](https://api.github.com/repos/sicktastic/MeltyHalo).

<a id="p089"></a>

## P089. nurdism/MeltyHalo

1. **Identity, authorship, URLs and visible dates.** Repository owner: nurdism. Inspected latest default-branch commit credited to swallenhardware. Repository created 2025-09-24T06:45:08Z (UTC). Inspected commit 8728d60a406723eba0ffa8731a02fe69b4399611 dated 2018-10-06T17:20:10Z (UTC). GitHub identifies parent swallenhardware/MeltyHalo. [repository metadata](https://api.github.com/repos/nurdism/MeltyHalo); [inspected commit](https://github.com/nurdism/MeltyHalo/commit/8728d60a406723eba0ffa8731a02fe69b4399611).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [Accelerometer.ino](https://github.com/nurdism/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/Accelerometer.ino), [haloBot.ino](https://github.com/nurdism/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/haloBot.ino), [meltybrain.ino](https://github.com/nurdism/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/meltybrain.ino), [README.md](https://github.com/nurdism/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/README.md). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: identical, 0 commit(s) ahead and 0 behind at inspection. No fork-specific commits appear in that comparison; no new fork implementation is inferred. [upstream comparison](https://api.github.com/repos/swallenhardware/MeltyHalo/compare/master...nurdism:master).

3. **Robot context and reported status.** Reported in inherited README: Halo is a beetleweight battlebot designed by Spencer Allen and Pierce Jensen. A separate robot or competition record for this fork owner: not found. [README.md](https://github.com/nurdism/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/README.md).

4. **Hardware and exact parts.** Confirmed in code: Teensy-specific watchdog/i2c_t3 implementation, H3LIS331DL at I2C 0x18, infrared input, two Servo-driven ESC outputs and a five-pixel Adafruit DotStar display. Exact motor/ESC/battery/radio models: not found in the inspected files. [haloBot.ino](https://github.com/nurdism/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/haloBot.ino), [Accelerometer.ino](https://github.com/nurdism/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/Accelerometer.ino).

5. **Heading sensing and mounting.** Confirmed in code: sensor Z axis is radial to the ring; Y is axial and associated with inversion. Beacon, accelerometer-only and hybrid modes exist; hybrid beacon detections adjust accelerometer trim. Sensor radius and exact IR component/mount dimensions: not found. [Accelerometer.ino](https://github.com/nurdism/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/Accelerometer.ino), [meltybrain.ino](https://github.com/nurdism/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/meltybrain.ino).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed in code: H3LIS331DL configuration is described as 1 kHz/400 g, sampled every 10000 µs (100 Hz). robotPeriod=726/sqrt((rawZ−225)/522), in microseconds per degree. Two samples support trapezoidal integration and linear extrapolation between measurements. Beacon-only heading uses consecutive edge intervals. A measured achieved control rate: not found. [Accelerometer.ino](https://github.com/nurdism/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/Accelerometer.ino), [meltybrain.ino](https://github.com/nurdism/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/meltybrain.ino).

7. **Drift and correction.** Confirmed in code: accelTrim separates integrated phase from beacon/manual correction; hybrid correction includes a 40° beacon pickup offset. Accelerometer read failure selects beacon-only sensing. No measured long-term heading error or independent fallback test is supplied. [Accelerometer.ino](https://github.com/nurdism/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/Accelerometer.ino), [meltybrain.ino](https://github.com/nurdism/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/meltybrain.ino).

8. **Translation timing, phase width and stick mapping.** Confirmed in code: for translation demand above 10, angular difference below 90° selects one 180° half; the selected motor runs at max(throttle−20,0), the other at throttle, swapping opposite the target heading. No translation demand gives equal spin power. A tunable narrow impulse width is not found in this path. [meltybrain.ino](https://github.com/nurdism/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/meltybrain.ino).

9. **Heading LED/display.** Reported: POV display while spinning. Code distinguishes static idle/tank animations from angular spin animations on five DotStars; exact display artwork and physical placement are not established here because Animations.ino was not inspected. [README.md](https://github.com/nurdism/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/README.md), [haloBot.ino](https://github.com/nurdism/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/haloBot.ino).

10. **Calibration and persistence.** Reported in code: calibration constants are robot-specific and link to the author’s accelerometer-calibration article. README still lists finishing manual-trim support as TODO. A complete new calibration procedure for this fork: not found. [Accelerometer.ino](https://github.com/nurdism/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/Accelerometer.ino), [README.md](https://github.com/nurdism/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/README.md).

11. **Controls, modes, arming and failsafe.** Reported: two-way serial controller, arcade ram-bot mode, spin mode, dead-man control, communication shutdown and watchdog. Code includes idle/tank/spin states and watchdog motor-enable shutdown. These are inherited claims/code paths, not fresh hardware safety tests. [README.md](https://github.com/nurdism/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/README.md), [haloBot.ino](https://github.com/nurdism/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/haloBot.ino).

12. **Distinctive ideas and implementation.** Distinctive inherited design: an IR absolute index and acceleration-derived phase can compensate for each other’s failures; accelerometer-only operation is selectable. Fork-specific additions are not established by this default branch. [README.md](https://github.com/nurdism/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/README.md), [meltybrain.ino](https://github.com/nurdism/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/meltybrain.ino).

13. **Author-reported problems, failures and evidence limits.** Author-reported problem handling: unreliable beacon and failed accelerometer are anticipated through fallback paths; manual trim remains unfinished in the README. A separate failure diary or measured fault-injection result for this fork: not found. [README.md](https://github.com/nurdism/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/README.md), [Accelerometer.ino](https://github.com/nurdism/MeltyHalo/blob/8728d60a406723eba0ffa8731a02fe69b4399611/Accelerometer.ino).

14. **License and reuse notice.** GitHub repository metadata identifies MIT. This survey did not audit all dependency or asset licenses. [repository metadata](https://api.github.com/repos/nurdism/MeltyHalo).

<a id="p090"></a>

## P090. martinkuberski/MeltyHalo

1. **Identity, authorship, URLs and visible dates.** Repository owner: martinkuberski. Inspected latest default-branch commit credited to Martin Kuberski. Repository created 2022-02-23T18:11:24Z (UTC). Inspected commit 6cdd7dcc49dad5cd8f068c26315169ed713aa936 dated 2022-02-25T23:39:06Z (UTC). GitHub identifies parent swallenhardware/MeltyHalo. [repository metadata](https://api.github.com/repos/martinkuberski/MeltyHalo); [inspected commit](https://github.com/martinkuberski/MeltyHalo/commit/6cdd7dcc49dad5cd8f068c26315169ed713aa936).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [haloBot/Accelerometer.ino](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/haloBot/Accelerometer.ino), [haloBot/Comms.ino](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/haloBot/Comms.ino), [haloBot/haloBot.ino](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/haloBot/haloBot.ino), [haloBot/meltybrain.ino](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/haloBot/meltybrain.ino), [haloBotBlind/meltybrain.ino](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/haloBotBlind/meltybrain.ino), [README.md](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/README.md). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: ahead, 9 commit(s) ahead and 0 behind at inspection. Changed-file scope includes `Comms.ino`, `README.md`, `haloBot/Accelerometer.ino`, `haloBot/Animations.ino`, `haloBot/Comms.ino`, `haloBot/haloBot.ino`, `haloBot/meltybrain.ino`, `haloBotBlind/Accelerometer.ino`, `haloBotBlind/Animations.ino`, `haloBotBlind/Comms.ino`, `haloBotBlind/haloBotBlind.ino`, `haloBotBlind/meltybrain.ino` and additional files. Detailed findings below describe the inspected subset; the entire changed tree was not audited. [upstream comparison](https://api.github.com/repos/swallenhardware/MeltyHalo/compare/master...martinkuberski:master).

3. **Robot context and reported status.** Reported name: MeltyBrian, an accelerometer-only MeltyHalo implementation. README retains the original Halo beetleweight description; a separate verified MeltyBrian weight/event result is not found. [README.md](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/README.md).

4. **Hardware and exact parts.** Reported: Teensy 3.2, Flysky FS-I6 transmitter and FS-iA6B receiver. Confirmed code uses PulsePositionInput, Servo ESC outputs and five DotStars; accelerometer register code identifies H3LIS331DL. Motor/ESC/battery models: not found. [README.md](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/README.md), [haloBot/haloBot.ino](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/haloBot/haloBot.ino), [haloBot/Accelerometer.ino](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/haloBot/Accelerometer.ino).

5. **Heading sensing and mounting.** Confirmed: haloBot sets ACCEL_SENSING and uses the inherited radial-Z/axial-Y sensor arrangement. Separate haloBotBlind comments out sensor/beacon heading and synthesizes angle from elapsed time modulo a configured period. Radius/mount measurements for either variant: not found. [haloBot/haloBot.ino](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/haloBot/haloBot.ino), [haloBot/Accelerometer.ino](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/haloBot/Accelerometer.ino), [haloBotBlind/meltybrain.ino](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/haloBotBlind/meltybrain.ino).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed in haloBot: inherited 100 Hz reads, period=726/sqrt((rawZ−225)/522), two-sample integration and extrapolation. Blind version computes angle=map(((micros−freqSetTime)/1000)%freq,0,freq,0,360). This is programmed timing, not sensor-measured RPM. Measured rates/accuracy: not found. [haloBot/Accelerometer.ino](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/haloBot/Accelerometer.ino), [haloBotBlind/meltybrain.ino](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/haloBotBlind/meltybrain.ino).

7. **Drift and correction.** Confirmed: haloBot retains accelTrim and manual head offset; the blind version comments out both sensor trim and manual angle correction in the inspected meltybrain tab. A verified drift-compensation result for either: not found. [haloBot/meltybrain.ino](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/haloBot/meltybrain.ino), [haloBotBlind/meltybrain.ino](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/haloBotBlind/meltybrain.ino).

8. **Translation timing, phase width and stick mapping.** Confirmed: two opposing 180° sectors alternate which motor receives throttle−20; thumbstick magnitude must exceed 10. The blind tab retains that motor modulation but drives it from synthetic phase. Comms maps joystick PWM values and uses atan2 to derive target direction. [haloBot/Comms.ino](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/haloBot/Comms.ino), [haloBot/meltybrain.ino](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/haloBot/meltybrain.ino), [haloBotBlind/meltybrain.ino](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/haloBotBlind/meltybrain.ino).

9. **Heading LED/display.** Confirmed: five-pixel DotStar animations remain; haloBot chooses static idle/tank and dynamic spin animation. Exact physical LED position, brightness and tested angular artwork: not found. [haloBot/haloBot.ino](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/haloBot/haloBot.ino).

10. **Calibration and persistence.** Reported: README tells users to remove incompatible Adafruit_BusIO headers except Adafruit_SPIDevice files. Inherited accelerometer calibration constants remain. A new measured calibration or completed trim procedure: not found. [README.md](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/README.md), [haloBot/Accelerometer.ino](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/haloBot/Accelerometer.ino).

11. **Controls, modes, arming and failsafe.** Confirmed: PPM input begins on pin 5, receiver values are mapped into controls, and a particular repeated FS-I6 failsafe pattern triggers idle after ten matches. Hardware watchdog ISR drives motor enable high. Untested static concern: Comms sets en=1 while haloBot state transitions test en==0xAA; successful state transitions are therefore not established by this inspection. [haloBot/Comms.ino](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/haloBot/Comms.ino), [haloBot/haloBot.ino](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/haloBot/haloBot.ino).

12. **Distinctive ideas and implementation.** Inspected fork additions include the Flysky/PPM input path and a separate sensorless blind experiment. The blind control is explicitly identifiable as fake-angle timing; it is not presented here as a working absolute-heading solution. [README.md](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/README.md), [haloBot/Comms.ino](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/haloBot/Comms.ino), [haloBotBlind/meltybrain.ino](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/haloBotBlind/meltybrain.ino).

13. **Author-reported problems, failures and evidence limits.** Author-reported integration problem: Adafruit_BusIO headers conflict with the chosen I2C setup. A hardware failure/test diary is not found. The en mismatch above is a static source observation by this survey, not an author-reported failure. [README.md](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/README.md), [haloBot/Comms.ino](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/haloBot/Comms.ino), [haloBot/haloBot.ino](https://github.com/martinkuberski/MeltyHalo/blob/6cdd7dcc49dad5cd8f068c26315169ed713aa936/haloBot/haloBot.ino).

14. **License and reuse notice.** GitHub repository metadata identifies MIT. This survey did not audit all dependency or asset licenses. [repository metadata](https://api.github.com/repos/martinkuberski/MeltyHalo).

<a id="p091"></a>

## P091. Ryan-WHOOP-26982E/PotatoMelt_Stig

1. **Identity, authorship, URLs and visible dates.** Repository owner: Ryan-WHOOP-26982E. Inspected latest default-branch commit credited to Danielle Skysdottir. Repository created 2026-02-27T17:04:40Z (UTC). Inspected commit 71cd20fc82610c7a3dd203e88907d089d40dcd2d dated 2024-05-17T00:25:02Z (UTC). GitHub identifies parent skysdottir/PotatoMelt. [repository metadata](https://api.github.com/repos/Ryan-WHOOP-26982E/PotatoMelt_Stig); [inspected commit](https://github.com/Ryan-WHOOP-26982E/PotatoMelt_Stig/commit/71cd20fc82610c7a3dd203e88907d089d40dcd2d).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [potatomelt/accel_handler.cpp](https://github.com/Ryan-WHOOP-26982E/PotatoMelt_Stig/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/accel_handler.cpp), [potatomelt/spin_control.cpp](https://github.com/Ryan-WHOOP-26982E/PotatoMelt_Stig/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/spin_control.cpp), [potatomelt/melty_config.h](https://github.com/Ryan-WHOOP-26982E/PotatoMelt_Stig/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/melty_config.h), [potatomelt/rc_handler.cpp](https://github.com/Ryan-WHOOP-26982E/PotatoMelt_Stig/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/rc_handler.cpp), [README.md](https://github.com/Ryan-WHOOP-26982E/PotatoMelt_Stig/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/README.md). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: identical, 0 commit(s) ahead and 0 behind at inspection. No fork-specific commits appear in that comparison; no new fork implementation is inferred. [upstream comparison](https://api.github.com/repos/skysdottir/PotatoMelt/compare/main...Ryan-WHOOP-26982E:main).

3. **Robot context and reported status.** Reported: PotatoMelt-derived translational-drift controller. The inherited README describes development hardware, not a verified robot built by this fork owner. Weight, wheel geometry and event results for this fork: not found. [README.md](https://github.com/Ryan-WHOOP-26982E/PotatoMelt_Stig/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/README.md).

4. **Hardware and exact parts.** Reported development parts: Adafruit ItsyBitsy 32u4, 16 MHz/5 V; Adafruit LIS331 I2C board; generic iBus receiver; Repeat Robotics dual AM32 ESC. Exact motors, battery and receiver model: not found. [README.md](https://github.com/Ryan-WHOOP-26982E/PotatoMelt_Stig/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/README.md).

5. **Heading sensing and mounting.** Confirmed in code: radial sensing uses LIS331 Y-axis force converted to g. Default effective radius is 2.91 cm; actual measured mounting geometry is not supplied. Heading is a relative phase estimated from rotational speed. [potatomelt/accel_handler.cpp](https://github.com/Ryan-WHOOP-26982E/PotatoMelt_Stig/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/accel_handler.cpp), [potatomelt/melty_config.h](https://github.com/Ryan-WHOOP-26982E/PotatoMelt_Stig/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/melty_config.h).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed in code: get_uncorrected_rpm computes sqrt(abs(g−zero)×89445/radius_cm). A table of eight RPM/correction pairs supports linear interpolation. spin_control converts corrected/steered RPM to a revolution interval; Timer3 compare ISR is configured at 2 kHz, while spin_one_iteration updates parameters then delays 20 ms. PID uses a 20 ms sample interval. A measured achieved rate or noise spectrum: not found. [potatomelt/accel_handler.cpp](https://github.com/Ryan-WHOOP-26982E/PotatoMelt_Stig/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/accel_handler.cpp), [potatomelt/spin_control.cpp](https://github.com/Ryan-WHOOP-26982E/PotatoMelt_Stig/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/spin_control.cpp).

7. **Drift and correction.** Confirmed in code and described in README: driver steering changes the estimated rotation interval; an RPM-dependent correction table is tuned until the beacon stops precessing. PID input remains uncorrected RPM in this snapshot, explicitly to avoid calibration bugs changing spin control. Residual drift measurements: not found. [potatomelt/spin_control.cpp](https://github.com/Ryan-WHOOP-26982E/PotatoMelt_Stig/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/spin_control.cpp), [README.md](https://github.com/Ryan-WHOOP-26982E/PotatoMelt_Stig/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/README.md).

8. **Translation timing, phase width and stick mapping.** Confirmed in code: forward/back translation exchanges high/low DShot commands over opposing 180° half rotations. Offset scales with signed forward/back stick displacement, base throttle and translation trim, with limits before DShot conversion. Left/right input steers the relative heading; omnidirectional translation is not implemented in this inspected path. [potatomelt/spin_control.cpp](https://github.com/Ryan-WHOOP-26982E/PotatoMelt_Stig/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/spin_control.cpp).

9. **Heading LED/display.** Confirmed in code: LED start/stop wrap around a calibrated percentage offset; width follows raw RPM/MAX_TARGET_RPM, clamped to 10–90% of a revolution. README describes fast idle blink, double config blink and precession-based adjustment. Physical beacon mounting and brightness: not found. [potatomelt/spin_control.cpp](https://github.com/Ryan-WHOOP-26982E/PotatoMelt_Stig/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/spin_control.cpp), [README.md](https://github.com/Ryan-WHOOP-26982E/PotatoMelt_Stig/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/README.md).

10. **Calibration and persistence.** Reported procedure: at rest hold the right stick backward for 1 s; entering config snapshots zero g. At eight stable speeds adjust until beacon precession stops, then toggle channel 6 to save points. Backward stick with rotation adjusts beacon offset; exit while stopped. EEPROM support is enabled. Independent successful calibration evidence: not found. [README.md](https://github.com/Ryan-WHOOP-26982E/PotatoMelt_Stig/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/README.md), [potatomelt/melty_config.h](https://github.com/Ryan-WHOOP-26982E/PotatoMelt_Stig/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/melty_config.h).

11. **Controls, modes, arming and failsafe.** Confirmed in code: iBus channel handling, tank mode, spin direction and translation-trim inputs. Config enables a 2 s watchdog, battery warning/critical-halt features, and a 3 s control-motion timeout. These are configured safeguards; a complete end-to-end failsafe test is not supplied. [potatomelt/rc_handler.cpp](https://github.com/Ryan-WHOOP-26982E/PotatoMelt_Stig/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/rc_handler.cpp), [potatomelt/melty_config.h](https://github.com/Ryan-WHOOP-26982E/PotatoMelt_Stig/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/melty_config.h).

12. **Distinctive ideas and implementation.** Distinctive inherited implementation: eight-point speed correction, separate raw-RPM speed PID and corrected phase estimate, and interrupt-driven DShot updates. No fork-owner-specific experiment or new control feature is established by the inspected default branch. [potatomelt/accel_handler.cpp](https://github.com/Ryan-WHOOP-26982E/PotatoMelt_Stig/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/accel_handler.cpp), [potatomelt/spin_control.cpp](https://github.com/Ryan-WHOOP-26982E/PotatoMelt_Stig/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/spin_control.cpp).

13. **Author-reported problems, failures and evidence limits.** Reported limitations: README calls this an early Arduino project and provides no fitness guarantee. Code comments explicitly distrust the correction-factor code enough to keep it out of the speed PID. A fork-owner-specific failure log or quantified test result: not found. [README.md](https://github.com/Ryan-WHOOP-26982E/PotatoMelt_Stig/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/README.md), [potatomelt/spin_control.cpp](https://github.com/Ryan-WHOOP-26982E/PotatoMelt_Stig/blob/71cd20fc82610c7a3dd203e88907d089d40dcd2d/potatomelt/spin_control.cpp).

14. **License and reuse notice.** GitHub repository metadata identifies LGPL-2.1. This survey did not audit all dependency or asset licenses. [repository metadata](https://api.github.com/repos/Ryan-WHOOP-26982E/PotatoMelt_Stig).

<a id="p092"></a>

## P092. Ryan-WHOOP-26982E/stigpotatomelt-esp32

1. **Identity, authorship, URLs and visible dates.** Repository owner: Ryan-WHOOP-26982E. Inspected latest default-branch commit credited to Ryan-WHOOP-26982E. Repository created 2026-03-31T00:52:19Z (UTC). Inspected commit 4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5 dated 2026-04-11T02:08:25Z (UTC). GitHub identifies parent skysdottir/potatomelt-esp32. [repository metadata](https://api.github.com/repos/Ryan-WHOOP-26982E/stigpotatomelt-esp32); [inspected commit](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/commit/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [potatomelt/src/subsystems/imu.cpp](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/subsystems/imu.cpp), [potatomelt/potatomelt.ino](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/potatomelt.ino), [potatomelt/src/robot.cpp](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/robot.cpp), [potatomelt/src/melty_config.h](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/melty_config.h), [potatomelt/src/controller.cpp](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/controller.cpp), [README.md](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/README.md), [potatomelt/src/subsystems/accelerometer.cpp](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/subsystems/accelerometer.cpp). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: ahead, 10 commit(s) ahead and 0 behind at inspection. Changed-file scope includes `potatomelt/examples-temp/accel_test/SparkFun_LIS331_ESP32.cpp`, `potatomelt/examples-temp/accel_test/SparkFun_LIS331_ESP32.h`, `potatomelt/examples-temp/accel_test/accel_test.ino`, `potatomelt/potatomelt.ino`, `potatomelt/src/controller.cpp`, `potatomelt/src/controller.h`, `potatomelt/src/lib/SbusReader.cpp`, `potatomelt/src/lib/SbusReader.h`, `potatomelt/src/lib/SparkFun_LIS331_ESP32.cpp`, `potatomelt/src/melty_config.h`, `potatomelt/src/robot.cpp`, `potatomelt/src/robot.h` and additional files. Detailed findings below describe the inspected subset; the entire changed tree was not audited. [upstream comparison](https://api.github.com/repos/skysdottir/potatomelt-esp32/compare/main...Ryan-WHOOP-26982E:main).

3. **Robot context and reported status.** Reported: ESP32 PotatoMelt-derived meltybrain controller. The inherited README describes ESP32-S3 use. Exact chassis, measured weight, wheels and event results for this fork: not found. [README.md](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/README.md).

4. **Hardware and exact parts.** Confirmed in source: XIAO ESP32-S3 pin labels, Serial1 SBUS input on D7/D6, one installed LIS331-family accelerometer at 0x19, DShot600 outputs GPIO9/8, two discrete LED outputs GPIO2/3 and 3S battery configuration. Exact motor/ESC/receiver model: not found. [potatomelt/src/melty_config.h](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/melty_config.h), [potatomelt/src/robot.cpp](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/robot.cpp), [potatomelt/src/subsystems/imu.cpp](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/subsystems/imu.cpp).

5. **Heading sensing and mounting.** Confirmed: get_xy_accel actually uses abs(Zg−resting_Z) because the sensor is mounted vertically; radius default 2.738 cm. Source explicitly removes the second sensor as not installed. This contradicts the unchanged README’s generic description and is the inspected implementation. [potatomelt/src/subsystems/accelerometer.cpp](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/subsystems/accelerometer.cpp), [potatomelt/src/subsystems/imu.cpp](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/subsystems/imu.cpp), [potatomelt/src/melty_config.h](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/melty_config.h).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed: LIS331 ODR is set to 400 Hz; raw radial g is EMA-filtered with alpha=0.1 before RPM=sqrt(abs(filtered_g)×89445/2.738)×correction. Tracking interval is 60,000,000/steered_RPM µs; a separate core-0 task updates motors/LEDs with tick yields. The comment’s approximate 35 ms EMA time constant assumes a 4 ms caller rate and is not a measurement here. [potatomelt/src/subsystems/accelerometer.cpp](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/subsystems/accelerometer.cpp), [potatomelt/src/subsystems/imu.cpp](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/subsystems/imu.cpp), [potatomelt/potatomelt.ino](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/potatomelt.ino).

7. **Drift and correction.** Confirmed: per-target-RPM correction factors are persisted; trim multiplies by 1.005 or its reciprocal. Steering scales the period estimate independently of speed PID. Residual drift measurements and external absolute-heading correction: not found. [potatomelt/src/subsystems/imu.cpp](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/subsystems/imu.cpp), [potatomelt/potatomelt.ino](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/potatomelt.ino).

8. **Translation timing, phase width and stick mapping.** Confirmed: Robot::spin uses phase p within each half turn; parabolic modulation −4p(p−1) scales a maximum differential from forward/back stick×base throttle×translation trim. Opposing 180° halves exchange motor roles. The left/right translation channel is reserved/unused in the inspected calculation. [potatomelt/src/robot.cpp](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/robot.cpp), [potatomelt/potatomelt.ino](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/potatomelt.ino), [potatomelt/src/controller.cpp](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/controller.cpp).

9. **Heading LED/display.** Confirmed: centered/wrapped heading arc width follows estimated RPM/MAX_TRACKING_RPM clamped 10–90%; on-arc displays a battery color gradient. Exact LED hardware and mounting are not established beyond source pin settings. [potatomelt/src/robot.cpp](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/robot.cpp), [potatomelt/potatomelt.ino](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/potatomelt.ino), [potatomelt/src/melty_config.h](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/melty_config.h).

10. **Calibration and persistence.** Confirmed: startup takes 60 offset samples; SBUS switches provide correction trim and translation-trim steps, while target RPM list is {2100,3200}. Per-target correction persists. An actual calibration log or achieved RPM is not found. [potatomelt/src/subsystems/imu.cpp](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/subsystems/imu.cpp), [potatomelt/src/controller.cpp](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/controller.cpp).

11. **Controls, modes, arming and failsafe.** Confirmed: SBUS lost-frame/failsafe flags mark controller disconnected/dead; no-frame timeout is 3 s. Spin/reverse/RPM/trim are mapped to SBUS channels; reverse is applied through signed DShot ranges in Robot::spin. Main loop still labels low-battery state TODO. These source safeguards were not hardware-tested by this survey. [potatomelt/src/controller.cpp](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/controller.cpp), [potatomelt/src/robot.cpp](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/robot.cpp), [potatomelt/potatomelt.ino](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/potatomelt.ino).

12. **Distinctive ideas and implementation.** Inspected distinctive additions: SBUS replaces Bluetooth input; single vertically mounted accelerometer, EMA, DShot600, persistent spin summaries and UDP/WiFi telemetry. Source warns WiFi shares core 0 with motor timing and says disable it for arena runs. Test results validating concurrent telemetry timing: not found. [potatomelt/src/controller.cpp](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/controller.cpp), [potatomelt/src/subsystems/imu.cpp](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/subsystems/imu.cpp), [potatomelt/src/robot.cpp](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/robot.cpp), [potatomelt/potatomelt.ino](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/potatomelt.ino).

13. **Author-reported problems, failures and evidence limits.** Author notes in source: absent second sensor caused I2C timeout latency, low tank scaling was below ESC threshold, default 50 Hz accelerometer ODR was too slow, and library Wire.begin resets bus clock/timeout. Source changes address those causes; reproduced measurements demonstrating fixes: not found. [potatomelt/src/subsystems/imu.cpp](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/subsystems/imu.cpp), [potatomelt/src/subsystems/accelerometer.cpp](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/subsystems/accelerometer.cpp), [potatomelt/src/melty_config.h](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/src/melty_config.h), [potatomelt/potatomelt.ino](https://github.com/Ryan-WHOOP-26982E/stigpotatomelt-esp32/blob/4e189b694fa924a7a6642e1f10d1e37cbfb4c7d5/potatomelt/potatomelt.ino).

14. **License and reuse notice.** GitHub repository metadata identifies LGPL-2.1. This survey did not audit all dependency or asset licenses. [repository metadata](https://api.github.com/repos/Ryan-WHOOP-26982E/stigpotatomelt-esp32).

<a id="p093"></a>

## P093. TGower/potatomelt-esp32

1. **Identity, authorship, URLs and visible dates.** Repository owner: TGower. Inspected latest default-branch commit credited to Trevor Gower. Repository created 2025-01-29T05:18:48Z (UTC). Inspected commit 7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8 dated 2025-03-21T02:39:38Z (UTC). GitHub identifies parent skysdottir/potatomelt-esp32. [repository metadata](https://api.github.com/repos/TGower/potatomelt-esp32); [inspected commit](https://github.com/TGower/potatomelt-esp32/commit/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [potatomelt/src/subsystems/imu.cpp](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/src/subsystems/imu.cpp), [potatomelt/potatomelt.ino](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/potatomelt.ino), [potatomelt/src/subsystems/accelerometer.cpp](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/src/subsystems/accelerometer.cpp), [potatomelt/src/robot.cpp](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/src/robot.cpp), [potatomelt/src/melty_config.h](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/src/melty_config.h), [potatomelt/src/controller.cpp](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/src/controller.cpp), [README.md](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/README.md). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: diverged, 2 commit(s) ahead and 2 behind at inspection. Changed-file scope includes `potatomelt/potatomelt.ino`, `potatomelt/src/controller.cpp`, `potatomelt/src/melty_config.h`. Detailed findings below describe the inspected subset; the entire changed tree was not audited. [upstream comparison](https://api.github.com/repos/skysdottir/potatomelt-esp32/compare/main...TGower:main).

3. **Robot context and reported status.** Reported: ESP32 PotatoMelt-derived meltybrain controller. The inherited README describes ESP32-S3 use. Exact chassis, measured weight, wheels and event results for this fork: not found. [README.md](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/README.md).

4. **Hardware and exact parts.** Confirmed: two LIS331-family sensors at 0x18/0x19, Bluetooth Xbox controller via Bluepad32 with a permitted MAC address, DShot300 motors GPIO6/7, NeoPixel GPIO17 and 6S battery setting. ESP32-S3 is the inherited README platform; exact physical board, motors and ESC model: not found. [potatomelt/src/controller.cpp](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/src/controller.cpp), [potatomelt/src/subsystems/imu.cpp](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/src/subsystems/imu.cpp), [potatomelt/src/robot.cpp](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/src/robot.cpp), [potatomelt/src/melty_config.h](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/src/melty_config.h), [README.md](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/README.md).

5. **Heading sensing and mounting.** Confirmed: average of both sensors’ offset-corrected X/Y magnitudes estimates radial g, using configured 5.00 cm radius. Sensor Z averages feed inversion detection, but code says inversion integration into tank control is TODO. Exact physical placement of the two dies: not found. [potatomelt/src/subsystems/imu.cpp](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/src/subsystems/imu.cpp), [potatomelt/src/subsystems/accelerometer.cpp](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/src/subsystems/accelerometer.cpp), [potatomelt/src/melty_config.h](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/src/melty_config.h).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed: IMU::get_rpm uses sqrt(abs(g)×89445/radius_cm) times a stored correction factor. calculate_melty_params clamps tracking to at least 400 RPM then converts to 60,000,000/RPM µs. Parameters and a separate core-0 motor/LED hot loop are split across FreeRTOS tasks. vTaskDelay(1) is a tick delay, not proof of an exact 1 kHz measured rate. [potatomelt/src/subsystems/imu.cpp](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/src/subsystems/imu.cpp), [potatomelt/potatomelt.ino](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/potatomelt.ino).

7. **Drift and correction.** Confirmed: per-target-RPM correction factors are persisted; trim multiplies by 1.005 or its reciprocal. Steering scales the period estimate independently of speed PID. Residual drift measurements and external absolute-heading correction: not found. [potatomelt/src/subsystems/imu.cpp](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/src/subsystems/imu.cpp), [potatomelt/potatomelt.ino](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/potatomelt.ino).

8. **Translation timing, phase width and stick mapping.** Confirmed: Robot::spin uses phase p within each half turn; parabolic modulation −4p(p−1) scales a maximum differential from forward/back stick×base throttle×translation trim. Opposing 180° halves exchange motor roles. The left/right translation channel is reserved/unused in the inspected calculation. [potatomelt/src/robot.cpp](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/src/robot.cpp), [potatomelt/potatomelt.ino](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/potatomelt.ino), [potatomelt/src/controller.cpp](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/src/controller.cpp).

9. **Heading LED/display.** Confirmed: centered/wrapped heading arc width follows estimated RPM/MAX_TRACKING_RPM clamped 10–90%; on-arc displays a battery color gradient. Exact LED hardware and mounting are not established beyond source pin settings. [potatomelt/src/robot.cpp](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/src/robot.cpp), [potatomelt/potatomelt.ino](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/potatomelt.ino), [potatomelt/src/melty_config.h](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/src/melty_config.h).

10. **Calibration and persistence.** Confirmed: startup samples accelerometer offsets at rest; live trim adjusts a persistent correction per target RPM. The inherited README describes D-pad spin and translation calibration, but the actual radio mapping differs by snapshot below. A calibration experiment log: not found. [potatomelt/src/subsystems/imu.cpp](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/src/subsystems/imu.cpp), [potatomelt/src/controller.cpp](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/src/controller.cpp), [README.md](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/README.md).

11. **Controls, modes, arming and failsafe.** Confirmed: Bluetooth disconnect/stale states stop both motors; 3 s update timeout; right trigger requests spin, right stick translates/steers, left vertical stick steps RPM targets, X toggles reverse state and D-pad adjusts trims. Binding is MAC-restricted. Main loop contains low-battery-state TODO; runtime reverse-state effectiveness was not fully traced in this snapshot. [potatomelt/src/controller.cpp](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/src/controller.cpp), [potatomelt/src/robot.cpp](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/src/robot.cpp), [potatomelt/potatomelt.ino](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/potatomelt.ino).

12. **Distinctive ideas and implementation.** Distinctive implementation: phase-sensitive motor/LED task is separated from radio, sensor and speed-PID calculations, with persistent RPM-specific corrections and smooth parabolic translation. Snapshot-specific changes are recorded in field 2. [potatomelt/src/robot.cpp](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/src/robot.cpp), [potatomelt/src/subsystems/imu.cpp](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/src/subsystems/imu.cpp), [potatomelt/potatomelt.ino](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/potatomelt.ino).

13. **Author-reported problems, failures and evidence limits.** Source reports a Bluepad32 scan timeout/crash workaround: disable new Bluetooth connections after an authorized controller connects, reenable on disconnect. It also notes warmup anomalies and pending inversion integration. Target lists include up to 9000 RPM; these are configured targets, not achieved test results. [potatomelt/src/controller.cpp](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/src/controller.cpp), [potatomelt/src/subsystems/imu.cpp](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/src/subsystems/imu.cpp), [potatomelt/src/melty_config.h](https://github.com/TGower/potatomelt-esp32/blob/7379a3fb7a93037f382e0c2a79f36a6fd9ea11d8/potatomelt/src/melty_config.h).

14. **License and reuse notice.** GitHub repository metadata identifies LGPL-2.1. This survey did not audit all dependency or asset licenses. [repository metadata](https://api.github.com/repos/TGower/potatomelt-esp32).

<a id="p094"></a>

## P094. shrine-priestess/LoserMelt

1. **Identity, authorship, URLs and visible dates.** Repository owner: shrine-priestess. Inspected latest default-branch commit credited to Kezia Skye. Repository created 2026-02-21T19:22:00Z (UTC). Inspected commit f3c07adc9f4a95813c3c411b9b3313a584644c7d dated 2026-03-20T12:39:35Z (UTC). GitHub identifies parent skysdottir/PotatoMelt. [repository metadata](https://api.github.com/repos/shrine-priestess/LoserMelt); [inspected commit](https://github.com/shrine-priestess/LoserMelt/commit/f3c07adc9f4a95813c3c411b9b3313a584644c7d).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [losermelt/led_driver.cpp](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/losermelt/led_driver.cpp), [losermelt/accel_handler.cpp](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/losermelt/accel_handler.cpp), [losermelt/spin_control.cpp](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/losermelt/spin_control.cpp), [losermelt/melty_config.h](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/losermelt/melty_config.h), [losermelt/rc_handler.cpp](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/losermelt/rc_handler.cpp), [README.md](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/README.md). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: ahead, 7 commit(s) ahead and 0 behind at inspection. Changed-file scope includes `README.md`, `lib/DShot-Arduino-master.zip`, `lib/SparkFun_LIS331_Arduino_Library.zip`, `losermelt/PotatoMelt.code-workspace`, `losermelt/SparkFun_LIS331.cpp`, `losermelt/SparkFun_LIS331.h`, `losermelt/accel_handler.cpp`, `losermelt/accel_handler.h`, `losermelt/config_storage.cpp`, `losermelt/config_storage.h`, `losermelt/led_driver.cpp`, `losermelt/led_driver.h` and additional files. Detailed findings below describe the inspected subset; the entire changed tree was not audited. [upstream comparison](https://api.github.com/repos/skysdottir/PotatoMelt/compare/main...shrine-priestess:main).

3. **Robot context and reported status.** Reported: LoserMelt derives from PotatoMelt’s sbus branch. Robot weight, exact built chassis, event history and a distinct verified Serval robot configuration: not found in the inspected README/source. [README.md](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/README.md).

4. **Hardware and exact parts.** Confirmed in inspected code: AVR Timer3/DShot-style motor path and SBUS receiver through Serial1. README lists ItsyBitsy M4 migration, CRSF/ELRS telemetry and possible 2D translation as planned, not completed. Exact installed MCU, motors, ESCs, receiver and battery: not found. [README.md](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/README.md), [losermelt/rc_handler.cpp](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/losermelt/rc_handler.cpp), [losermelt/spin_control.cpp](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/losermelt/spin_control.cpp).

5. **Heading sensing and mounting.** Confirmed: LIS331 force is (abs(Xg)+abs(Yg))/2, not a single radial axis or Euclidean magnitude; default effective radius4.2 cm and zero offset0 g. This is a configured model, not measured mounting geometry; physical validity of the axis average was not tested. [losermelt/accel_handler.cpp](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/losermelt/accel_handler.cpp), [losermelt/melty_config.h](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/losermelt/melty_config.h).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed: get_uncorrected_rpm computes sqrt((mean_abs_XY_g−zero)×89445/radius_cm), then eight-pair interpolated correction and steering yield period60,000,000/RPM. Unlike Serval snapshot, no abs() surrounds the offset-subtracted force here. Timer3 OCR3A=15999 at16 MHz/prescaler1 implies1 kHz despite a stale2 kHz comment; parameter path delays20 ms. Rates/negative-input behavior were not hardware-tested. [losermelt/accel_handler.cpp](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/losermelt/accel_handler.cpp), [losermelt/spin_control.cpp](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/losermelt/spin_control.cpp).

7. **Drift and correction.** Confirmed: speed-dependent correction table and direction-aware steering adjust the estimated period; calibration can alter LED-only offset. Long-term measured drift and impact realignment results: not found. [losermelt/spin_control.cpp](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/losermelt/spin_control.cpp), [losermelt/accel_handler.cpp](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/losermelt/accel_handler.cpp).

8. **Translation timing, phase width and stick mapping.** Confirmed: forward/back translation uses a parabolic approximation to half a sine, −4p(p−1), over each 180° phase; differential offset swaps between motors at the half-turn boundary. Offset scales with stick displacement, throttle and trim. The README’s possible 2D translation remains planned. [losermelt/spin_control.cpp](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/losermelt/spin_control.cpp), [README.md](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/README.md).

9. **Heading LED/display.** Confirmed: top/bottom digital heading LEDs on pins 13/12 are switched together, including shimmer; phase width derives from RPM and is clamped 10–90%. Physical LED mounting/brightness and inverted display alignment: not found. [losermelt/led_driver.cpp](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/losermelt/led_driver.cpp), [losermelt/melty_config.h](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/losermelt/melty_config.h), [losermelt/spin_control.cpp](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/losermelt/spin_control.cpp).

10. **Calibration and persistence.** Confirmed in code: config toggle captures stationary g offset; neutral/left-right tunes correction, backward/left-right tunes beacon phase; save-button events add correction pairs and EEPROM support is enabled. A successfully executed calibration log: not found. [losermelt/spin_control.cpp](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/losermelt/spin_control.cpp), [losermelt/accel_handler.cpp](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/losermelt/accel_handler.cpp), [losermelt/melty_config.h](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/losermelt/melty_config.h).

11. **Controls, modes, arming and failsafe.** Confirmed: Serial1 SBUS channel controls; tank mode and translation trim enabled; PID disabled; 2 s watchdog; CONTROL_MOTION_TIMEOUT_MS=30000 and MIN_TRANSLATION_RPM=800. The presence of these settings is not an end-to-end failsafe test. [losermelt/rc_handler.cpp](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/losermelt/rc_handler.cpp), [losermelt/melty_config.h](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/losermelt/melty_config.h).

12. **Distinctive ideas and implementation.** Distinctive inherited direction-aware parabolic translation and SBUS controls are visible in source. Planned CRSF/ELRS telemetry and M4 migration are not treated as delivered features. [losermelt/spin_control.cpp](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/losermelt/spin_control.cpp), [losermelt/rc_handler.cpp](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/losermelt/rc_handler.cpp), [README.md](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/README.md).

13. **Author-reported problems, failures and evidence limits.** Author-reported completed failure narrative: not found. Configuration comments still state non-AVR portability is untested; plans include hardware/protocol migration. No test evidence was found establishing those migrations. [losermelt/melty_config.h](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/losermelt/melty_config.h), [README.md](https://github.com/shrine-priestess/LoserMelt/blob/f3c07adc9f4a95813c3c411b9b3313a584644c7d/README.md).

14. **License and reuse notice.** GitHub repository metadata identifies LGPL-2.1. This survey did not audit all dependency or asset licenses. [repository metadata](https://api.github.com/repos/shrine-priestess/LoserMelt).

<a id="p095"></a>

## P095. kemacalls/ServalLoserMelt

1. **Identity, authorship, URLs and visible dates.** Repository owner: kemacalls. Inspected latest default-branch commit credited to Kezia Skye. Repository created 2026-03-18T12:15:12Z (UTC). Inspected commit 556cc4cdabf223b115acaa1977c6249aed23ec96 dated 2026-02-25T16:28:22Z (UTC). GitHub identifies parent shrine-priestess/LoserMelt. [repository metadata](https://api.github.com/repos/kemacalls/ServalLoserMelt); [inspected commit](https://github.com/kemacalls/ServalLoserMelt/commit/556cc4cdabf223b115acaa1977c6249aed23ec96).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [losermelt/accel_handler.cpp](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/losermelt/accel_handler.cpp), [losermelt/spin_control.cpp](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/losermelt/spin_control.cpp), [losermelt/melty_config.h](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/losermelt/melty_config.h), [losermelt/rc_handler.cpp](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/losermelt/rc_handler.cpp), [README.md](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/README.md). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: behind, 0 commit(s) ahead and 2 behind at inspection. No fork-specific commits appear in that comparison; no new fork implementation is inferred. [upstream comparison](https://api.github.com/repos/shrine-priestess/LoserMelt/compare/main...kemacalls:main).

3. **Robot context and reported status.** Reported: LoserMelt derives from PotatoMelt’s sbus branch. Robot weight, exact built chassis, event history and a distinct verified Serval robot configuration: not found in the inspected README/source. [README.md](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/README.md).

4. **Hardware and exact parts.** Confirmed in inspected code: AVR Timer3/DShot-style motor path and SBUS receiver through Serial1. README lists ItsyBitsy M4 migration, CRSF/ELRS telemetry and possible 2D translation as planned, not completed. Exact installed MCU, motors, ESCs, receiver and battery: not found. [README.md](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/README.md), [losermelt/rc_handler.cpp](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/losermelt/rc_handler.cpp), [losermelt/spin_control.cpp](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/losermelt/spin_control.cpp).

5. **Heading sensing and mounting.** Confirmed: Y-axis LIS331 g; default effective radius 2.6 cm and LED offset 7%. Actual physical mount: not found. [losermelt/accel_handler.cpp](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/losermelt/accel_handler.cpp), [losermelt/melty_config.h](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/losermelt/melty_config.h).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed: RPM=sqrt(abs(g−zero)×89445/radius_cm), corrected by an eight-pair interpolated RPM table; period=60,000,000/RPM. Timer3 uses OCR3A=15999 at 16 MHz/prescaler 1, implying 1 kHz despite a stale 2 kHz comment. Parameters update then delay 20 ms; achieved timing was not measured. [losermelt/accel_handler.cpp](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/losermelt/accel_handler.cpp), [losermelt/spin_control.cpp](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/losermelt/spin_control.cpp).

7. **Drift and correction.** Confirmed: speed-dependent correction table and direction-aware steering adjust the estimated period; calibration can alter LED-only offset. Long-term measured drift and impact realignment results: not found. [losermelt/spin_control.cpp](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/losermelt/spin_control.cpp), [losermelt/accel_handler.cpp](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/losermelt/accel_handler.cpp).

8. **Translation timing, phase width and stick mapping.** Confirmed: forward/back translation uses a parabolic approximation to half a sine, −4p(p−1), over each 180° phase; differential offset swaps between motors at the half-turn boundary. Offset scales with stick displacement, throttle and trim. The README’s possible 2D translation remains planned. [losermelt/spin_control.cpp](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/losermelt/spin_control.cpp), [README.md](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/README.md).

9. **Heading LED/display.** Confirmed: phase-centered LED arc with width based on RPM/target RPM, clamped 10–90%; shimmer marks adjustments. Exact output pins/number differ between snapshots below; physical location/visibility tests: not found. [losermelt/spin_control.cpp](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/losermelt/spin_control.cpp), [losermelt/melty_config.h](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/losermelt/melty_config.h).

10. **Calibration and persistence.** Confirmed in code: config toggle captures stationary g offset; neutral/left-right tunes correction, backward/left-right tunes beacon phase; save-button events add correction pairs and EEPROM support is enabled. A successfully executed calibration log: not found. [losermelt/spin_control.cpp](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/losermelt/spin_control.cpp), [losermelt/accel_handler.cpp](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/losermelt/accel_handler.cpp), [losermelt/melty_config.h](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/losermelt/melty_config.h).

11. **Controls, modes, arming and failsafe.** Confirmed: SBUS controls on Serial1; tank/translation trim enabled; PID disabled; 2 s watchdog; CONTROL_MOTION_TIMEOUT_MS=3000 and MIN_TRANSLATION_RPM=400. A hardware failsafe test is not supplied. [losermelt/rc_handler.cpp](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/losermelt/rc_handler.cpp), [losermelt/melty_config.h](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/losermelt/melty_config.h).

12. **Distinctive ideas and implementation.** Distinctive inherited direction-aware parabolic translation and SBUS controls are visible in source. Planned CRSF/ELRS telemetry and M4 migration are not treated as delivered features. [losermelt/spin_control.cpp](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/losermelt/spin_control.cpp), [losermelt/rc_handler.cpp](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/losermelt/rc_handler.cpp), [README.md](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/README.md).

13. **Author-reported problems, failures and evidence limits.** Author-reported completed failure narrative: not found. Configuration comments still state non-AVR portability is untested; plans include hardware/protocol migration. No test evidence was found establishing those migrations. [losermelt/melty_config.h](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/losermelt/melty_config.h), [README.md](https://github.com/kemacalls/ServalLoserMelt/blob/556cc4cdabf223b115acaa1977c6249aed23ec96/README.md).

14. **License and reuse notice.** GitHub repository metadata identifies LGPL-2.1. This survey did not audit all dependency or asset licenses. [repository metadata](https://api.github.com/repos/kemacalls/ServalLoserMelt).

<a id="p096"></a>

## P096. BTSC10/Oreo

1. **Identity, authorship, URLs and visible dates.** Repository owner: BTSC10. Inspected latest default-branch commit credited to BTSC10. Repository created 2022-11-12T23:51:06Z (UTC). Inspected commit 0b184f7268182e7d035c278b371867e926309bb1 dated 2023-08-15T09:52:53Z (UTC). [repository metadata](https://api.github.com/repos/BTSC10/Oreo); [inspected commit](https://github.com/BTSC10/Oreo/commit/0b184f7268182e7d035c278b371867e926309bb1).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [Software/Core/Src/main.c](https://github.com/BTSC10/Oreo/blob/0b184f7268182e7d035c278b371867e926309bb1/Software/Core/Src/main.c), [Software/Core/Inc/main.h](https://github.com/BTSC10/Oreo/blob/0b184f7268182e7d035c278b371867e926309bb1/Software/Core/Inc/main.h), [README.md](https://github.com/BTSC10/Oreo/blob/0b184f7268182e7d035c278b371867e926309bb1/README.md). Hardware tests/builds/simulations were not run by this survey. Changes from upstream not established; no verified parent-branch comparison was available/performed.

3. **Robot context and reported status.** Reported: beetleweight meltybrain combat robot. The BTSC10 README also uses the name Broos; completed motion tests and event results are not supplied in the inspected README/source. [README.md](https://github.com/BTSC10/Oreo/blob/0b184f7268182e7d035c278b371867e926309bb1/README.md).

4. **Hardware and exact parts.** Confirmed: an STM32F3 HAL/CMSIS software project is present. The inspected main.c initializes the system clock and GPIO but does not establish the intended sensor, motor driver, radio or battery parts. Hardware folders and a BOM spreadsheet were seen in repository inventory but not electrically/BOM-inspected; exact parts: not found in the inspected evidence. [Software/Core/Src/main.c](https://github.com/BTSC10/Oreo/blob/0b184f7268182e7d035c278b371867e926309bb1/Software/Core/Src/main.c), [Software/Core/Inc/main.h](https://github.com/BTSC10/Oreo/blob/0b184f7268182e7d035c278b371867e926309bb1/Software/Core/Inc/main.h).

5. **Heading sensing and mounting.** Heading sensor and mounting geometry: not found in the inspected main.c/main.h. Do not infer them from the meltybrain repository description. [Software/Core/Src/main.c](https://github.com/BTSC10/Oreo/blob/0b184f7268182e7d035c278b371867e926309bb1/Software/Core/Src/main.c), [Software/Core/Inc/main.h](https://github.com/BTSC10/Oreo/blob/0b184f7268182e7d035c278b371867e926309bb1/Software/Core/Inc/main.h).

6. **Angle/RPM algorithm, filters, rates and code locations.** Heading/RPM algorithm, sample frequency, filters and angle integration: not found. The inspected main.c contains an empty application while loop after initialization. [Software/Core/Src/main.c](https://github.com/BTSC10/Oreo/blob/0b184f7268182e7d035c278b371867e926309bb1/Software/Core/Src/main.c).

7. **Drift and correction.** Drift correction: not found in the inspected application source. [Software/Core/Src/main.c](https://github.com/BTSC10/Oreo/blob/0b184f7268182e7d035c278b371867e926309bb1/Software/Core/Src/main.c).

8. **Translation timing, phase width and stick mapping.** Translation timing, phase windows, pulse width and stick mapping: not found in the inspected application source. [Software/Core/Src/main.c](https://github.com/BTSC10/Oreo/blob/0b184f7268182e7d035c278b371867e926309bb1/Software/Core/Src/main.c).

9. **Heading LED/display.** Heading LED behavior/placement: not found in the inspected application source. [Software/Core/Src/main.c](https://github.com/BTSC10/Oreo/blob/0b184f7268182e7d035c278b371867e926309bb1/Software/Core/Src/main.c).

10. **Calibration and persistence.** Calibration procedure or code: not found in the inspected application source or README. [Software/Core/Src/main.c](https://github.com/BTSC10/Oreo/blob/0b184f7268182e7d035c278b371867e926309bb1/Software/Core/Src/main.c), [README.md](https://github.com/BTSC10/Oreo/blob/0b184f7268182e7d035c278b371867e926309bb1/README.md).

11. **Controls, modes, arming and failsafe.** Drive modes, RC controls, arming and failsafe implementation: not found in the inspected application source. [Software/Core/Src/main.c](https://github.com/BTSC10/Oreo/blob/0b184f7268182e7d035c278b371867e926309bb1/Software/Core/Src/main.c).

12. **Distinctive ideas and implementation.** Repository includes mechanical/electronic design assets, but their function and implementation differences were not inspected. No unusual working melty control algorithm is established by the source reviewed. [repository metadata](https://api.github.com/repos/BTSC10/Oreo).

13. **Author-reported problems, failures and evidence limits.** Author-reported failure/debugging narrative: not found in the inspected README; no hardware test result was established. [README.md](https://github.com/BTSC10/Oreo/blob/0b184f7268182e7d035c278b371867e926309bb1/README.md).

14. **License and reuse notice.** GitHub repository metadata identifies GPL-3.0. This survey did not audit all dependency or asset licenses. [repository metadata](https://api.github.com/repos/BTSC10/Oreo).

<a id="p097"></a>

## P097. Danwith2ns/Oreo

1. **Identity, authorship, URLs and visible dates.** Repository owner: Danwith2ns. Inspected latest default-branch commit credited to DoomsDayDeviceV3. Repository created 2023-03-08T16:06:09Z (UTC). Inspected commit cbc2eaa7b8017334f4b5686d390b2d06e3c5167d dated 2023-03-08T16:00:57Z (UTC). GitHub identifies parent BTSC10/Oreo. [repository metadata](https://api.github.com/repos/Danwith2ns/Oreo); [inspected commit](https://github.com/Danwith2ns/Oreo/commit/cbc2eaa7b8017334f4b5686d390b2d06e3c5167d).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [Software/Core/Src/main.c](https://github.com/Danwith2ns/Oreo/blob/cbc2eaa7b8017334f4b5686d390b2d06e3c5167d/Software/Core/Src/main.c), [Software/Core/Inc/main.h](https://github.com/Danwith2ns/Oreo/blob/cbc2eaa7b8017334f4b5686d390b2d06e3c5167d/Software/Core/Inc/main.h), [README.md](https://github.com/Danwith2ns/Oreo/blob/cbc2eaa7b8017334f4b5686d390b2d06e3c5167d/README.md). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: behind, 0 commit(s) ahead and 23 behind at inspection. No fork-specific commits appear in that comparison; no new fork implementation is inferred. [upstream comparison](https://api.github.com/repos/BTSC10/Oreo/compare/main...Danwith2ns:main).

3. **Robot context and reported status.** Reported: beetleweight meltybrain combat robot. The BTSC10 README also uses the name Broos; completed motion tests and event results are not supplied in the inspected README/source. [README.md](https://github.com/Danwith2ns/Oreo/blob/cbc2eaa7b8017334f4b5686d390b2d06e3c5167d/README.md).

4. **Hardware and exact parts.** Confirmed: an STM32F3 HAL/CMSIS software project is present. The inspected main.c initializes the system clock and GPIO but does not establish the intended sensor, motor driver, radio or battery parts. Hardware folders and a BOM spreadsheet were seen in repository inventory but not electrically/BOM-inspected; exact parts: not found in the inspected evidence. [Software/Core/Src/main.c](https://github.com/Danwith2ns/Oreo/blob/cbc2eaa7b8017334f4b5686d390b2d06e3c5167d/Software/Core/Src/main.c), [Software/Core/Inc/main.h](https://github.com/Danwith2ns/Oreo/blob/cbc2eaa7b8017334f4b5686d390b2d06e3c5167d/Software/Core/Inc/main.h).

5. **Heading sensing and mounting.** Heading sensor and mounting geometry: not found in the inspected main.c/main.h. Do not infer them from the meltybrain repository description. [Software/Core/Src/main.c](https://github.com/Danwith2ns/Oreo/blob/cbc2eaa7b8017334f4b5686d390b2d06e3c5167d/Software/Core/Src/main.c), [Software/Core/Inc/main.h](https://github.com/Danwith2ns/Oreo/blob/cbc2eaa7b8017334f4b5686d390b2d06e3c5167d/Software/Core/Inc/main.h).

6. **Angle/RPM algorithm, filters, rates and code locations.** Heading/RPM algorithm, sample frequency, filters and angle integration: not found. The inspected main.c contains an empty application while loop after initialization. [Software/Core/Src/main.c](https://github.com/Danwith2ns/Oreo/blob/cbc2eaa7b8017334f4b5686d390b2d06e3c5167d/Software/Core/Src/main.c).

7. **Drift and correction.** Drift correction: not found in the inspected application source. [Software/Core/Src/main.c](https://github.com/Danwith2ns/Oreo/blob/cbc2eaa7b8017334f4b5686d390b2d06e3c5167d/Software/Core/Src/main.c).

8. **Translation timing, phase width and stick mapping.** Translation timing, phase windows, pulse width and stick mapping: not found in the inspected application source. [Software/Core/Src/main.c](https://github.com/Danwith2ns/Oreo/blob/cbc2eaa7b8017334f4b5686d390b2d06e3c5167d/Software/Core/Src/main.c).

9. **Heading LED/display.** Heading LED behavior/placement: not found in the inspected application source. [Software/Core/Src/main.c](https://github.com/Danwith2ns/Oreo/blob/cbc2eaa7b8017334f4b5686d390b2d06e3c5167d/Software/Core/Src/main.c).

10. **Calibration and persistence.** Calibration procedure or code: not found in the inspected application source or README. [Software/Core/Src/main.c](https://github.com/Danwith2ns/Oreo/blob/cbc2eaa7b8017334f4b5686d390b2d06e3c5167d/Software/Core/Src/main.c), [README.md](https://github.com/Danwith2ns/Oreo/blob/cbc2eaa7b8017334f4b5686d390b2d06e3c5167d/README.md).

11. **Controls, modes, arming and failsafe.** Drive modes, RC controls, arming and failsafe implementation: not found in the inspected application source. [Software/Core/Src/main.c](https://github.com/Danwith2ns/Oreo/blob/cbc2eaa7b8017334f4b5686d390b2d06e3c5167d/Software/Core/Src/main.c).

12. **Distinctive ideas and implementation.** Repository includes mechanical/electronic design assets, but their function and implementation differences were not inspected. No unusual working melty control algorithm is established by the source reviewed. [repository metadata](https://api.github.com/repos/Danwith2ns/Oreo).

13. **Author-reported problems, failures and evidence limits.** Author-reported failure/debugging narrative: not found in the inspected README; no hardware test result was established. [README.md](https://github.com/Danwith2ns/Oreo/blob/cbc2eaa7b8017334f4b5686d390b2d06e3c5167d/README.md).

14. **License and reuse notice.** GitHub repository metadata identifies GPL-3.0. This survey did not audit all dependency or asset licenses. [repository metadata](https://api.github.com/repos/Danwith2ns/Oreo).

<a id="p098"></a>

## P098. rtforsy/openmelt

1. **Identity, authorship, URLs and visible dates.** Repository owner: rtforsy. Inspected latest default-branch commit credited to Rich Olson / nothinglabs.com. Repository created 2018-04-21T23:26:10Z (UTC). Inspected commit 0aa68b1365df1c0da0bc29fb3c985a0456ef06a6 dated 2015-04-04T18:24:18Z (UTC). GitHub identifies parent nothinglabs/openmelt. [repository metadata](https://api.github.com/repos/rtforsy/openmelt); [inspected commit](https://github.com/rtforsy/openmelt/commit/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [main.c](https://github.com/rtforsy/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c), [makefile](https://github.com/rtforsy/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/makefile). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: behind, 0 commit(s) ahead and 3 behind at inspection. No fork-specific commits appear in that comparison; no new fork implementation is inferred. [upstream comparison](https://api.github.com/repos/nothinglabs/openmelt/compare/master...rtforsy:master).

3. **Robot context and reported status.** Reported in inherited source documentation: a one- or two-motor translational-drift controller; source assumes counterclockwise drive. Robot weight, exact chassis and fork-owner competition results: not found. [main.c](https://github.com/rtforsy/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

4. **Hardware and exact parts.** Reported hardware in source: Pololu Baby Orangutan/AVR platform; analog accelerometer options include SparkFun-mounted ADXL193; NPN Darlington motor drivers or fast-PWM brushless controllers; heading LED driven through the board motor driver. The makefile selects atmega168. An exact fork-specific parts list, motors and battery: not found. [main.c](https://github.com/rtforsy/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c), [makefile](https://github.com/rtforsy/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/makefile).

5. **Heading sensing and mounting.** Reported mounting: ADXL193 arrow away from spin center; effective radius default is 5.4 cm. Analog sensor force estimates relative rotational phase, with a once-per-turn LED. No compass/external absolute reference is used in the inspected calculation path. [main.c](https://github.com/rtforsy/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed in main_calculations: four ADC samples spaced by 20 µs, then a 0.6 old/0.4 new running average; subtract base ADC offset, convert to g, then RPM=sqrt(g×89445/radius_cm). Timer1 provides the spin timing; documented build notes describe about 3 µs resolution. This is not a fixed measured heading-update frequency. [main.c](https://github.com/rtforsy/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

7. **Drift and correction.** Reported/confirmed in source: effective-radius calibration and left/right heading steering compensate tracking drift. Source says the moving average improves tracking stability at the cost of lag during RPM changes. Quantified residual drift and impact response: not found. [main.c](https://github.com/rtforsy/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

8. **Translation timing, phase width and stick mapping.** Confirmed/reported in source: motors are switched on/off over throttle-dependent portions of each turn, with opposite timing for motor 2; neutral alternates phases to cancel translation. Below min_rpm=500, full-power spin-up is selected. Maximum RPM/g limits reduce requested throttle. A separate user-selected impulse-width control beyond throttle timing: not found. [main.c](https://github.com/rtforsy/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

9. **Heading LED/display.** Reported: heading LED may be up to 3 W, driven by the Baby Orangutan motor bridge; slow/fast/config flashes convey status, and flash count reports highest RPM. Default documented geometry puts motor 1 at 9 o’clock, motor 2 at 3 o’clock and LED at 6 o’clock. Actual fork-owner hardware: not found. [main.c](https://github.com/rtforsy/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

10. **Calibration and persistence.** Reported procedure in source: enter config only at rest; capture accelerometer zero, adjust tracking with left/right at low throttle, adjust beacon alignment at mid throttle, and retain calibration. Source contains EEPROM-related setup. A new procedure or successful calibration record for this fork owner: not found. [main.c](https://github.com/rtforsy/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

11. **Controls, modes, arming and failsafe.** Confirmed/reported in source: three RC pulse inputs, centered-stick startup gating, lost-throttle-update tracking and RPM/g limiting. RC throttle is smoothed 85% old/15% new and steering 50/50. Exact radio model and end-to-end loss-of-radio testing for the fork: not found. [main.c](https://github.com/rtforsy/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

12. **Distinctive ideas and implementation.** Distinctive inherited implementation: native AVR timer/ADC code, binary motor duty by angular timing, analog high-g sensor options, and combined motor/LED timing rather than an Arduino framework. Separate fork control changes are addressed in field 2. [main.c](https://github.com/rtforsy/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c), [makefile](https://github.com/rtforsy/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/makefile).

13. **Author-reported problems, failures and evidence limits.** Inherited author notes report low-voltage reboots/receiver dropout/calibration loss, erratic translation when two-wheel robots are unbalanced, and scraping linked to vertical balance. Brushless two-motor support is explicitly described as not specifically tested. These are source-author notes, not new results by this fork owner. [main.c](https://github.com/rtforsy/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

14. **License and reuse notice.** The source header states Creative Commons Attribution–NonCommercial–ShareAlike 3.0. No separate repository license file was established; the code-header notice is the evidence. [main.c](https://github.com/rtforsy/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

<a id="p099"></a>

## P099. acklenx/openmelt

1. **Identity, authorship, URLs and visible dates.** Repository owner: acklenx. Inspected latest default-branch commit credited to Rich Olson / nothinglabs.com. Repository created 2021-01-28T04:21:22Z (UTC). Inspected commit 0aa68b1365df1c0da0bc29fb3c985a0456ef06a6 dated 2015-04-04T18:24:18Z (UTC). GitHub identifies parent nothinglabs/openmelt. [repository metadata](https://api.github.com/repos/acklenx/openmelt); [inspected commit](https://github.com/acklenx/openmelt/commit/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [main.c](https://github.com/acklenx/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c), [makefile](https://github.com/acklenx/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/makefile). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: behind, 0 commit(s) ahead and 3 behind at inspection. No fork-specific commits appear in that comparison; no new fork implementation is inferred. [upstream comparison](https://api.github.com/repos/nothinglabs/openmelt/compare/master...acklenx:master).

3. **Robot context and reported status.** Reported in inherited source documentation: a one- or two-motor translational-drift controller; source assumes counterclockwise drive. Robot weight, exact chassis and fork-owner competition results: not found. [main.c](https://github.com/acklenx/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

4. **Hardware and exact parts.** Reported hardware in source: Pololu Baby Orangutan/AVR platform; analog accelerometer options include SparkFun-mounted ADXL193; NPN Darlington motor drivers or fast-PWM brushless controllers; heading LED driven through the board motor driver. The makefile selects atmega168. An exact fork-specific parts list, motors and battery: not found. [main.c](https://github.com/acklenx/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c), [makefile](https://github.com/acklenx/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/makefile).

5. **Heading sensing and mounting.** Reported mounting: ADXL193 arrow away from spin center; effective radius default is 5.4 cm. Analog sensor force estimates relative rotational phase, with a once-per-turn LED. No compass/external absolute reference is used in the inspected calculation path. [main.c](https://github.com/acklenx/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed in main_calculations: four ADC samples spaced by 20 µs, then a 0.6 old/0.4 new running average; subtract base ADC offset, convert to g, then RPM=sqrt(g×89445/radius_cm). Timer1 provides the spin timing; documented build notes describe about 3 µs resolution. This is not a fixed measured heading-update frequency. [main.c](https://github.com/acklenx/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

7. **Drift and correction.** Reported/confirmed in source: effective-radius calibration and left/right heading steering compensate tracking drift. Source says the moving average improves tracking stability at the cost of lag during RPM changes. Quantified residual drift and impact response: not found. [main.c](https://github.com/acklenx/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

8. **Translation timing, phase width and stick mapping.** Confirmed/reported in source: motors are switched on/off over throttle-dependent portions of each turn, with opposite timing for motor 2; neutral alternates phases to cancel translation. Below min_rpm=500, full-power spin-up is selected. Maximum RPM/g limits reduce requested throttle. A separate user-selected impulse-width control beyond throttle timing: not found. [main.c](https://github.com/acklenx/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

9. **Heading LED/display.** Reported: heading LED may be up to 3 W, driven by the Baby Orangutan motor bridge; slow/fast/config flashes convey status, and flash count reports highest RPM. Default documented geometry puts motor 1 at 9 o’clock, motor 2 at 3 o’clock and LED at 6 o’clock. Actual fork-owner hardware: not found. [main.c](https://github.com/acklenx/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

10. **Calibration and persistence.** Reported procedure in source: enter config only at rest; capture accelerometer zero, adjust tracking with left/right at low throttle, adjust beacon alignment at mid throttle, and retain calibration. Source contains EEPROM-related setup. A new procedure or successful calibration record for this fork owner: not found. [main.c](https://github.com/acklenx/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

11. **Controls, modes, arming and failsafe.** Confirmed/reported in source: three RC pulse inputs, centered-stick startup gating, lost-throttle-update tracking and RPM/g limiting. RC throttle is smoothed 85% old/15% new and steering 50/50. Exact radio model and end-to-end loss-of-radio testing for the fork: not found. [main.c](https://github.com/acklenx/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

12. **Distinctive ideas and implementation.** Distinctive inherited implementation: native AVR timer/ADC code, binary motor duty by angular timing, analog high-g sensor options, and combined motor/LED timing rather than an Arduino framework. Separate fork control changes are addressed in field 2. [main.c](https://github.com/acklenx/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c), [makefile](https://github.com/acklenx/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/makefile).

13. **Author-reported problems, failures and evidence limits.** Inherited author notes report low-voltage reboots/receiver dropout/calibration loss, erratic translation when two-wheel robots are unbalanced, and scraping linked to vertical balance. Brushless two-motor support is explicitly described as not specifically tested. These are source-author notes, not new results by this fork owner. [main.c](https://github.com/acklenx/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

14. **License and reuse notice.** The source header states Creative Commons Attribution–NonCommercial–ShareAlike 3.0. No separate repository license file was established; the code-header notice is the evidence. [main.c](https://github.com/acklenx/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

<a id="p100"></a>

## P100. qbnut/openmelt

1. **Identity, authorship, URLs and visible dates.** Repository owner: qbnut. Inspected latest default-branch commit credited to Rich Olson / nothinglabs.com. Repository created 2019-06-04T20:11:55Z (UTC). Inspected commit 0aa68b1365df1c0da0bc29fb3c985a0456ef06a6 dated 2015-04-04T18:24:18Z (UTC). GitHub identifies parent nothinglabs/openmelt. [repository metadata](https://api.github.com/repos/qbnut/openmelt); [inspected commit](https://github.com/qbnut/openmelt/commit/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [main.c](https://github.com/qbnut/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c), [makefile](https://github.com/qbnut/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/makefile). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: behind, 0 commit(s) ahead and 3 behind at inspection. No fork-specific commits appear in that comparison; no new fork implementation is inferred. [upstream comparison](https://api.github.com/repos/nothinglabs/openmelt/compare/master...qbnut:master).

3. **Robot context and reported status.** Reported in inherited source documentation: a one- or two-motor translational-drift controller; source assumes counterclockwise drive. Robot weight, exact chassis and fork-owner competition results: not found. [main.c](https://github.com/qbnut/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

4. **Hardware and exact parts.** Reported hardware in source: Pololu Baby Orangutan/AVR platform; analog accelerometer options include SparkFun-mounted ADXL193; NPN Darlington motor drivers or fast-PWM brushless controllers; heading LED driven through the board motor driver. The makefile selects atmega168. An exact fork-specific parts list, motors and battery: not found. [main.c](https://github.com/qbnut/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c), [makefile](https://github.com/qbnut/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/makefile).

5. **Heading sensing and mounting.** Reported mounting: ADXL193 arrow away from spin center; effective radius default is 5.4 cm. Analog sensor force estimates relative rotational phase, with a once-per-turn LED. No compass/external absolute reference is used in the inspected calculation path. [main.c](https://github.com/qbnut/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed in main_calculations: four ADC samples spaced by 20 µs, then a 0.6 old/0.4 new running average; subtract base ADC offset, convert to g, then RPM=sqrt(g×89445/radius_cm). Timer1 provides the spin timing; documented build notes describe about 3 µs resolution. This is not a fixed measured heading-update frequency. [main.c](https://github.com/qbnut/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

7. **Drift and correction.** Reported/confirmed in source: effective-radius calibration and left/right heading steering compensate tracking drift. Source says the moving average improves tracking stability at the cost of lag during RPM changes. Quantified residual drift and impact response: not found. [main.c](https://github.com/qbnut/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

8. **Translation timing, phase width and stick mapping.** Confirmed/reported in source: motors are switched on/off over throttle-dependent portions of each turn, with opposite timing for motor 2; neutral alternates phases to cancel translation. Below min_rpm=500, full-power spin-up is selected. Maximum RPM/g limits reduce requested throttle. A separate user-selected impulse-width control beyond throttle timing: not found. [main.c](https://github.com/qbnut/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

9. **Heading LED/display.** Reported: heading LED may be up to 3 W, driven by the Baby Orangutan motor bridge; slow/fast/config flashes convey status, and flash count reports highest RPM. Default documented geometry puts motor 1 at 9 o’clock, motor 2 at 3 o’clock and LED at 6 o’clock. Actual fork-owner hardware: not found. [main.c](https://github.com/qbnut/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

10. **Calibration and persistence.** Reported procedure in source: enter config only at rest; capture accelerometer zero, adjust tracking with left/right at low throttle, adjust beacon alignment at mid throttle, and retain calibration. Source contains EEPROM-related setup. A new procedure or successful calibration record for this fork owner: not found. [main.c](https://github.com/qbnut/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

11. **Controls, modes, arming and failsafe.** Confirmed/reported in source: three RC pulse inputs, centered-stick startup gating, lost-throttle-update tracking and RPM/g limiting. RC throttle is smoothed 85% old/15% new and steering 50/50. Exact radio model and end-to-end loss-of-radio testing for the fork: not found. [main.c](https://github.com/qbnut/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

12. **Distinctive ideas and implementation.** Distinctive inherited implementation: native AVR timer/ADC code, binary motor duty by angular timing, analog high-g sensor options, and combined motor/LED timing rather than an Arduino framework. Separate fork control changes are addressed in field 2. [main.c](https://github.com/qbnut/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c), [makefile](https://github.com/qbnut/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/makefile).

13. **Author-reported problems, failures and evidence limits.** Inherited author notes report low-voltage reboots/receiver dropout/calibration loss, erratic translation when two-wheel robots are unbalanced, and scraping linked to vertical balance. Brushless two-motor support is explicitly described as not specifically tested. These are source-author notes, not new results by this fork owner. [main.c](https://github.com/qbnut/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

14. **License and reuse notice.** The source header states Creative Commons Attribution–NonCommercial–ShareAlike 3.0. No separate repository license file was established; the code-header notice is the evidence. [main.c](https://github.com/qbnut/openmelt/blob/0aa68b1365df1c0da0bc29fb3c985a0456ef06a6/main.c).

<a id="p101"></a>

## P101. dhmeves/openmelt

1. **Identity, authorship, URLs and visible dates.** Repository owner: dhmeves. Inspected latest default-branch commit credited to Rich Olson / nothinglabs.com. Repository created 2018-02-24T04:35:35Z (UTC). Inspected commit 5bc3d4302229542ae18d205e803a478480f0aa44 dated 2023-12-13T05:02:38Z (UTC). GitHub identifies parent nothinglabs/openmelt. [repository metadata](https://api.github.com/repos/dhmeves/openmelt); [inspected commit](https://github.com/dhmeves/openmelt/commit/5bc3d4302229542ae18d205e803a478480f0aa44).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [main.c](https://github.com/dhmeves/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/main.c), [makefile](https://github.com/dhmeves/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/makefile), [README.md](https://github.com/dhmeves/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/README.md). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: identical, 0 commit(s) ahead and 0 behind at inspection. No fork-specific commits appear in that comparison; no new fork implementation is inferred. [upstream comparison](https://api.github.com/repos/nothinglabs/openmelt/compare/master...dhmeves:master).

3. **Robot context and reported status.** Reported in inherited source documentation: a one- or two-motor translational-drift controller; source assumes counterclockwise drive. Robot weight, exact chassis and fork-owner competition results: not found. [main.c](https://github.com/dhmeves/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/main.c).

4. **Hardware and exact parts.** Reported hardware in source: Pololu Baby Orangutan/AVR platform; analog accelerometer options include SparkFun-mounted ADXL193; NPN Darlington motor drivers or fast-PWM brushless controllers; heading LED driven through the board motor driver. The makefile selects atmega168. An exact fork-specific parts list, motors and battery: not found. [main.c](https://github.com/dhmeves/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/main.c), [makefile](https://github.com/dhmeves/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/makefile).

5. **Heading sensing and mounting.** Reported mounting: ADXL193 arrow away from spin center; effective radius default is 5.4 cm. Analog sensor force estimates relative rotational phase, with a once-per-turn LED. No compass/external absolute reference is used in the inspected calculation path. [main.c](https://github.com/dhmeves/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/main.c).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed in main_calculations: four ADC samples spaced by 20 µs, then a 0.6 old/0.4 new running average; subtract base ADC offset, convert to g, then RPM=sqrt(g×89445/radius_cm). Timer1 provides the spin timing; documented build notes describe about 3 µs resolution. This is not a fixed measured heading-update frequency. [main.c](https://github.com/dhmeves/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/main.c).

7. **Drift and correction.** Reported/confirmed in source: effective-radius calibration and left/right heading steering compensate tracking drift. Source says the moving average improves tracking stability at the cost of lag during RPM changes. Quantified residual drift and impact response: not found. [main.c](https://github.com/dhmeves/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/main.c).

8. **Translation timing, phase width and stick mapping.** Confirmed/reported in source: motors are switched on/off over throttle-dependent portions of each turn, with opposite timing for motor 2; neutral alternates phases to cancel translation. Below min_rpm=500, full-power spin-up is selected. Maximum RPM/g limits reduce requested throttle. A separate user-selected impulse-width control beyond throttle timing: not found. [main.c](https://github.com/dhmeves/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/main.c).

9. **Heading LED/display.** Reported: heading LED may be up to 3 W, driven by the Baby Orangutan motor bridge; slow/fast/config flashes convey status, and flash count reports highest RPM. Default documented geometry puts motor 1 at 9 o’clock, motor 2 at 3 o’clock and LED at 6 o’clock. Actual fork-owner hardware: not found. [main.c](https://github.com/dhmeves/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/main.c).

10. **Calibration and persistence.** Reported procedure in source: enter config only at rest; capture accelerometer zero, adjust tracking with left/right at low throttle, adjust beacon alignment at mid throttle, and retain calibration. Source contains EEPROM-related setup. A new procedure or successful calibration record for this fork owner: not found. [main.c](https://github.com/dhmeves/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/main.c).

11. **Controls, modes, arming and failsafe.** Confirmed/reported in source: three RC pulse inputs, centered-stick startup gating, lost-throttle-update tracking and RPM/g limiting. RC throttle is smoothed 85% old/15% new and steering 50/50. Exact radio model and end-to-end loss-of-radio testing for the fork: not found. [main.c](https://github.com/dhmeves/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/main.c).

12. **Distinctive ideas and implementation.** Distinctive inherited implementation: native AVR timer/ADC code, binary motor duty by angular timing, analog high-g sensor options, and combined motor/LED timing rather than an Arduino framework. Separate fork control changes are addressed in field 2. [main.c](https://github.com/dhmeves/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/main.c), [makefile](https://github.com/dhmeves/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/makefile).

13. **Author-reported problems, failures and evidence limits.** Inherited author notes report low-voltage reboots/receiver dropout/calibration loss, erratic translation when two-wheel robots are unbalanced, and scraping linked to vertical balance. Brushless two-motor support is explicitly described as not specifically tested. These are source-author notes, not new results by this fork owner. [main.c](https://github.com/dhmeves/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/main.c).

14. **License and reuse notice.** The source header states Creative Commons Attribution–NonCommercial–ShareAlike 3.0. No separate repository license file was established; the code-header notice is the evidence. [main.c](https://github.com/dhmeves/openmelt/blob/5bc3d4302229542ae18d205e803a478480f0aa44/main.c).

<a id="p102"></a>

## P102. gentry-atkinson/openmelt

1. **Identity, authorship, URLs and visible dates.** Repository owner: gentry-atkinson. Inspected latest default-branch commit credited to Gentry Atkinson. Repository created 2019-11-12T20:35:40Z (UTC). Inspected commit cd09fc6d9aea4629ec0a438d75ccd69d92e15fac dated 2020-04-03T19:27:14Z (UTC). GitHub identifies parent nothinglabs/openmelt. [repository metadata](https://api.github.com/repos/gentry-atkinson/openmelt); [inspected commit](https://github.com/gentry-atkinson/openmelt/commit/cd09fc6d9aea4629ec0a438d75ccd69d92e15fac).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [main.c](https://github.com/gentry-atkinson/openmelt/blob/cd09fc6d9aea4629ec0a438d75ccd69d92e15fac/main.c), [makefile](https://github.com/gentry-atkinson/openmelt/blob/cd09fc6d9aea4629ec0a438d75ccd69d92e15fac/makefile). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: diverged, 2 commit(s) ahead and 3 behind at inspection. Inspected change list removes old artifacts/archives; main.c blob is unchanged in the inspected snapshots. No new control algorithm is inferred. [upstream comparison](https://api.github.com/repos/nothinglabs/openmelt/compare/master...gentry-atkinson:master).

3. **Robot context and reported status.** Reported in inherited source documentation: a one- or two-motor translational-drift controller; source assumes counterclockwise drive. Robot weight, exact chassis and fork-owner competition results: not found. [main.c](https://github.com/gentry-atkinson/openmelt/blob/cd09fc6d9aea4629ec0a438d75ccd69d92e15fac/main.c).

4. **Hardware and exact parts.** Reported hardware in source: Pololu Baby Orangutan/AVR platform; analog accelerometer options include SparkFun-mounted ADXL193; NPN Darlington motor drivers or fast-PWM brushless controllers; heading LED driven through the board motor driver. The makefile selects atmega168. An exact fork-specific parts list, motors and battery: not found. [main.c](https://github.com/gentry-atkinson/openmelt/blob/cd09fc6d9aea4629ec0a438d75ccd69d92e15fac/main.c), [makefile](https://github.com/gentry-atkinson/openmelt/blob/cd09fc6d9aea4629ec0a438d75ccd69d92e15fac/makefile).

5. **Heading sensing and mounting.** Reported mounting: ADXL193 arrow away from spin center; effective radius default is 5.4 cm. Analog sensor force estimates relative rotational phase, with a once-per-turn LED. No compass/external absolute reference is used in the inspected calculation path. [main.c](https://github.com/gentry-atkinson/openmelt/blob/cd09fc6d9aea4629ec0a438d75ccd69d92e15fac/main.c).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed in main_calculations: four ADC samples spaced by 20 µs, then a 0.6 old/0.4 new running average; subtract base ADC offset, convert to g, then RPM=sqrt(g×89445/radius_cm). Timer1 provides the spin timing; documented build notes describe about 3 µs resolution. This is not a fixed measured heading-update frequency. [main.c](https://github.com/gentry-atkinson/openmelt/blob/cd09fc6d9aea4629ec0a438d75ccd69d92e15fac/main.c).

7. **Drift and correction.** Reported/confirmed in source: effective-radius calibration and left/right heading steering compensate tracking drift. Source says the moving average improves tracking stability at the cost of lag during RPM changes. Quantified residual drift and impact response: not found. [main.c](https://github.com/gentry-atkinson/openmelt/blob/cd09fc6d9aea4629ec0a438d75ccd69d92e15fac/main.c).

8. **Translation timing, phase width and stick mapping.** Confirmed/reported in source: motors are switched on/off over throttle-dependent portions of each turn, with opposite timing for motor 2; neutral alternates phases to cancel translation. Below min_rpm=500, full-power spin-up is selected. Maximum RPM/g limits reduce requested throttle. A separate user-selected impulse-width control beyond throttle timing: not found. [main.c](https://github.com/gentry-atkinson/openmelt/blob/cd09fc6d9aea4629ec0a438d75ccd69d92e15fac/main.c).

9. **Heading LED/display.** Reported: heading LED may be up to 3 W, driven by the Baby Orangutan motor bridge; slow/fast/config flashes convey status, and flash count reports highest RPM. Default documented geometry puts motor 1 at 9 o’clock, motor 2 at 3 o’clock and LED at 6 o’clock. Actual fork-owner hardware: not found. [main.c](https://github.com/gentry-atkinson/openmelt/blob/cd09fc6d9aea4629ec0a438d75ccd69d92e15fac/main.c).

10. **Calibration and persistence.** Reported procedure in source: enter config only at rest; capture accelerometer zero, adjust tracking with left/right at low throttle, adjust beacon alignment at mid throttle, and retain calibration. Source contains EEPROM-related setup. A new procedure or successful calibration record for this fork owner: not found. [main.c](https://github.com/gentry-atkinson/openmelt/blob/cd09fc6d9aea4629ec0a438d75ccd69d92e15fac/main.c).

11. **Controls, modes, arming and failsafe.** Confirmed/reported in source: three RC pulse inputs, centered-stick startup gating, lost-throttle-update tracking and RPM/g limiting. RC throttle is smoothed 85% old/15% new and steering 50/50. Exact radio model and end-to-end loss-of-radio testing for the fork: not found. [main.c](https://github.com/gentry-atkinson/openmelt/blob/cd09fc6d9aea4629ec0a438d75ccd69d92e15fac/main.c).

12. **Distinctive ideas and implementation.** Distinctive inherited implementation: native AVR timer/ADC code, binary motor duty by angular timing, analog high-g sensor options, and combined motor/LED timing rather than an Arduino framework. Separate fork control changes are addressed in field 2. [main.c](https://github.com/gentry-atkinson/openmelt/blob/cd09fc6d9aea4629ec0a438d75ccd69d92e15fac/main.c), [makefile](https://github.com/gentry-atkinson/openmelt/blob/cd09fc6d9aea4629ec0a438d75ccd69d92e15fac/makefile).

13. **Author-reported problems, failures and evidence limits.** Inherited author notes report low-voltage reboots/receiver dropout/calibration loss, erratic translation when two-wheel robots are unbalanced, and scraping linked to vertical balance. Brushless two-motor support is explicitly described as not specifically tested. These are source-author notes, not new results by this fork owner. [main.c](https://github.com/gentry-atkinson/openmelt/blob/cd09fc6d9aea4629ec0a438d75ccd69d92e15fac/main.c).

14. **License and reuse notice.** The source header states Creative Commons Attribution–NonCommercial–ShareAlike 3.0. No separate repository license file was established; the code-header notice is the evidence. [main.c](https://github.com/gentry-atkinson/openmelt/blob/cd09fc6d9aea4629ec0a438d75ccd69d92e15fac/main.c).

<a id="p103"></a>

## P103. amramsey/openmelt2

1. **Identity, authorship, URLs and visible dates.** Repository owner: amramsey. Inspected latest default-branch commit credited to Rich Olson / nothinglabs.com. Repository created 2026-02-04T02:45:13Z (UTC). Inspected commit 7d062906950647350195b2b439e6f40e28492ce7 dated 2025-02-03T04:24:28Z (UTC). GitHub identifies parent nothinglabs/openmelt2. [repository metadata](https://api.github.com/repos/amramsey/openmelt2); [inspected commit](https://github.com/amramsey/openmelt2/commit/7d062906950647350195b2b439e6f40e28492ce7).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [openmelt/accel_handler.cpp](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/accel_handler.cpp), [openmelt/spin_control.cpp](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/spin_control.cpp), [openmelt/melty_config.h](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/melty_config.h), [openmelt/rc_handler.cpp](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/rc_handler.cpp), [openmelt/motor_driver.cpp](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/motor_driver.cpp), [readme.md](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: identical, 0 commit(s) ahead and 0 behind at inspection. No fork-specific commits appear in that comparison; no new fork implementation is inferred. [upstream comparison](https://api.github.com/repos/nothinglabs/openmelt2/compare/main...amramsey:main).

3. **Robot context and reported status.** Reported in inherited README: Open Melt 2 is an Arduino translational-drift controller for one or two drive motors, with an antweight reference platform. The inherited 3200 RPM testing claim belongs to the upstream project, not an independently verified build of this fork. A separate fork robot and event record: not found. [readme.md](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md).

4. **Hardware and exact parts.** Reported inherited hardware: Arduino Micro/ATmega32u4 5 V 16 MHz; H3LIS331DL, preferably Adafruit breakout; optional SparkFun breakout plus level converter; hobby RC receiver, heading LED and motor driver(s). Reference motor switching uses RFP30N06LE; SimonK Hobbypower 30 A support is reported. Exact hardware built by this fork owner: not found. [readme.md](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md).

5. **Heading sensing and mounting.** Confirmed in code: X-axis LIS331 acceleration through I2C; default effective radius 3.9 cm. README describes interactive orientation/radius compensation and respecting 400 g full-scale loading. The number is a software default, not a measured fork mounting radius. [openmelt/accel_handler.cpp](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/accel_handler.cpp), [openmelt/melty_config.h](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/melty_config.h), [readme.md](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed in get_rotation_interval_ms: RPM=sqrt(abs(g−zero)×89445/effective_radius_cm), then period=60,000/RPM ms. Steering changes effective radius. I2C is configured at 400 kHz; no explicit additional digital noise filter or fixed measured loop frequency was found in the inspected accel/spin files. [openmelt/accel_handler.cpp](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/accel_handler.cpp), [openmelt/spin_control.cpp](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/spin_control.cpp).

7. **Drift and correction.** Confirmed/reported: radius/zero-offset setup corrects speed tracking; RC left/right trim adjusts heading by changing the estimated period. LED phase has an independent stored offset. Automatic absolute-heading recovery and quantified drift tests for this fork: not found. [openmelt/spin_control.cpp](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/spin_control.cpp), [readme.md](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md).

8. **Translation timing, phase width and stick mapping.** Confirmed in code: motor-on duration is throttle fraction of the estimated revolution in default BINARY_THROTTLE. Motor windows are centered half a turn apart; forward/back swaps them and neutral alternates to cancel drift. Below 400 RPM the code requests full-rotation power. Dynamic-PWM mode can fix on-duration at 50%, but configuration selection must be checked separately. [openmelt/spin_control.cpp](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/spin_control.cpp), [openmelt/melty_config.h](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/melty_config.h).

9. **Heading LED/display.** Confirmed/reported: once-per-turn beacon centered on a stored 0–99% offset, width follows throttle and is clamped to 10–90% of a turn; shimmer indicates low battery or calibration adjustment. README discusses shell occlusion at shallow viewing angles. Exact fork LED model and placement: not found. [openmelt/spin_control.cpp](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/spin_control.cpp), [readme.md](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md).

10. **Calibration and persistence.** Reported/confirmed: enter config while stopped by holding back for about 1 s; zero-g is averaged, neutral forward/back permits radius tuning, backward diagonal adjusts LED offset, forward tests movement. Save to EEPROM on exit. Fork-specific calibration measurements: not found. [readme.md](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md), [openmelt/spin_control.cpp](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/spin_control.cpp).

11. **Controls, modes, arming and failsafe.** Confirmed/reported: three interrupt-read RC channels; zero-throttle startup verification and a configured 2 s watchdog. README describes stopping after about 1 s without throttle updates and resuming when signals return. This is source behavior, not an independently exercised failsafe. [openmelt/rc_handler.cpp](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/rc_handler.cpp), [openmelt/melty_config.h](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/melty_config.h), [readme.md](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md).

12. **Distinctive ideas and implementation.** Distinctive inherited design: interactive radius and LED-offset calibration, one/two-wheel timing without a wheel-count setting, and binary/fixed/dynamic-PWM motor modes. Fork-specific work is recorded separately in field 2. [openmelt/spin_control.cpp](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/spin_control.cpp), [openmelt/melty_config.h](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/melty_config.h).

13. **Author-reported problems, failures and evidence limits.** Inherited author reports: some one-wheel builds bounce/oscillate and lose translational control at high speed; a prototype hang/runaway was associated with I2C wiring/library failure, prompting watchdog use. These are upstream reports copied into the README, not validated failures of this fork. [readme.md](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md).

14. **License and reuse notice.** Inherited README states Creative Commons Attribution–NonCommercial–ShareAlike 4.0. A separate license audit of this fork’s additions was not performed. [readme.md](https://github.com/amramsey/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md).

<a id="p104"></a>

## P104. teamhappybots/openmelt2

1. **Identity, authorship, URLs and visible dates.** Repository owner: teamhappybots. Inspected latest default-branch commit credited to Rich Olson / nothinglabs.com. Repository created 2025-02-07T21:59:38Z (UTC). Inspected commit 7d062906950647350195b2b439e6f40e28492ce7 dated 2025-02-03T04:24:28Z (UTC). GitHub identifies parent nothinglabs/openmelt2. [repository metadata](https://api.github.com/repos/teamhappybots/openmelt2); [inspected commit](https://github.com/teamhappybots/openmelt2/commit/7d062906950647350195b2b439e6f40e28492ce7).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [openmelt/motor_driver.cpp](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/motor_driver.cpp), [readme.md](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md), [openmelt/accel_handler.cpp](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/accel_handler.cpp), [openmelt/spin_control.cpp](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/spin_control.cpp), [openmelt/melty_config.h](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/melty_config.h), [openmelt/rc_handler.cpp](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/rc_handler.cpp). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: identical, 0 commit(s) ahead and 0 behind at inspection. No fork-specific commits appear in that comparison; no new fork implementation is inferred. [upstream comparison](https://api.github.com/repos/nothinglabs/openmelt2/compare/main...teamhappybots:main).

3. **Robot context and reported status.** Reported in inherited README: Open Melt 2 is an Arduino translational-drift controller for one or two drive motors, with an antweight reference platform. The inherited 3200 RPM testing claim belongs to the upstream project, not an independently verified build of this fork. A separate fork robot and event record: not found. [readme.md](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md).

4. **Hardware and exact parts.** Reported inherited hardware: Arduino Micro/ATmega32u4 5 V 16 MHz; H3LIS331DL, preferably Adafruit breakout; optional SparkFun breakout plus level converter; hobby RC receiver, heading LED and motor driver(s). Reference motor switching uses RFP30N06LE; SimonK Hobbypower 30 A support is reported. Exact hardware built by this fork owner: not found. [readme.md](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md).

5. **Heading sensing and mounting.** Confirmed in code: X-axis LIS331 acceleration through I2C; default effective radius 3.9 cm. README describes interactive orientation/radius compensation and respecting 400 g full-scale loading. The number is a software default, not a measured fork mounting radius. [openmelt/accel_handler.cpp](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/accel_handler.cpp), [openmelt/melty_config.h](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/melty_config.h), [readme.md](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed in get_rotation_interval_ms: RPM=sqrt(abs(g−zero)×89445/effective_radius_cm), then period=60,000/RPM ms. Steering changes effective radius. I2C is configured at 400 kHz; no explicit additional digital noise filter or fixed measured loop frequency was found in the inspected accel/spin files. [openmelt/accel_handler.cpp](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/accel_handler.cpp), [openmelt/spin_control.cpp](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/spin_control.cpp).

7. **Drift and correction.** Confirmed/reported: radius/zero-offset setup corrects speed tracking; RC left/right trim adjusts heading by changing the estimated period. LED phase has an independent stored offset. Automatic absolute-heading recovery and quantified drift tests for this fork: not found. [openmelt/spin_control.cpp](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/spin_control.cpp), [readme.md](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md).

8. **Translation timing, phase width and stick mapping.** Confirmed in code: motor-on duration is throttle fraction of the estimated revolution in default BINARY_THROTTLE. Motor windows are centered half a turn apart; forward/back swaps them and neutral alternates to cancel drift. Below 400 RPM the code requests full-rotation power. Dynamic-PWM mode can fix on-duration at 50%, but configuration selection must be checked separately. [openmelt/spin_control.cpp](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/spin_control.cpp), [openmelt/melty_config.h](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/melty_config.h).

9. **Heading LED/display.** Confirmed/reported: once-per-turn beacon centered on a stored 0–99% offset, width follows throttle and is clamped to 10–90% of a turn; shimmer indicates low battery or calibration adjustment. README discusses shell occlusion at shallow viewing angles. Exact fork LED model and placement: not found. [openmelt/spin_control.cpp](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/spin_control.cpp), [readme.md](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md).

10. **Calibration and persistence.** Reported/confirmed: enter config while stopped by holding back for about 1 s; zero-g is averaged, neutral forward/back permits radius tuning, backward diagonal adjusts LED offset, forward tests movement. Save to EEPROM on exit. Fork-specific calibration measurements: not found. [readme.md](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md), [openmelt/spin_control.cpp](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/spin_control.cpp).

11. **Controls, modes, arming and failsafe.** Confirmed/reported: three interrupt-read RC channels; zero-throttle startup verification and a configured 2 s watchdog. README describes stopping after about 1 s without throttle updates and resuming when signals return. This is source behavior, not an independently exercised failsafe. [openmelt/rc_handler.cpp](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/rc_handler.cpp), [openmelt/melty_config.h](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/melty_config.h), [readme.md](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md).

12. **Distinctive ideas and implementation.** Distinctive inherited design: interactive radius and LED-offset calibration, one/two-wheel timing without a wheel-count setting, and binary/fixed/dynamic-PWM motor modes. Fork-specific work is recorded separately in field 2. [openmelt/spin_control.cpp](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/spin_control.cpp), [openmelt/melty_config.h](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/melty_config.h).

13. **Author-reported problems, failures and evidence limits.** Inherited author reports: some one-wheel builds bounce/oscillate and lose translational control at high speed; a prototype hang/runaway was associated with I2C wiring/library failure, prompting watchdog use. These are upstream reports copied into the README, not validated failures of this fork. [readme.md](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md).

14. **License and reuse notice.** Inherited README states Creative Commons Attribution–NonCommercial–ShareAlike 4.0. A separate license audit of this fork’s additions was not performed. [readme.md](https://github.com/teamhappybots/openmelt2/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md).

<a id="p105"></a>

## P105. lobonz/openmelt2-ESP32

1. **Identity, authorship, URLs and visible dates.** Repository owner: lobonz. Inspected latest default-branch commit credited to Mitch Hughes. Repository created 2025-04-04T21:27:27Z (UTC). Inspected commit 806996c3d3dea098d7f285a33e45128a01e63dbc dated 2025-11-08T03:23:02Z (UTC). GitHub identifies parent nothinglabs/openmelt2. [repository metadata](https://api.github.com/repos/lobonz/openmelt2-ESP32); [inspected commit](https://github.com/lobonz/openmelt2-ESP32/commit/806996c3d3dea098d7f285a33e45128a01e63dbc).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [openmelt/accel_handler.cpp](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/openmelt/accel_handler.cpp), [openmelt/spin_control.cpp](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/openmelt/spin_control.cpp), [openmelt/melty_config.h](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/openmelt/melty_config.h), [openmelt/rc_handler.cpp](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/openmelt/rc_handler.cpp), [openmelt/motor_driver.cpp](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/openmelt/motor_driver.cpp), [openmelt/README.md](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/openmelt/README.md), [openmelt/NOISE.md](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/openmelt/NOISE.md), [readme.md](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/readme.md). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: ahead, 36 commit(s) ahead and 0 behind at inspection. Changed-file scope includes `m5_stamp_s3_reference/M5StampS3-1.27.webp`, `m5_stamp_s3_reference/StampS3Footprint.png`, `m5_stamp_s3_reference/StampS3_127_Pinout.png`, `openmelt/.cursor/rules/stamps3.mdc`, `openmelt/NOISE.md`, `openmelt/README.md`, `openmelt/accel_handler.cpp`, `openmelt/accel_handler.h`, `openmelt/battery_monitor.cpp`, `openmelt/config_storage.cpp`, `openmelt/config_storage.h`, `openmelt/debug_handler.cpp` and additional files. Detailed findings below describe the inspected subset; the entire changed tree was not audited. [upstream comparison](https://api.github.com/repos/nothinglabs/openmelt2/compare/main...lobonz:main).

3. **Robot context and reported status.** Reported status: work-in-progress Open Melt port for M5 Stamp S3/ESP32, with web diagnostics and conventional driving. README’s inherited upstream RPM demonstrations do not verify this port’s performance. Robot weight/actual competition outcome: not found. [readme.md](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/readme.md), [openmelt/README.md](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/openmelt/README.md).

4. **Hardware and exact parts.** Reported as tested in fork-specific README: M5Stack Stamp S3, H3LIS331DL, standard RC receiver and standard PWM ESCs. Confirmed settings put SDA/SCL on GPIO13/15, motors GPIO9/10, battery ADC14 and heading LED7. Exact motor/ESC/receiver/battery model: not found. [openmelt/README.md](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/openmelt/README.md), [openmelt/melty_config.h](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/openmelt/melty_config.h).

5. **Heading sensing and mounting.** Confirmed: LIS331 X axis through I2C at 400 kHz. Effective-radius default is 10.0 cm and zero-g default 1.5 g; both can be calibrated. Actual measured mount and orientation drawing: not found in the inspected material. [openmelt/accel_handler.cpp](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/openmelt/accel_handler.cpp), [openmelt/melty_config.h](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/openmelt/melty_config.h).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed: inherited sqrt(abs(g−zero)×89445/effective_radius_cm) speed model and estimated rotation period; this source adds debug output and ESP32 pin initialization. Fixed measured sample/control rates or an added temporal acceleration filter: not found in the inspected path. [openmelt/spin_control.cpp](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/openmelt/spin_control.cpp), [openmelt/accel_handler.cpp](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/openmelt/accel_handler.cpp).

7. **Drift and correction.** Confirmed/reported: radius/zero-offset setup corrects speed tracking; RC left/right trim adjusts heading by changing the estimated period. LED phase has an independent stored offset. Automatic absolute-heading recovery and quantified drift tests for this fork: not found. [openmelt/spin_control.cpp](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/openmelt/spin_control.cpp), [readme.md](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/readme.md).

8. **Translation timing, phase width and stick mapping.** Confirmed: estimated-turn motor windows still provide translation; motor driver adds SERVO_PWM_THROTTLE, writing 1000–2000 µs-style commands centered at 1500 µs, with normal two-wheel/arcade behavior at zero spin throttle and translation-aware spin scaling. Exact achieved ESC refresh/phase accuracy was not tested here. [openmelt/spin_control.cpp](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/openmelt/spin_control.cpp), [openmelt/motor_driver.cpp](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/openmelt/motor_driver.cpp), [openmelt/README.md](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/openmelt/README.md).

9. **Heading LED/display.** Confirmed/reported: once-per-turn beacon centered on a stored 0–99% offset, width follows throttle and is clamped to 10–90% of a turn; shimmer indicates low battery or calibration adjustment. README discusses shell occlusion at shallow viewing angles. Exact fork LED model and placement: not found. [openmelt/spin_control.cpp](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/openmelt/spin_control.cpp), [readme.md](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/readme.md).

10. **Calibration and persistence.** Reported: interactive stopped/back-stick config for radius/heading plus persistent user settings; latest commit says configuration moved to web UI. Fork README describes Hammertime_AP diagnostics. The actual web endpoint code was not read, so complete endpoint semantics and successful save tests are not established. [openmelt/README.md](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/openmelt/README.md), [inspected commit](https://github.com/lobonz/openmelt2-ESP32/commit/806996c3d3dea098d7f285a33e45128a01e63dbc).

11. **Controls, modes, arming and failsafe.** Confirmed: standard PWM RC input is interrupt-captured; throttle adds a center deadband at 1450–1550 µs and normal driving when not spinning. Inherited watchdog/boot/freshness intentions are present; ESP32 safety behavior was not independently exercised. [openmelt/rc_handler.cpp](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/openmelt/rc_handler.cpp), [openmelt/melty_config.h](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/openmelt/melty_config.h), [openmelt/README.md](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/openmelt/README.md).

12. **Distinctive ideas and implementation.** Inspected additions: Stamp S3 pin assignments, servo-PWM ESC support, diagnostics and a fork-specific setup guide. Root README says bundled SparkFun LIS331 enum OPEN_DRAIN was renamed OPEN_DRAIN_MODE to avoid an M5 library collision. This is a reported source-level compatibility change. [openmelt/melty_config.h](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/openmelt/melty_config.h), [openmelt/motor_driver.cpp](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/openmelt/motor_driver.cpp), [openmelt/README.md](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/openmelt/README.md), [readme.md](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/readme.md).

13. **Author-reported problems, failures and evidence limits.** Reported issues: enum-name collision with M5 libraries; NOISE.md proposes capacitors, signal/ground wiring and supply-noise remedies. That file provides suggestions, not confirmed fixes or evidence that any was installed. Full working melty/arena test results: not found. [readme.md](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/readme.md), [openmelt/NOISE.md](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/openmelt/NOISE.md).

14. **License and reuse notice.** Inherited README states Creative Commons Attribution–NonCommercial–ShareAlike 4.0. A separate license audit of this fork’s additions was not performed. [readme.md](https://github.com/lobonz/openmelt2-ESP32/blob/806996c3d3dea098d7f285a33e45128a01e63dbc/readme.md).

<a id="p106"></a>

## P106. gmazin/openmelt2-custom

1. **Identity, authorship, URLs and visible dates.** Repository owner: gmazin. Inspected latest default-branch commit credited to Georgiy Mazin. Repository created 2026-06-24T05:51:39Z (UTC). Inspected commit 6962bb6441e6feff72df4fbb1a4f8922c57c9b48 dated 2026-08-12T02:24:35Z (UTC). GitHub identifies parent nothinglabs/openmelt2. [repository metadata](https://api.github.com/repos/gmazin/openmelt2-custom); [inspected commit](https://github.com/gmazin/openmelt2-custom/commit/6962bb6441e6feff72df4fbb1a4f8922c57c9b48).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [openmelt/accel_handler.cpp](https://github.com/gmazin/openmelt2-custom/blob/6962bb6441e6feff72df4fbb1a4f8922c57c9b48/openmelt/accel_handler.cpp), [openmelt/spin_control.cpp](https://github.com/gmazin/openmelt2-custom/blob/6962bb6441e6feff72df4fbb1a4f8922c57c9b48/openmelt/spin_control.cpp), [openmelt/melty_config.h](https://github.com/gmazin/openmelt2-custom/blob/6962bb6441e6feff72df4fbb1a4f8922c57c9b48/openmelt/melty_config.h), [openmelt/rc_handler.cpp](https://github.com/gmazin/openmelt2-custom/blob/6962bb6441e6feff72df4fbb1a4f8922c57c9b48/openmelt/rc_handler.cpp), [openmelt/motor_driver.cpp](https://github.com/gmazin/openmelt2-custom/blob/6962bb6441e6feff72df4fbb1a4f8922c57c9b48/openmelt/motor_driver.cpp), [openmelt_pico/openmelt_pico.ino](https://github.com/gmazin/openmelt2-custom/blob/6962bb6441e6feff72df4fbb1a4f8922c57c9b48/openmelt_pico/openmelt_pico.ino), [readme.md](https://github.com/gmazin/openmelt2-custom/blob/6962bb6441e6feff72df4fbb1a4f8922c57c9b48/readme.md). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: ahead, 2 commit(s) ahead and 0 behind at inspection. Changed-file scope includes `openmelt_pico/openmelt_pico.ino`. Detailed findings below describe the inspected subset; the entire changed tree was not audited. [upstream comparison](https://api.github.com/repos/nothinglabs/openmelt2/compare/main...gmazin:main).

3. **Robot context and reported status.** Confirmed source contains a single-file Pico/Pico 2 port alongside the unchanged Arduino controller. Comments identify Raspberry Pi Pico 2 W board wiring; exact robot name/weight and combat results: not found. Latest commit reports an arduino-cli compile, not a hardware driving validation. [openmelt_pico/openmelt_pico.ino](https://github.com/gmazin/openmelt2-custom/blob/6962bb6441e6feff72df4fbb1a4f8922c57c9b48/openmelt_pico/openmelt_pico.ino), [inspected commit](https://github.com/gmazin/openmelt2-custom/commit/6962bb6441e6feff72df4fbb1a4f8922c57c9b48).

4. **Hardware and exact parts.** Confirmed source: Pico/RP2040/RP2350, two SPI H3LIS331DL sensors, CRSF through AlfredoCRSF at 420000 baud, PIO_DShot at DShot600, two eight-NeoPixel sticks, 3.3 V/12-bit ADC and flash-backed EEPROM. Exact motors/ESC/radio/battery model: not found. Motor GP14/15 are explicitly guesses pending final board assignments. [openmelt_pico/openmelt_pico.ino](https://github.com/gmazin/openmelt2-custom/blob/6962bb6441e6feff72df4fbb1a4f8922c57c9b48/openmelt_pico/openmelt_pico.ino).

5. **Heading sensing and mounting.** Reported configured geometry: opposing accelerometers at 0.75 inch = 1.905 cm from spin axis. Each X reading is converted to absolute g; dual magnitudes are averaged. Code uses a present sensor alone, the lower reading for disagreement >40 g, or zero if neither is present. This is code behavior; cancellation/noise improvement is an author rationale, not measured here. [openmelt_pico/openmelt_pico.ino](https://github.com/gmazin/openmelt2-custom/blob/6962bb6441e6feff72df4fbb1a4f8922c57c9b48/openmelt_pico/openmelt_pico.ino).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed: direct register SPI at 8 MHz, WHO_AM_I probe, configured 1 kHz/±400 g. RPM=sqrt(abs(averaged_g−zero)×89445/effective_radius_cm), floored at 1 RPM. DShot service period is 200 µs (configured 5 kHz); source estimates about 4.8° command spacing at 4000 RPM. Effective update rates were not measured here. [openmelt_pico/openmelt_pico.ino](https://github.com/gmazin/openmelt2-custom/blob/6962bb6441e6feff72df4fbb1a4f8922c57c9b48/openmelt_pico/openmelt_pico.ino).

7. **Drift and correction.** Confirmed: effective-radius calibration, relative phase steering and separate LED offset remain. Dual-sensor averaging is intended to suppress translation contamination; the author’s stronger noise-cancellation claims have no supplied quantitative hardware verification in the material inspected. [openmelt_pico/openmelt_pico.ino](https://github.com/gmazin/openmelt2-custom/blob/6962bb6441e6feff72df4fbb1a4f8922c57c9b48/openmelt_pico/openmelt_pico.ino), [inspected commit](https://github.com/gmazin/openmelt2-custom/commit/6962bb6441e6feff72df4fbb1a4f8922c57c9b48).

8. **Translation timing, phase width and stick mapping.** Confirmed: port preserves Open Melt angular motor-on/coast phases centered 180° apart, forward/back swap and neutral alternation; binary phase requests are converted into configured DShot throttle. Below 400 RPM it selects full-power spin-up. PIO transport uses configured per-motor reversal and minimum/maximum throttle. [openmelt_pico/openmelt_pico.ino](https://github.com/gmazin/openmelt2-custom/blob/6962bb6441e6feff72df4fbb1a4f8922c57c9b48/openmelt_pico/openmelt_pico.ino).

9. **Heading LED/display.** Confirmed: NeoPixel sticks on GP2/3, eight LEDs each, brightness 120 and shimmer 35. Writes are gated on color changes to reduce blocking; onboard Pico 2 W LED is deliberately unused because of CYW43 SPI overhead. Actual viewing tests and measured latency: not found. [openmelt_pico/openmelt_pico.ino](https://github.com/gmazin/openmelt2-custom/blob/6962bb6441e6feff72df4fbb1a4f8922c57c9b48/openmelt_pico/openmelt_pico.ino).

10. **Calibration and persistence.** Confirmed: stopped config samples zero g, adjusts effective radius/beacon alignment, then commits flash-backed EEPROM; sentinel=44 invalidates prior single-sensor offsets. Actual successful calibration at operating RPM: not found. [openmelt_pico/openmelt_pico.ino](https://github.com/gmazin/openmelt2-custom/blob/6962bb6441e6feff72df4fbb1a4f8922c57c9b48/openmelt_pico/openmelt_pico.ino).

11. **Controls, modes, arming and failsafe.** Confirmed: CRSF on UART0 GP0/1, RC freshness limit 250 ms, zero-throttle boot gate, hardware watchdog 2 s and 3 s DShot arming zeros. Source explicitly notes ESCs arm on power-up and motor pins are placeholders. No end-to-end failsafe test is supplied. [openmelt_pico/openmelt_pico.ino](https://github.com/gmazin/openmelt2-custom/blob/6962bb6441e6feff72df4fbb1a4f8922c57c9b48/openmelt_pico/openmelt_pico.ino).

12. **Distinctive ideas and implementation.** Inspected additions: single-file Pico port, dual independent SPI buses, direct register driver replacing global-SPI LIS331 library, CRSF input, PIO DShot, change-gated dual NeoPixels and flash configuration. Compile verification is reported for rp2040:rp2040:rpipico2w; this survey did not rerun it. [openmelt_pico/openmelt_pico.ino](https://github.com/gmazin/openmelt2-custom/blob/6962bb6441e6feff72df4fbb1a4f8922c57c9b48/openmelt_pico/openmelt_pico.ino), [inspected commit](https://github.com/gmazin/openmelt2-custom/commit/6962bb6441e6feff72df4fbb1a4f8922c57c9b48).

13. **Author-reported problems, failures and evidence limits.** Author-reported integration constraints: bundled LIS331 library hardcodes global SPI; NeoPixel writes cost time; onboard LED access can block; prior saved zero offset is incompatible with averaged sensor data. Motor signals remain unassigned in schematic per the source comment. Real combat failures or measured hardware validation: not found. [openmelt_pico/openmelt_pico.ino](https://github.com/gmazin/openmelt2-custom/blob/6962bb6441e6feff72df4fbb1a4f8922c57c9b48/openmelt_pico/openmelt_pico.ino), [inspected commit](https://github.com/gmazin/openmelt2-custom/commit/6962bb6441e6feff72df4fbb1a4f8922c57c9b48).

14. **License and reuse notice.** Inherited README states Creative Commons Attribution–NonCommercial–ShareAlike 4.0. A separate license audit of this fork’s additions was not performed. [readme.md](https://github.com/gmazin/openmelt2-custom/blob/6962bb6441e6feff72df4fbb1a4f8922c57c9b48/readme.md).

<a id="p107"></a>

## P107. Cschlaefli/openmelt2

1. **Identity, authorship, URLs and visible dates.** Repository owner: Cschlaefli. Inspected latest default-branch commit credited to Cade Schlaefli. Repository created 2026-02-24T22:26:33Z (UTC). Inspected commit 91cffd517974014ff79e7bd264a03c8a411670b4 dated 2026-02-25T01:44:40Z (UTC). GitHub identifies parent nothinglabs/openmelt2. [repository metadata](https://api.github.com/repos/Cschlaefli/openmelt2); [inspected commit](https://github.com/Cschlaefli/openmelt2/commit/91cffd517974014ff79e7bd264a03c8a411670b4).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [openmelt/accel_handler.cpp](https://github.com/Cschlaefli/openmelt2/blob/91cffd517974014ff79e7bd264a03c8a411670b4/openmelt/accel_handler.cpp), [openmelt/spin_control.cpp](https://github.com/Cschlaefli/openmelt2/blob/91cffd517974014ff79e7bd264a03c8a411670b4/openmelt/spin_control.cpp), [openmelt/melty_config.h](https://github.com/Cschlaefli/openmelt2/blob/91cffd517974014ff79e7bd264a03c8a411670b4/openmelt/melty_config.h), [openmelt/rc_handler.cpp](https://github.com/Cschlaefli/openmelt2/blob/91cffd517974014ff79e7bd264a03c8a411670b4/openmelt/rc_handler.cpp), [openmelt/motor_driver.cpp](https://github.com/Cschlaefli/openmelt2/blob/91cffd517974014ff79e7bd264a03c8a411670b4/openmelt/motor_driver.cpp), [readme.md](https://github.com/Cschlaefli/openmelt2/blob/91cffd517974014ff79e7bd264a03c8a411670b4/readme.md). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: ahead, 1 commit(s) ahead and 0 behind at inspection. Changed-file scope includes `.devcontainer/Containerfile`, `.devcontainer/devcontainer.json`. Detailed findings below describe the inspected subset; the entire changed tree was not audited. [upstream comparison](https://api.github.com/repos/nothinglabs/openmelt2/compare/main...Cschlaefli:main).

3. **Robot context and reported status.** Reported in inherited README: Open Melt 2 is an Arduino translational-drift controller for one or two drive motors, with an antweight reference platform. The inherited 3200 RPM testing claim belongs to the upstream project, not an independently verified build of this fork. A separate fork robot and event record: not found. [readme.md](https://github.com/Cschlaefli/openmelt2/blob/91cffd517974014ff79e7bd264a03c8a411670b4/readme.md).

4. **Hardware and exact parts.** Reported inherited hardware: Arduino Micro/ATmega32u4 5 V 16 MHz; H3LIS331DL, preferably Adafruit breakout; optional SparkFun breakout plus level converter; hobby RC receiver, heading LED and motor driver(s). Reference motor switching uses RFP30N06LE; SimonK Hobbypower 30 A support is reported. Exact hardware built by this fork owner: not found. [readme.md](https://github.com/Cschlaefli/openmelt2/blob/91cffd517974014ff79e7bd264a03c8a411670b4/readme.md).

5. **Heading sensing and mounting.** Confirmed in code: X-axis LIS331 acceleration through I2C; default effective radius 3.9 cm. README describes interactive orientation/radius compensation and respecting 400 g full-scale loading. The number is a software default, not a measured fork mounting radius. [openmelt/accel_handler.cpp](https://github.com/Cschlaefli/openmelt2/blob/91cffd517974014ff79e7bd264a03c8a411670b4/openmelt/accel_handler.cpp), [openmelt/melty_config.h](https://github.com/Cschlaefli/openmelt2/blob/91cffd517974014ff79e7bd264a03c8a411670b4/openmelt/melty_config.h), [readme.md](https://github.com/Cschlaefli/openmelt2/blob/91cffd517974014ff79e7bd264a03c8a411670b4/readme.md).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed in get_rotation_interval_ms: RPM=sqrt(abs(g−zero)×89445/effective_radius_cm), then period=60,000/RPM ms. Steering changes effective radius. I2C is configured at 400 kHz; no explicit additional digital noise filter or fixed measured loop frequency was found in the inspected accel/spin files. [openmelt/accel_handler.cpp](https://github.com/Cschlaefli/openmelt2/blob/91cffd517974014ff79e7bd264a03c8a411670b4/openmelt/accel_handler.cpp), [openmelt/spin_control.cpp](https://github.com/Cschlaefli/openmelt2/blob/91cffd517974014ff79e7bd264a03c8a411670b4/openmelt/spin_control.cpp).

7. **Drift and correction.** Confirmed/reported: radius/zero-offset setup corrects speed tracking; RC left/right trim adjusts heading by changing the estimated period. LED phase has an independent stored offset. Automatic absolute-heading recovery and quantified drift tests for this fork: not found. [openmelt/spin_control.cpp](https://github.com/Cschlaefli/openmelt2/blob/91cffd517974014ff79e7bd264a03c8a411670b4/openmelt/spin_control.cpp), [readme.md](https://github.com/Cschlaefli/openmelt2/blob/91cffd517974014ff79e7bd264a03c8a411670b4/readme.md).

8. **Translation timing, phase width and stick mapping.** Confirmed in code: motor-on duration is throttle fraction of the estimated revolution in default BINARY_THROTTLE. Motor windows are centered half a turn apart; forward/back swaps them and neutral alternates to cancel drift. Below 400 RPM the code requests full-rotation power. Dynamic-PWM mode can fix on-duration at 50%, but configuration selection must be checked separately. [openmelt/spin_control.cpp](https://github.com/Cschlaefli/openmelt2/blob/91cffd517974014ff79e7bd264a03c8a411670b4/openmelt/spin_control.cpp), [openmelt/melty_config.h](https://github.com/Cschlaefli/openmelt2/blob/91cffd517974014ff79e7bd264a03c8a411670b4/openmelt/melty_config.h).

9. **Heading LED/display.** Confirmed/reported: once-per-turn beacon centered on a stored 0–99% offset, width follows throttle and is clamped to 10–90% of a turn; shimmer indicates low battery or calibration adjustment. README discusses shell occlusion at shallow viewing angles. Exact fork LED model and placement: not found. [openmelt/spin_control.cpp](https://github.com/Cschlaefli/openmelt2/blob/91cffd517974014ff79e7bd264a03c8a411670b4/openmelt/spin_control.cpp), [readme.md](https://github.com/Cschlaefli/openmelt2/blob/91cffd517974014ff79e7bd264a03c8a411670b4/readme.md).

10. **Calibration and persistence.** Reported/confirmed: enter config while stopped by holding back for about 1 s; zero-g is averaged, neutral forward/back permits radius tuning, backward diagonal adjusts LED offset, forward tests movement. Save to EEPROM on exit. Fork-specific calibration measurements: not found. [readme.md](https://github.com/Cschlaefli/openmelt2/blob/91cffd517974014ff79e7bd264a03c8a411670b4/readme.md), [openmelt/spin_control.cpp](https://github.com/Cschlaefli/openmelt2/blob/91cffd517974014ff79e7bd264a03c8a411670b4/openmelt/spin_control.cpp).

11. **Controls, modes, arming and failsafe.** Confirmed/reported: three interrupt-read RC channels; zero-throttle startup verification and a configured 2 s watchdog. README describes stopping after about 1 s without throttle updates and resuming when signals return. This is source behavior, not an independently exercised failsafe. [openmelt/rc_handler.cpp](https://github.com/Cschlaefli/openmelt2/blob/91cffd517974014ff79e7bd264a03c8a411670b4/openmelt/rc_handler.cpp), [openmelt/melty_config.h](https://github.com/Cschlaefli/openmelt2/blob/91cffd517974014ff79e7bd264a03c8a411670b4/openmelt/melty_config.h), [readme.md](https://github.com/Cschlaefli/openmelt2/blob/91cffd517974014ff79e7bd264a03c8a411670b4/readme.md).

12. **Distinctive ideas and implementation.** Inspected change evidence: upstream comparison lists only .devcontainer/Containerfile and .devcontainer/devcontainer.json; latest commit describes setup for an ESP32 conversion. The inspected default-branch firmware remains the Arduino implementation. A completed ESP32 port or hardware validation is not established. [upstream comparison](https://api.github.com/repos/nothinglabs/openmelt2/compare/main...Cschlaefli:main), [inspected commit](https://github.com/Cschlaefli/openmelt2/commit/91cffd517974014ff79e7bd264a03c8a411670b4), [openmelt/melty_config.h](https://github.com/Cschlaefli/openmelt2/blob/91cffd517974014ff79e7bd264a03c8a411670b4/openmelt/melty_config.h).

13. **Author-reported problems, failures and evidence limits.** Inherited author reports: some one-wheel builds bounce/oscillate and lose translational control at high speed; a prototype hang/runaway was associated with I2C wiring/library failure, prompting watchdog use. These are upstream reports copied into the README, not validated failures of this fork. [readme.md](https://github.com/Cschlaefli/openmelt2/blob/91cffd517974014ff79e7bd264a03c8a411670b4/readme.md).

14. **License and reuse notice.** Inherited README states Creative Commons Attribution–NonCommercial–ShareAlike 4.0. A separate license audit of this fork’s additions was not performed. [readme.md](https://github.com/Cschlaefli/openmelt2/blob/91cffd517974014ff79e7bd264a03c8a411670b4/readme.md).

<a id="p108"></a>

## P108. DiracDesigns/openmelt2

1. **Identity, authorship, URLs and visible dates.** Repository owner: DiracDesigns. Inspected latest default-branch commit credited to DiracDesigns. Repository created 2025-05-16T15:33:40Z (UTC). Inspected commit 8b770ab5831ba7a85f10550e29492beded6e8a6f dated 2025-05-16T15:36:45Z (UTC). GitHub identifies parent nothinglabs/openmelt2. [repository metadata](https://api.github.com/repos/DiracDesigns/openmelt2); [inspected commit](https://github.com/DiracDesigns/openmelt2/commit/8b770ab5831ba7a85f10550e29492beded6e8a6f).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [openmelt/accel_handler.cpp](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/openmelt/accel_handler.cpp), [openmelt/spin_control.cpp](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/openmelt/spin_control.cpp), [openmelt/melty_config.h](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/openmelt/melty_config.h), [openmelt/rc_handler.cpp](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/openmelt/rc_handler.cpp), [openmelt/motor_driver.cpp](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/openmelt/motor_driver.cpp), [readme.md](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/readme.md). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: ahead, 2 commit(s) ahead and 0 behind at inspection. Changed-file scope includes `openmelt/melty_config.h`, `openmelt/motor_driver.cpp`, `openmelt/openmelt.ino`. Detailed findings below describe the inspected subset; the entire changed tree was not audited. [upstream comparison](https://api.github.com/repos/nothinglabs/openmelt2/compare/main...DiracDesigns:main).

3. **Robot context and reported status.** Reported in inherited README: Open Melt 2 is an Arduino translational-drift controller for one or two drive motors, with an antweight reference platform. The inherited 3200 RPM testing claim belongs to the upstream project, not an independently verified build of this fork. A separate fork robot and event record: not found. [readme.md](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/readme.md).

4. **Hardware and exact parts.** Reported inherited hardware: Arduino Micro/ATmega32u4 5 V 16 MHz; H3LIS331DL, preferably Adafruit breakout; optional SparkFun breakout plus level converter; hobby RC receiver, heading LED and motor driver(s). Reference motor switching uses RFP30N06LE; SimonK Hobbypower 30 A support is reported. Exact hardware built by this fork owner: not found. [readme.md](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/readme.md).

5. **Heading sensing and mounting.** Confirmed in code: X-axis LIS331 acceleration through I2C; default effective radius 3.9 cm. README describes interactive orientation/radius compensation and respecting 400 g full-scale loading. The number is a software default, not a measured fork mounting radius. [openmelt/accel_handler.cpp](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/openmelt/accel_handler.cpp), [openmelt/melty_config.h](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/openmelt/melty_config.h), [readme.md](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/readme.md).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed in get_rotation_interval_ms: RPM=sqrt(abs(g−zero)×89445/effective_radius_cm), then period=60,000/RPM ms. Steering changes effective radius. I2C is configured at 400 kHz; no explicit additional digital noise filter or fixed measured loop frequency was found in the inspected accel/spin files. [openmelt/accel_handler.cpp](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/openmelt/accel_handler.cpp), [openmelt/spin_control.cpp](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/openmelt/spin_control.cpp).

7. **Drift and correction.** Confirmed/reported: radius/zero-offset setup corrects speed tracking; RC left/right trim adjusts heading by changing the estimated period. LED phase has an independent stored offset. Automatic absolute-heading recovery and quantified drift tests for this fork: not found. [openmelt/spin_control.cpp](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/openmelt/spin_control.cpp), [readme.md](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/readme.md).

8. **Translation timing, phase width and stick mapping.** Confirmed in code: motor-on duration is throttle fraction of the estimated revolution in default BINARY_THROTTLE. Motor windows are centered half a turn apart; forward/back swaps them and neutral alternates to cancel drift. Below 400 RPM the code requests full-rotation power. Dynamic-PWM mode can fix on-duration at 50%, but configuration selection must be checked separately. [openmelt/spin_control.cpp](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/openmelt/spin_control.cpp), [openmelt/melty_config.h](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/openmelt/melty_config.h).

9. **Heading LED/display.** Confirmed/reported: once-per-turn beacon centered on a stored 0–99% offset, width follows throttle and is clamped to 10–90% of a turn; shimmer indicates low battery or calibration adjustment. README discusses shell occlusion at shallow viewing angles. Exact fork LED model and placement: not found. [openmelt/spin_control.cpp](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/openmelt/spin_control.cpp), [readme.md](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/readme.md).

10. **Calibration and persistence.** Reported/confirmed: enter config while stopped by holding back for about 1 s; zero-g is averaged, neutral forward/back permits radius tuning, backward diagonal adjusts LED offset, forward tests movement. Save to EEPROM on exit. Fork-specific calibration measurements: not found. [readme.md](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/readme.md), [openmelt/spin_control.cpp](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/openmelt/spin_control.cpp).

11. **Controls, modes, arming and failsafe.** Confirmed/reported: three interrupt-read RC channels; zero-throttle startup verification and a configured 2 s watchdog. README describes stopping after about 1 s without throttle updates and resuming when signals return. This is source behavior, not an independently exercised failsafe. [openmelt/rc_handler.cpp](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/openmelt/rc_handler.cpp), [openmelt/melty_config.h](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/openmelt/melty_config.h), [readme.md](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/readme.md).

12. **Distinctive ideas and implementation.** Inspected additions: Brushless_Fixed_PWM_Throttle enum/Servo motor-driver branch and related initialization changes. melty_config.h still selects BINARY_THROTTLE in this snapshot, so the new branch is not the active default configuration. [openmelt/melty_config.h](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/openmelt/melty_config.h), [openmelt/motor_driver.cpp](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/openmelt/motor_driver.cpp), [upstream comparison](https://api.github.com/repos/nothinglabs/openmelt2/compare/main...DiracDesigns:main).

13. **Author-reported problems, failures and evidence limits.** Fork author’s failure log: not found. Untested static observation: added brushless motor branches contain assignment tests such as if(motor_pin = MOTOR_PIN1), and motor_off repeats MOTOR_PIN1. These source concerns do not constitute a reproduced hardware failure. Inherited README issues remain upstream reports. [openmelt/motor_driver.cpp](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/openmelt/motor_driver.cpp), [readme.md](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/readme.md).

14. **License and reuse notice.** Inherited README states Creative Commons Attribution–NonCommercial–ShareAlike 4.0. A separate license audit of this fork’s additions was not performed. [readme.md](https://github.com/DiracDesigns/openmelt2/blob/8b770ab5831ba7a85f10550e29492beded6e8a6f/readme.md).

<a id="p109"></a>

## P109. acklenx/openmelt2

1. **Identity, authorship, URLs and visible dates.** Repository owner: acklenx. Inspected latest default-branch commit credited to Rich Olson / nothinglabs.com. Repository created 2024-09-06T01:12:15Z (UTC). Inspected commit 867b3199055e8908933d619f6437f22d5fb0276e dated 2024-03-13T20:48:46Z (UTC). GitHub identifies parent nothinglabs/openmelt2. [repository metadata](https://api.github.com/repos/acklenx/openmelt2); [inspected commit](https://github.com/acklenx/openmelt2/commit/867b3199055e8908933d619f6437f22d5fb0276e).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [openmelt/accel_handler.cpp](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/accel_handler.cpp), [openmelt/spin_control.cpp](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/spin_control.cpp), [openmelt/melty_config.h](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/melty_config.h), [openmelt/rc_handler.cpp](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/rc_handler.cpp), [openmelt/motor_driver.cpp](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/motor_driver.cpp), [readme.md](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/readme.md). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: behind, 0 commit(s) ahead and 2 behind at inspection. No fork-specific commits appear in that comparison; no new fork implementation is inferred. [upstream comparison](https://api.github.com/repos/nothinglabs/openmelt2/compare/main...acklenx:main).

3. **Robot context and reported status.** Reported in inherited README: Open Melt 2 is an Arduino translational-drift controller for one or two drive motors, with an antweight reference platform. The inherited 3200 RPM testing claim belongs to the upstream project, not an independently verified build of this fork. A separate fork robot and event record: not found. [readme.md](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/readme.md).

4. **Hardware and exact parts.** Reported inherited hardware: Arduino Micro/ATmega32u4 5 V 16 MHz; H3LIS331DL, preferably Adafruit breakout; optional SparkFun breakout plus level converter; hobby RC receiver, heading LED and motor driver(s). Reference motor switching uses RFP30N06LE; SimonK Hobbypower 30 A support is reported. Exact hardware built by this fork owner: not found. [readme.md](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/readme.md).

5. **Heading sensing and mounting.** Confirmed in code: X-axis LIS331 acceleration through I2C; default effective radius 3.9 cm. README describes interactive orientation/radius compensation and respecting 400 g full-scale loading. The number is a software default, not a measured fork mounting radius. [openmelt/accel_handler.cpp](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/accel_handler.cpp), [openmelt/melty_config.h](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/melty_config.h), [readme.md](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/readme.md).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed in get_rotation_interval_ms: RPM=sqrt(abs(g−zero)×89445/effective_radius_cm), then period=60,000/RPM ms. Steering changes effective radius. I2C is configured at 400 kHz; no explicit additional digital noise filter or fixed measured loop frequency was found in the inspected accel/spin files. [openmelt/accel_handler.cpp](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/accel_handler.cpp), [openmelt/spin_control.cpp](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/spin_control.cpp).

7. **Drift and correction.** Confirmed/reported: radius/zero-offset setup corrects speed tracking; RC left/right trim adjusts heading by changing the estimated period. LED phase has an independent stored offset. Automatic absolute-heading recovery and quantified drift tests for this fork: not found. [openmelt/spin_control.cpp](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/spin_control.cpp), [readme.md](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/readme.md).

8. **Translation timing, phase width and stick mapping.** Confirmed in code: motor-on duration is throttle fraction of the estimated revolution in default BINARY_THROTTLE. Motor windows are centered half a turn apart; forward/back swaps them and neutral alternates to cancel drift. Below 400 RPM the code requests full-rotation power. Dynamic-PWM mode can fix on-duration at 50%, but configuration selection must be checked separately. [openmelt/spin_control.cpp](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/spin_control.cpp), [openmelt/melty_config.h](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/melty_config.h).

9. **Heading LED/display.** Confirmed/reported: once-per-turn beacon centered on a stored 0–99% offset, width follows throttle and is clamped to 10–90% of a turn; shimmer indicates low battery or calibration adjustment. README discusses shell occlusion at shallow viewing angles. Exact fork LED model and placement: not found. [openmelt/spin_control.cpp](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/spin_control.cpp), [readme.md](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/readme.md).

10. **Calibration and persistence.** Reported/confirmed: enter config while stopped by holding back for about 1 s; zero-g is averaged, neutral forward/back permits radius tuning, backward diagonal adjusts LED offset, forward tests movement. Save to EEPROM on exit. Fork-specific calibration measurements: not found. [readme.md](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/readme.md), [openmelt/spin_control.cpp](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/spin_control.cpp).

11. **Controls, modes, arming and failsafe.** Confirmed/reported: three interrupt-read RC channels; zero-throttle startup verification and a configured 2 s watchdog. README describes stopping after about 1 s without throttle updates and resuming when signals return. This is source behavior, not an independently exercised failsafe. [openmelt/rc_handler.cpp](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/rc_handler.cpp), [openmelt/melty_config.h](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/melty_config.h), [readme.md](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/readme.md).

12. **Distinctive ideas and implementation.** Distinctive inherited design: interactive radius and LED-offset calibration, one/two-wheel timing without a wheel-count setting, and binary/fixed/dynamic-PWM motor modes. Fork-specific work is recorded separately in field 2. [openmelt/spin_control.cpp](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/spin_control.cpp), [openmelt/melty_config.h](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/melty_config.h).

13. **Author-reported problems, failures and evidence limits.** Inherited author reports: some one-wheel builds bounce/oscillate and lose translational control at high speed; a prototype hang/runaway was associated with I2C wiring/library failure, prompting watchdog use. These are upstream reports copied into the README, not validated failures of this fork. [readme.md](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/readme.md).

14. **License and reuse notice.** Inherited README states Creative Commons Attribution–NonCommercial–ShareAlike 4.0. A separate license audit of this fork’s additions was not performed. [readme.md](https://github.com/acklenx/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/readme.md).

<a id="p110"></a>

## P110. HelloGuy8000/espmelt

1. **Identity, authorship, URLs and visible dates.** Repository owner: HelloGuy8000. Inspected latest default-branch commit credited to Rich Olson / nothinglabs.com. Repository created 2026-03-24T01:00:11Z (UTC). Inspected commit 7d062906950647350195b2b439e6f40e28492ce7 dated 2025-02-03T04:24:28Z (UTC). GitHub identifies parent nothinglabs/openmelt2. [repository metadata](https://api.github.com/repos/HelloGuy8000/espmelt); [inspected commit](https://github.com/HelloGuy8000/espmelt/commit/7d062906950647350195b2b439e6f40e28492ce7).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [openmelt/accel_handler.cpp](https://github.com/HelloGuy8000/espmelt/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/accel_handler.cpp), [openmelt/spin_control.cpp](https://github.com/HelloGuy8000/espmelt/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/spin_control.cpp), [openmelt/melty_config.h](https://github.com/HelloGuy8000/espmelt/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/melty_config.h), [openmelt/rc_handler.cpp](https://github.com/HelloGuy8000/espmelt/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/rc_handler.cpp), [openmelt/motor_driver.cpp](https://github.com/HelloGuy8000/espmelt/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/motor_driver.cpp), [readme.md](https://github.com/HelloGuy8000/espmelt/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: identical, 0 commit(s) ahead and 0 behind at inspection. No fork-specific commits appear in that comparison; no new fork implementation is inferred. [upstream comparison](https://api.github.com/repos/nothinglabs/openmelt2/compare/main...HelloGuy8000:main).

3. **Robot context and reported status.** Reported in inherited README: Open Melt 2 is an Arduino translational-drift controller for one or two drive motors, with an antweight reference platform. The inherited 3200 RPM testing claim belongs to the upstream project, not an independently verified build of this fork. A separate fork robot and event record: not found. [readme.md](https://github.com/HelloGuy8000/espmelt/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md).

4. **Hardware and exact parts.** Reported inherited hardware: Arduino Micro/ATmega32u4 5 V 16 MHz; H3LIS331DL, preferably Adafruit breakout; optional SparkFun breakout plus level converter; hobby RC receiver, heading LED and motor driver(s). Reference motor switching uses RFP30N06LE; SimonK Hobbypower 30 A support is reported. Exact hardware built by this fork owner: not found. [readme.md](https://github.com/HelloGuy8000/espmelt/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md).

5. **Heading sensing and mounting.** Confirmed in code: X-axis LIS331 acceleration through I2C; default effective radius 3.9 cm. README describes interactive orientation/radius compensation and respecting 400 g full-scale loading. The number is a software default, not a measured fork mounting radius. [openmelt/accel_handler.cpp](https://github.com/HelloGuy8000/espmelt/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/accel_handler.cpp), [openmelt/melty_config.h](https://github.com/HelloGuy8000/espmelt/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/melty_config.h), [readme.md](https://github.com/HelloGuy8000/espmelt/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed in get_rotation_interval_ms: RPM=sqrt(abs(g−zero)×89445/effective_radius_cm), then period=60,000/RPM ms. Steering changes effective radius. I2C is configured at 400 kHz; no explicit additional digital noise filter or fixed measured loop frequency was found in the inspected accel/spin files. [openmelt/accel_handler.cpp](https://github.com/HelloGuy8000/espmelt/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/accel_handler.cpp), [openmelt/spin_control.cpp](https://github.com/HelloGuy8000/espmelt/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/spin_control.cpp).

7. **Drift and correction.** Confirmed/reported: radius/zero-offset setup corrects speed tracking; RC left/right trim adjusts heading by changing the estimated period. LED phase has an independent stored offset. Automatic absolute-heading recovery and quantified drift tests for this fork: not found. [openmelt/spin_control.cpp](https://github.com/HelloGuy8000/espmelt/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/spin_control.cpp), [readme.md](https://github.com/HelloGuy8000/espmelt/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md).

8. **Translation timing, phase width and stick mapping.** Confirmed in code: motor-on duration is throttle fraction of the estimated revolution in default BINARY_THROTTLE. Motor windows are centered half a turn apart; forward/back swaps them and neutral alternates to cancel drift. Below 400 RPM the code requests full-rotation power. Dynamic-PWM mode can fix on-duration at 50%, but configuration selection must be checked separately. [openmelt/spin_control.cpp](https://github.com/HelloGuy8000/espmelt/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/spin_control.cpp), [openmelt/melty_config.h](https://github.com/HelloGuy8000/espmelt/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/melty_config.h).

9. **Heading LED/display.** Confirmed/reported: once-per-turn beacon centered on a stored 0–99% offset, width follows throttle and is clamped to 10–90% of a turn; shimmer indicates low battery or calibration adjustment. README discusses shell occlusion at shallow viewing angles. Exact fork LED model and placement: not found. [openmelt/spin_control.cpp](https://github.com/HelloGuy8000/espmelt/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/spin_control.cpp), [readme.md](https://github.com/HelloGuy8000/espmelt/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md).

10. **Calibration and persistence.** Reported/confirmed: enter config while stopped by holding back for about 1 s; zero-g is averaged, neutral forward/back permits radius tuning, backward diagonal adjusts LED offset, forward tests movement. Save to EEPROM on exit. Fork-specific calibration measurements: not found. [readme.md](https://github.com/HelloGuy8000/espmelt/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md), [openmelt/spin_control.cpp](https://github.com/HelloGuy8000/espmelt/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/spin_control.cpp).

11. **Controls, modes, arming and failsafe.** Confirmed/reported: three interrupt-read RC channels; zero-throttle startup verification and a configured 2 s watchdog. README describes stopping after about 1 s without throttle updates and resuming when signals return. This is source behavior, not an independently exercised failsafe. [openmelt/rc_handler.cpp](https://github.com/HelloGuy8000/espmelt/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/rc_handler.cpp), [openmelt/melty_config.h](https://github.com/HelloGuy8000/espmelt/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/melty_config.h), [readme.md](https://github.com/HelloGuy8000/espmelt/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md).

12. **Distinctive ideas and implementation.** Repository description says ESP32, but the inspected default-branch firmware/configuration is the inherited Arduino/AVR implementation and upstream compare is identical. An ESP32 conversion on this inspected branch is not established. Other branches were not surveyed. [repository metadata](https://api.github.com/repos/HelloGuy8000/espmelt), [upstream comparison](https://api.github.com/repos/nothinglabs/openmelt2/compare/main...HelloGuy8000:main), [openmelt/melty_config.h](https://github.com/HelloGuy8000/espmelt/blob/7d062906950647350195b2b439e6f40e28492ce7/openmelt/melty_config.h).

13. **Author-reported problems, failures and evidence limits.** Inherited author reports: some one-wheel builds bounce/oscillate and lose translational control at high speed; a prototype hang/runaway was associated with I2C wiring/library failure, prompting watchdog use. These are upstream reports copied into the README, not validated failures of this fork. [readme.md](https://github.com/HelloGuy8000/espmelt/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md).

14. **License and reuse notice.** Inherited README states Creative Commons Attribution–NonCommercial–ShareAlike 4.0. A separate license audit of this fork’s additions was not performed. [readme.md](https://github.com/HelloGuy8000/espmelt/blob/7d062906950647350195b2b439e6f40e28492ce7/readme.md).

<a id="p111"></a>

## P111. mak0t0san/openmelt2

1. **Identity, authorship, URLs and visible dates.** Repository owner: mak0t0san. Inspected latest default-branch commit credited to Rich Olson / nothinglabs.com. Repository created 2025-02-01T20:41:39Z (UTC). Inspected commit 867b3199055e8908933d619f6437f22d5fb0276e dated 2024-03-13T20:48:46Z (UTC). GitHub identifies parent nothinglabs/openmelt2. [repository metadata](https://api.github.com/repos/mak0t0san/openmelt2); [inspected commit](https://github.com/mak0t0san/openmelt2/commit/867b3199055e8908933d619f6437f22d5fb0276e).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [openmelt/accel_handler.cpp](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/accel_handler.cpp), [openmelt/spin_control.cpp](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/spin_control.cpp), [openmelt/melty_config.h](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/melty_config.h), [openmelt/rc_handler.cpp](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/rc_handler.cpp), [openmelt/motor_driver.cpp](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/motor_driver.cpp), [readme.md](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/readme.md). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: behind, 0 commit(s) ahead and 2 behind at inspection. No fork-specific commits appear in that comparison; no new fork implementation is inferred. [upstream comparison](https://api.github.com/repos/nothinglabs/openmelt2/compare/main...mak0t0san:main).

3. **Robot context and reported status.** Reported in inherited README: Open Melt 2 is an Arduino translational-drift controller for one or two drive motors, with an antweight reference platform. The inherited 3200 RPM testing claim belongs to the upstream project, not an independently verified build of this fork. A separate fork robot and event record: not found. [readme.md](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/readme.md).

4. **Hardware and exact parts.** Reported inherited hardware: Arduino Micro/ATmega32u4 5 V 16 MHz; H3LIS331DL, preferably Adafruit breakout; optional SparkFun breakout plus level converter; hobby RC receiver, heading LED and motor driver(s). Reference motor switching uses RFP30N06LE; SimonK Hobbypower 30 A support is reported. Exact hardware built by this fork owner: not found. [readme.md](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/readme.md).

5. **Heading sensing and mounting.** Confirmed in code: X-axis LIS331 acceleration through I2C; default effective radius 3.9 cm. README describes interactive orientation/radius compensation and respecting 400 g full-scale loading. The number is a software default, not a measured fork mounting radius. [openmelt/accel_handler.cpp](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/accel_handler.cpp), [openmelt/melty_config.h](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/melty_config.h), [readme.md](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/readme.md).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed in get_rotation_interval_ms: RPM=sqrt(abs(g−zero)×89445/effective_radius_cm), then period=60,000/RPM ms. Steering changes effective radius. I2C is configured at 400 kHz; no explicit additional digital noise filter or fixed measured loop frequency was found in the inspected accel/spin files. [openmelt/accel_handler.cpp](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/accel_handler.cpp), [openmelt/spin_control.cpp](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/spin_control.cpp).

7. **Drift and correction.** Confirmed/reported: radius/zero-offset setup corrects speed tracking; RC left/right trim adjusts heading by changing the estimated period. LED phase has an independent stored offset. Automatic absolute-heading recovery and quantified drift tests for this fork: not found. [openmelt/spin_control.cpp](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/spin_control.cpp), [readme.md](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/readme.md).

8. **Translation timing, phase width and stick mapping.** Confirmed in code: motor-on duration is throttle fraction of the estimated revolution in default BINARY_THROTTLE. Motor windows are centered half a turn apart; forward/back swaps them and neutral alternates to cancel drift. Below 400 RPM the code requests full-rotation power. Dynamic-PWM mode can fix on-duration at 50%, but configuration selection must be checked separately. [openmelt/spin_control.cpp](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/spin_control.cpp), [openmelt/melty_config.h](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/melty_config.h).

9. **Heading LED/display.** Confirmed/reported: once-per-turn beacon centered on a stored 0–99% offset, width follows throttle and is clamped to 10–90% of a turn; shimmer indicates low battery or calibration adjustment. README discusses shell occlusion at shallow viewing angles. Exact fork LED model and placement: not found. [openmelt/spin_control.cpp](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/spin_control.cpp), [readme.md](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/readme.md).

10. **Calibration and persistence.** Reported/confirmed: enter config while stopped by holding back for about 1 s; zero-g is averaged, neutral forward/back permits radius tuning, backward diagonal adjusts LED offset, forward tests movement. Save to EEPROM on exit. Fork-specific calibration measurements: not found. [readme.md](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/readme.md), [openmelt/spin_control.cpp](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/spin_control.cpp).

11. **Controls, modes, arming and failsafe.** Confirmed/reported: three interrupt-read RC channels; zero-throttle startup verification and a configured 2 s watchdog. README describes stopping after about 1 s without throttle updates and resuming when signals return. This is source behavior, not an independently exercised failsafe. [openmelt/rc_handler.cpp](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/rc_handler.cpp), [openmelt/melty_config.h](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/melty_config.h), [readme.md](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/readme.md).

12. **Distinctive ideas and implementation.** Distinctive inherited design: interactive radius and LED-offset calibration, one/two-wheel timing without a wheel-count setting, and binary/fixed/dynamic-PWM motor modes. Fork-specific work is recorded separately in field 2. [openmelt/spin_control.cpp](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/spin_control.cpp), [openmelt/melty_config.h](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/openmelt/melty_config.h).

13. **Author-reported problems, failures and evidence limits.** Inherited author reports: some one-wheel builds bounce/oscillate and lose translational control at high speed; a prototype hang/runaway was associated with I2C wiring/library failure, prompting watchdog use. These are upstream reports copied into the README, not validated failures of this fork. [readme.md](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/readme.md).

14. **License and reuse notice.** Inherited README states Creative Commons Attribution–NonCommercial–ShareAlike 4.0. A separate license audit of this fork’s additions was not performed. [readme.md](https://github.com/mak0t0san/openmelt2/blob/867b3199055e8908933d619f6437f22d5fb0276e/readme.md).

<a id="p112"></a>

## P112. Ryan-WHOOP-26982E/openmeltStig

1. **Identity, authorship, URLs and visible dates.** Repository owner: Ryan-WHOOP-26982E. Inspected latest default-branch commit credited to Ryan-WHOOP-26982E. Repository created 2026-02-10T22:19:58Z (UTC). Inspected commit 0041f72ad10104b7d6f8316800ed030a3bd33230 dated 2026-02-23T02:09:03Z (UTC). [repository metadata](https://api.github.com/repos/Ryan-WHOOP-26982E/openmeltStig); [inspected commit](https://github.com/Ryan-WHOOP-26982E/openmeltStig/commit/0041f72ad10104b7d6f8316800ed030a3bd33230).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [openmelt/accel_handler.cpp](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/openmelt/accel_handler.cpp), [openmelt/spin_control.cpp](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/openmelt/spin_control.cpp), [openmelt/melty_config.h](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/openmelt/melty_config.h), [openmelt/rc_handler.cpp](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/openmelt/rc_handler.cpp), [openmelt/motor_driver.cpp](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/openmelt/motor_driver.cpp), [readme.md](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/readme.md). Hardware tests/builds/simulations were not run by this survey. Changes from upstream not established; no verified parent-branch comparison was available/performed.

3. **Robot context and reported status.** Reported in inherited README: Open Melt 2 is an Arduino translational-drift controller for one or two drive motors, with an antweight reference platform. The inherited 3200 RPM testing claim belongs to the upstream project, not an independently verified build of this fork. A separate fork robot and event record: not found. [readme.md](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/readme.md).

4. **Hardware and exact parts.** Reported inherited hardware: Arduino Micro/ATmega32u4 5 V 16 MHz; H3LIS331DL, preferably Adafruit breakout; optional SparkFun breakout plus level converter; hobby RC receiver, heading LED and motor driver(s). Reference motor switching uses RFP30N06LE; SimonK Hobbypower 30 A support is reported. Exact hardware built by this fork owner: not found. [readme.md](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/readme.md).

5. **Heading sensing and mounting.** Confirmed in code: X-axis LIS331 acceleration through I2C; default effective radius 3.9 cm. README describes interactive orientation/radius compensation and respecting 400 g full-scale loading. The number is a software default, not a measured fork mounting radius. [openmelt/accel_handler.cpp](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/openmelt/accel_handler.cpp), [openmelt/melty_config.h](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/openmelt/melty_config.h), [readme.md](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/readme.md).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed in get_rotation_interval_ms: RPM=sqrt(abs(g−zero)×89445/effective_radius_cm), then period=60,000/RPM ms. Steering changes effective radius. I2C is configured at 400 kHz; no explicit additional digital noise filter or fixed measured loop frequency was found in the inspected accel/spin files. [openmelt/accel_handler.cpp](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/openmelt/accel_handler.cpp), [openmelt/spin_control.cpp](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/openmelt/spin_control.cpp).

7. **Drift and correction.** Confirmed/reported: radius/zero-offset setup corrects speed tracking; RC left/right trim adjusts heading by changing the estimated period. LED phase has an independent stored offset. Automatic absolute-heading recovery and quantified drift tests for this fork: not found. [openmelt/spin_control.cpp](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/openmelt/spin_control.cpp), [readme.md](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/readme.md).

8. **Translation timing, phase width and stick mapping.** Confirmed in code: motor-on duration is throttle fraction of the estimated revolution in default BINARY_THROTTLE. Motor windows are centered half a turn apart; forward/back swaps them and neutral alternates to cancel drift. Below 400 RPM the code requests full-rotation power. Dynamic-PWM mode can fix on-duration at 50%, but configuration selection must be checked separately. [openmelt/spin_control.cpp](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/openmelt/spin_control.cpp), [openmelt/melty_config.h](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/openmelt/melty_config.h).

9. **Heading LED/display.** Confirmed/reported: once-per-turn beacon centered on a stored 0–99% offset, width follows throttle and is clamped to 10–90% of a turn; shimmer indicates low battery or calibration adjustment. README discusses shell occlusion at shallow viewing angles. Exact fork LED model and placement: not found. [openmelt/spin_control.cpp](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/openmelt/spin_control.cpp), [readme.md](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/readme.md).

10. **Calibration and persistence.** Reported/confirmed: enter config while stopped by holding back for about 1 s; zero-g is averaged, neutral forward/back permits radius tuning, backward diagonal adjusts LED offset, forward tests movement. Save to EEPROM on exit. Fork-specific calibration measurements: not found. [readme.md](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/readme.md), [openmelt/spin_control.cpp](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/openmelt/spin_control.cpp).

11. **Controls, modes, arming and failsafe.** Confirmed/reported: three interrupt-read RC channels; zero-throttle startup verification and a configured 2 s watchdog. README describes stopping after about 1 s without throttle updates and resuming when signals return. This is source behavior, not an independently exercised failsafe. [openmelt/rc_handler.cpp](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/openmelt/rc_handler.cpp), [openmelt/melty_config.h](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/openmelt/melty_config.h), [readme.md](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/readme.md).

12. **Distinctive ideas and implementation.** Distinctive inherited design: interactive radius and LED-offset calibration, one/two-wheel timing without a wheel-count setting, and binary/fixed/dynamic-PWM motor modes. Fork-specific work is recorded separately in field 2. [openmelt/spin_control.cpp](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/openmelt/spin_control.cpp), [openmelt/melty_config.h](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/openmelt/melty_config.h).

13. **Author-reported problems, failures and evidence limits.** Inherited author reports: some one-wheel builds bounce/oscillate and lose translational control at high speed; a prototype hang/runaway was associated with I2C wiring/library failure, prompting watchdog use. These are upstream reports copied into the README, not validated failures of this fork. [readme.md](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/readme.md).

14. **License and reuse notice.** Inherited README states Creative Commons Attribution–NonCommercial–ShareAlike 4.0. A separate license audit of this fork’s additions was not performed. [readme.md](https://github.com/Ryan-WHOOP-26982E/openmeltStig/blob/0041f72ad10104b7d6f8316800ed030a3bd33230/readme.md).

<a id="p113"></a>

## P113. TomasSiauliaiNights/openmelty

1. **Identity, authorship, URLs and visible dates.** Repository owner: TomasSiauliaiNights. Inspected latest default-branch commit credited to Tomas Sobutas. Repository created 2025-04-24T15:39:30Z (UTC). Inspected commit f343e487f7775b1a9a9011767366903d0ae95292 dated 2025-04-24T15:39:21Z (UTC). [repository metadata](https://api.github.com/repos/TomasSiauliaiNights/openmelty); [inspected commit](https://github.com/TomasSiauliaiNights/openmelty/commit/f343e487f7775b1a9a9011767366903d0ae95292).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [accel_handler.cpp](https://github.com/TomasSiauliaiNights/openmelty/blob/f343e487f7775b1a9a9011767366903d0ae95292/accel_handler.cpp), [spin_control.cpp](https://github.com/TomasSiauliaiNights/openmelty/blob/f343e487f7775b1a9a9011767366903d0ae95292/spin_control.cpp), [melty_config.h](https://github.com/TomasSiauliaiNights/openmelty/blob/f343e487f7775b1a9a9011767366903d0ae95292/melty_config.h), [rc_handler.cpp](https://github.com/TomasSiauliaiNights/openmelty/blob/f343e487f7775b1a9a9011767366903d0ae95292/rc_handler.cpp). Hardware tests/builds/simulations were not run by this survey. Changes from upstream not established; no verified parent-branch comparison was available/performed.

3. **Robot context and reported status.** Confirmed: initial-commit code snapshot with Open Melt-style modules. A README, named robot, weight, intended event and completed behavior demonstration: not found. [inspected commit](https://github.com/TomasSiauliaiNights/openmelty/commit/f343e487f7775b1a9a9011767366903d0ae95292).

4. **Hardware and exact parts.** Confirmed: Adafruit_ADXL375 object on I2C SDA8/SCL9; motor pins 1/7, heading pin 6, three PWM receiver inputs pins 2/4/3. Exact MCU/board, motors, ESC, radio and battery: not found. A specific ESP32 model must not be assumed from these API calls alone. [accel_handler.cpp](https://github.com/TomasSiauliaiNights/openmelty/blob/f343e487f7775b1a9a9011767366903d0ae95292/accel_handler.cpp), [melty_config.h](https://github.com/TomasSiauliaiNights/openmelty/blob/f343e487f7775b1a9a9011767366903d0ae95292/melty_config.h).

5. **Heading sensing and mounting.** Confirmed: get_accel_force_g uses ADXL375 Y acceleration divided by 9.81; configured effective radius=1 cm. Older LIS331 references remain in comments but the active object is ADXL375. Physical mounting geometry was not supplied. [accel_handler.cpp](https://github.com/TomasSiauliaiNights/openmelty/blob/f343e487f7775b1a9a9011767366903d0ae95292/accel_handler.cpp), [melty_config.h](https://github.com/TomasSiauliaiNights/openmelty/blob/f343e487f7775b1a9a9011767366903d0ae95292/melty_config.h).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed: sqrt(abs(g−zero)×89445/effective_radius_cm), estimated-turn timing and manual steering via radius factor. Sensor ODR, filter configuration and achieved estimator/control rate: not found in inspected code; I2C clock-setting line is commented out. [accel_handler.cpp](https://github.com/TomasSiauliaiNights/openmelty/blob/f343e487f7775b1a9a9011767366903d0ae95292/accel_handler.cpp), [spin_control.cpp](https://github.com/TomasSiauliaiNights/openmelty/blob/f343e487f7775b1a9a9011767366903d0ae95292/spin_control.cpp).

7. **Drift and correction.** Confirmed/reported: radius/zero-offset setup corrects speed tracking; RC left/right trim adjusts heading by changing the estimated period. LED phase has an independent stored offset. Automatic absolute-heading recovery and quantified drift tests for this fork: not found. [spin_control.cpp](https://github.com/TomasSiauliaiNights/openmelty/blob/f343e487f7775b1a9a9011767366903d0ae95292/spin_control.cpp).

8. **Translation timing, phase width and stick mapping.** Confirmed: 180°-separated forward/back motor windows and neutral alternation inherited in code. Configuration selects DYNAMIC_PWM_THROTTLE with a 50% angular on-portion and PWM values 1650/1000/1000. Actual motor_driver.cpp was not read, so pulse-unit/API correctness and working ESC output are not established. [spin_control.cpp](https://github.com/TomasSiauliaiNights/openmelty/blob/f343e487f7775b1a9a9011767366903d0ae95292/spin_control.cpp), [melty_config.h](https://github.com/TomasSiauliaiNights/openmelty/blob/f343e487f7775b1a9a9011767366903d0ae95292/melty_config.h).

9. **Heading LED/display.** Confirmed/reported: once-per-turn beacon centered on a stored 0–99% offset, width follows throttle and is clamped to 10–90% of a turn; shimmer indicates low battery or calibration adjustment. README discusses shell occlusion at shallow viewing angles. Exact fork LED model and placement: not found. [spin_control.cpp](https://github.com/TomasSiauliaiNights/openmelty/blob/f343e487f7775b1a9a9011767366903d0ae95292/spin_control.cpp).

10. **Calibration and persistence.** Confirmed: stopped config captures zero g; effective radius and LED offset are adjustable; save/load calls retain values through config_storage. Actual successful calibration, firmware compile and motion results: not found. [spin_control.cpp](https://github.com/TomasSiauliaiNights/openmelty/blob/f343e487f7775b1a9a9011767366903d0ae95292/spin_control.cpp).

11. **Controls, modes, arming and failsafe.** Confirmed: three interrupt-captured PWM channels, zero-throttle boot define and watchdog timeout setting. ENABLE_WATCHDOG is not an active define in the inspected config, so a functioning watchdog must not be assumed. Runtime control/safety tests: not found. [rc_handler.cpp](https://github.com/TomasSiauliaiNights/openmelty/blob/f343e487f7775b1a9a9011767366903d0ae95292/rc_handler.cpp), [melty_config.h](https://github.com/TomasSiauliaiNights/openmelty/blob/f343e487f7775b1a9a9011767366903d0ae95292/melty_config.h).

12. **Distinctive ideas and implementation.** Inspected differences visible in this standalone snapshot: active ADXL375 Y-axis acquisition, remapped pins and dynamic-PWM settings. No verified upstream relationship/diff was established; changes from upstream not established beyond these observed implementation details. [accel_handler.cpp](https://github.com/TomasSiauliaiNights/openmelty/blob/f343e487f7775b1a9a9011767366903d0ae95292/accel_handler.cpp), [melty_config.h](https://github.com/TomasSiauliaiNights/openmelty/blob/f343e487f7775b1a9a9011767366903d0ae95292/melty_config.h).

13. **Author-reported problems, failures and evidence limits.** Author-reported failure narrative: not found. Source prints an ADXL375 wiring error and halts if initialization fails, but that branch is not evidence of an actual observed fault. [accel_handler.cpp](https://github.com/TomasSiauliaiNights/openmelty/blob/f343e487f7775b1a9a9011767366903d0ae95292/accel_handler.cpp).

14. **License and reuse notice.** License: not found in inspected files/repository metadata. Inherited-looking source structure does not establish a repository license. [repository metadata](https://api.github.com/repos/TomasSiauliaiNights/openmelty).

<a id="p114"></a>

## P114. TomasSiauliaiNights/Openmeltyy

1. **Identity, authorship, URLs and visible dates.** Repository owner: TomasSiauliaiNights. Repository created 2025-04-24T15:26:42Z (UTC). Latest commit date: not found (empty repository). [repository metadata](https://api.github.com/repos/TomasSiauliaiNights/Openmeltyy); [repository](https://github.com/TomasSiauliaiNights/Openmeltyy).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: not found; empty public repository. Hardware tests/builds/simulations were not run by this survey. Changes from upstream not established; no verified parent-branch comparison was available/performed.

3. **Robot context and reported status.** Not found: repository is empty in the inspected public contents/commit lookup; no source, README, robot, design or test evidence was available. [repository metadata](https://api.github.com/repos/TomasSiauliaiNights/Openmeltyy).

4. **Hardware and exact parts.** Not found: repository is empty in the inspected public contents/commit lookup; no source, README, robot, design or test evidence was available. [repository metadata](https://api.github.com/repos/TomasSiauliaiNights/Openmeltyy).

5. **Heading sensing and mounting.** Not found: repository is empty in the inspected public contents/commit lookup; no source, README, robot, design or test evidence was available. [repository metadata](https://api.github.com/repos/TomasSiauliaiNights/Openmeltyy).

6. **Angle/RPM algorithm, filters, rates and code locations.** Not found: repository is empty in the inspected public contents/commit lookup; no source, README, robot, design or test evidence was available. [repository metadata](https://api.github.com/repos/TomasSiauliaiNights/Openmeltyy).

7. **Drift and correction.** Not found: repository is empty in the inspected public contents/commit lookup; no source, README, robot, design or test evidence was available. [repository metadata](https://api.github.com/repos/TomasSiauliaiNights/Openmeltyy).

8. **Translation timing, phase width and stick mapping.** Not found: repository is empty in the inspected public contents/commit lookup; no source, README, robot, design or test evidence was available. [repository metadata](https://api.github.com/repos/TomasSiauliaiNights/Openmeltyy).

9. **Heading LED/display.** Not found: repository is empty in the inspected public contents/commit lookup; no source, README, robot, design or test evidence was available. [repository metadata](https://api.github.com/repos/TomasSiauliaiNights/Openmeltyy).

10. **Calibration and persistence.** Not found: repository is empty in the inspected public contents/commit lookup; no source, README, robot, design or test evidence was available. [repository metadata](https://api.github.com/repos/TomasSiauliaiNights/Openmeltyy).

11. **Controls, modes, arming and failsafe.** Not found: repository is empty in the inspected public contents/commit lookup; no source, README, robot, design or test evidence was available. [repository metadata](https://api.github.com/repos/TomasSiauliaiNights/Openmeltyy).

12. **Distinctive ideas and implementation.** Not found: repository is empty in the inspected public contents/commit lookup; no source, README, robot, design or test evidence was available. [repository metadata](https://api.github.com/repos/TomasSiauliaiNights/Openmeltyy).

13. **Author-reported problems, failures and evidence limits.** Not found: repository is empty in the inspected public contents/commit lookup; no source, README, robot, design or test evidence was available. [repository metadata](https://api.github.com/repos/TomasSiauliaiNights/Openmeltyy).

14. **License and reuse notice.** Not found: repository is empty in the inspected public contents/commit lookup; no source, README, robot, design or test evidence was available. [repository metadata](https://api.github.com/repos/TomasSiauliaiNights/Openmeltyy).

<a id="p115"></a>

## P115. Jacob-Harrell-RIT/PolarMelt

1. **Identity, authorship, URLs and visible dates.** Repository owner: Jacob-Harrell-RIT. Inspected latest default-branch commit credited to Jacob-Harrell-RIT. Repository created 2018-01-25T19:39:08Z (UTC). Inspected commit 60a66917a972890b9ca4102144a84fe4c1cbc6cd dated 2018-04-15T21:35:09Z (UTC). [repository metadata](https://api.github.com/repos/Jacob-Harrell-RIT/PolarMelt); [inspected commit](https://github.com/Jacob-Harrell-RIT/PolarMelt/commit/60a66917a972890b9ca4102144a84fe4c1cbc6cd).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [MAG_Interrupt.ino](https://github.com/Jacob-Harrell-RIT/PolarMelt/blob/60a66917a972890b9ca4102144a84fe4c1cbc6cd/MAG_Interrupt.ino), [In Progress/Spinning_POW/Spinning_POW.ino](https://github.com/Jacob-Harrell-RIT/PolarMelt/blob/60a66917a972890b9ca4102144a84fe4c1cbc6cd/In%20Progress/Spinning_POW/Spinning_POW.ino), [README.md](https://github.com/Jacob-Harrell-RIT/PolarMelt/blob/60a66917a972890b9ca4102144a84fe4c1cbc6cd/README.md). Hardware tests/builds/simulations were not run by this survey. Changes from upstream not established; no verified parent-branch comparison was available/performed.

3. **Robot context and reported status.** Reported: Teensy 3.2 meltybrain experiment that will hopefully use magnetometer data for directional-error detection. Magnetometer correction is a stated intention, not established completed control. Weight/event outcome: not found. [README.md](https://github.com/Jacob-Harrell-RIT/PolarMelt/blob/60a66917a972890b9ca4102144a84fe4c1cbc6cd/README.md).

4. **Hardware and exact parts.** Reported/confirmed: Teensy 3.2, SBUS (x8r object on Serial2), two Servo outputs pins23/22 and two 19-pixel DotStar strips. MAG_Interrupt sketch instantiates Adafruit_LSM303. Main spin experiment reads analog A7/A6; exact high-g analog sensor, motor/ESC/battery model: not found. [README.md](https://github.com/Jacob-Harrell-RIT/PolarMelt/blob/60a66917a972890b9ca4102144a84fe4c1cbc6cd/README.md), [In Progress/Spinning_POW/Spinning_POW.ino](https://github.com/Jacob-Harrell-RIT/PolarMelt/blob/60a66917a972890b9ca4102144a84fe4c1cbc6cd/In%20Progress/Spinning_POW/Spinning_POW.ino), [MAG_Interrupt.ino](https://github.com/Jacob-Harrell-RIT/PolarMelt/blob/60a66917a972890b9ca4102144a84fe4c1cbc6cd/MAG_Interrupt.ino).

5. **Heading sensing and mounting.** Confirmed: spin experiment averages analog A7/A6 and subtracts 2047; ACCEL_RADIUS=2.5 cm is configured. Separate LSM303 sketch explores sensor reads. An implemented fusion path joining magnetometer to melty heading was not found in inspected code. [In Progress/Spinning_POW/Spinning_POW.ino](https://github.com/Jacob-Harrell-RIT/PolarMelt/blob/60a66917a972890b9ca4102144a84fe4c1cbc6cd/In%20Progress/Spinning_POW/Spinning_POW.ino), [MAG_Interrupt.ino](https://github.com/Jacob-Harrell-RIT/PolarMelt/blob/60a66917a972890b9ca4102144a84fe4c1cbc6cd/MAG_Interrupt.ino).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed in readAccel: theta_dot=sqrt((meanADC−2047)/ACCEL_RADIUS); heading increments theta_dot×DT×ADC_TO_THETA, wrapping modulo 4096. IntervalTimer requests 1250 µs. DT is declared const int=1.25, which truncates to 1 in C++; therefore requested timing and arithmetic dt disagree (static observation, not a measured failure). [In Progress/Spinning_POW/Spinning_POW.ino](https://github.com/Jacob-Harrell-RIT/PolarMelt/blob/60a66917a972890b9ca4102144a84fe4c1cbc6cd/In%20Progress/Spinning_POW/Spinning_POW.ino).

7. **Drift and correction.** Planned: magnetometer directional-error correction. Implemented in inspected spin file: accelerometer-derived relative phase only. Quantified drift, sensor calibration and magnetometer correction success: not found. [README.md](https://github.com/Jacob-Harrell-RIT/PolarMelt/blob/60a66917a972890b9ca4102144a84fe4c1cbc6cd/README.md), [In Progress/Spinning_POW/Spinning_POW.ino](https://github.com/Jacob-Harrell-RIT/PolarMelt/blob/60a66917a972890b9ca4102144a84fe4c1cbc6cd/In%20Progress/Spinning_POW/Spinning_POW.ino).

8. **Translation timing, phase width and stick mapping.** Not found in inspected spin sketch: phase-dependent motor modulation. Both ESC outputs map throttle to 1430–2000 µs; heading only gates LEDs. This source demonstrates spin/heading experiments, not verified translational-drift behavior. [In Progress/Spinning_POW/Spinning_POW.ino](https://github.com/Jacob-Harrell-RIT/PolarMelt/blob/60a66917a972890b9ca4102144a84fe4c1cbc6cd/In%20Progress/Spinning_POW/Spinning_POW.ino).

9. **Heading LED/display.** Confirmed: two 19-DotStar strips with separate data/clock pins; heading window 683<heading<1360 within a 4096-count turn controls blue light, with startup/neutral/error colors. Physical viewing geometry and brightness test: not found. [In Progress/Spinning_POW/Spinning_POW.ino](https://github.com/Jacob-Harrell-RIT/PolarMelt/blob/60a66917a972890b9ca4102144a84fe4c1cbc6cd/In%20Progress/Spinning_POW/Spinning_POW.ino).

10. **Calibration and persistence.** Confirmed: hard-coded radius, ADC conversion factor and center subtraction; documented interactive calibration or successful magnetometer calibration: not found. [In Progress/Spinning_POW/Spinning_POW.ino](https://github.com/Jacob-Harrell-RIT/PolarMelt/blob/60a66917a972890b9ca4102144a84fe4c1cbc6cd/In%20Progress/Spinning_POW/Spinning_POW.ino), [README.md](https://github.com/Jacob-Harrell-RIT/PolarMelt/blob/60a66917a972890b9ca4102144a84fe4c1cbc6cd/README.md).

11. **Controls, modes, arming and failsafe.** Confirmed: on received SBUS failsafe flag the code sets both servos to 1430 µs and shows error color. A separate no-new-frame timeout, arming interlock and verified failsafe testing were not found in the inspected spin file. [In Progress/Spinning_POW/Spinning_POW.ino](https://github.com/Jacob-Harrell-RIT/PolarMelt/blob/60a66917a972890b9ca4102144a84fe4c1cbc6cd/In%20Progress/Spinning_POW/Spinning_POW.ino).

12. **Distinctive ideas and implementation.** Distinctive intended direction: magnetometer-assisted drift correction. The supplied repository contains separate sensor and spin experiments; their existence is not a completed fused controller. [README.md](https://github.com/Jacob-Harrell-RIT/PolarMelt/blob/60a66917a972890b9ca4102144a84fe4c1cbc6cd/README.md), [MAG_Interrupt.ino](https://github.com/Jacob-Harrell-RIT/PolarMelt/blob/60a66917a972890b9ca4102144a84fe4c1cbc6cd/MAG_Interrupt.ino), [In Progress/Spinning_POW/Spinning_POW.ino](https://github.com/Jacob-Harrell-RIT/PolarMelt/blob/60a66917a972890b9ca4102144a84fe4c1cbc6cd/In%20Progress/Spinning_POW/Spinning_POW.ino).

13. **Author-reported problems, failures and evidence limits.** Author-reported failure diary: not found. The integer DT issue and absence of translation modulation above are survey source observations, not author claims or reproduced hardware failures. [In Progress/Spinning_POW/Spinning_POW.ino](https://github.com/Jacob-Harrell-RIT/PolarMelt/blob/60a66917a972890b9ca4102144a84fe4c1cbc6cd/In%20Progress/Spinning_POW/Spinning_POW.ino).

14. **License and reuse notice.** GitHub repository metadata identifies MIT. This survey did not audit all dependency or asset licenses. [repository metadata](https://api.github.com/repos/Jacob-Harrell-RIT/PolarMelt).

<a id="p116"></a>

## P116. EpicStuff/NSL-Susan-Code

1. **Identity, authorship, URLs and visible dates.** Repository owner: EpicStuff. Inspected latest default-branch commit credited to Alexander Bangu. Repository created 2024-05-17T20:57:04Z (UTC). Inspected commit 4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb dated 2026-10-18T20:21:45Z (UTC). GitHub identifies parent skysdottir/PotatoMelt. [repository metadata](https://api.github.com/repos/EpicStuff/NSL-Susan-Code); [inspected commit](https://github.com/EpicStuff/NSL-Susan-Code/commit/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [src/accel_handler.cpp](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/src/accel_handler.cpp), [src/spin_control.cpp](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/src/spin_control.cpp), [src/melty_config.h](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/src/melty_config.h), [src/rc_handler.cpp](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/src/rc_handler.cpp), [platformio.ini](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/platformio.ini), [LICENSE](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/LICENSE), [README.md](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/README.md). Hardware tests/builds/simulations were not run by this survey. Default-branch comparison to parent: ahead, 43 commit(s) ahead and 0 behind at inspection. Changed-file scope includes `.gitignore`, `LICENSE`, `README.md`, `include/README`, `lib/DShot-Arduino-master/README.md`, `lib/DShot-Arduino-master/examples/DShotLibraryTest/DShotLibraryTest.ino`, `lib/DShot-Arduino-master/keywords.txt`, `lib/DShot-Arduino-master/library.properties`, `lib/DShot/DShot.cpp`, `lib/DShot/DShot.h`, `lib/README`, `lib/SparkFun_LIS331_Arduino_Library/Examples/LIS331_I2C_Example/LIS331_I2C_Example.ino` and additional files. Detailed findings below describe the inspected subset; the entire changed tree was not audited. [upstream comparison](https://api.github.com/repos/skysdottir/PotatoMelt/compare/main...EpicStuff:main).

3. **Robot context and reported status.** Reported: NSL-Susan-Code is a PotatoMelt-based drive controller. README retains an ATmega Arduino description and leaves development hardware as TODO. Exact robot weight, construction and competition results: not found. [README.md](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/README.md).

4. **Hardware and exact parts.** Confirmed: PlatformIO board=micro, platform=atmelavr; LIS331-family I2C acquisition, iBus input and DShot motor path, heading output definitions on 16/13/30. README hardware section is TODO. Exact physical board revision, motor/ESC/receiver/battery parts: not found. [platformio.ini](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/platformio.ini), [src/accel_handler.cpp](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/src/accel_handler.cpp), [src/rc_handler.cpp](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/src/rc_handler.cpp), [src/melty_config.h](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/src/melty_config.h), [README.md](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/README.md).

5. **Heading sensing and mounting.** Confirmed: radial Y-axis LIS331 force and default effective radius 6 cm; default beacon offset 0%. Actual mounting radius/orientation measurement: not found. [src/accel_handler.cpp](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/src/accel_handler.cpp), [src/melty_config.h](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/src/melty_config.h).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed: sqrt(abs(g−zero)×89445/radius_cm), eight correction pairs with interpolation; Timer3 compare configured at 2 kHz, parameter path delays 20 ms, PID sample interval 20 ms. This variant assigns corrected RPM to PID input, unlike its stale raw-RPM comment. Measured achieved rates/noise response: not found. [src/accel_handler.cpp](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/src/accel_handler.cpp), [src/spin_control.cpp](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/src/spin_control.cpp).

7. **Drift and correction.** Confirmed: correction table adjusts RPM/phase and now feeds corrected RPM to the PID before steering correction; manual steering changes estimated period. PID gains are 0.3/0.2/0.1 in this snapshot. Quantified drift/closed-loop response: not found. [src/spin_control.cpp](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/src/spin_control.cpp), [src/melty_config.h](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/src/melty_config.h).

8. **Translation timing, phase width and stick mapping.** Confirmed in code: forward/back translation exchanges high/low DShot commands over opposing 180° half rotations. Offset scales with signed forward/back stick displacement, base throttle and translation trim, with limits before DShot conversion. Left/right input steers the relative heading; omnidirectional translation is not implemented in this inspected path. [src/spin_control.cpp](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/src/spin_control.cpp).

9. **Heading LED/display.** Confirmed: beacon width is RPM/MAX_TARGET_RPM/8, then clamped to 10–90% of a revolution; configuration defines three heading outputs. Exact LED driver wiring/physical placement was not inspected. [src/spin_control.cpp](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/src/spin_control.cpp), [src/melty_config.h](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/src/melty_config.h).

10. **Calibration and persistence.** Reported: hold right stick back for 3 s at rest to enter/exit config; capture zero g, tune eight speed/correction points and LED offset, save with channel6. This differs from the inherited 1 s wording in other PotatoMelt snapshots. Independent calibration success: not found. [README.md](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/README.md), [src/accel_handler.cpp](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/src/accel_handler.cpp).

11. **Controls, modes, arming and failsafe.** Confirmed: iBus receiver controls; tank/PID/translation trim enabled; 3 s control-motion timeout and watchdog timeout constant 2 s. An active ENABLE_WATCHDOG define was not found in the inspected config, so watchdog operation is not established from the timeout constant alone. Battery alarm/halt defines were also not established as active here. [src/rc_handler.cpp](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/src/rc_handler.cpp), [src/melty_config.h](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/src/melty_config.h).

12. **Distinctive ideas and implementation.** Inspected additions include PlatformIO/src layout, altered gains/radius/LED outputs, corrected-RPM PID input, narrower LED scaling and the README’s longer config hold. Upstream comparison also lists bundled DShot/LIS331 library changes; those libraries were not audited here. [upstream comparison](https://api.github.com/repos/skysdottir/PotatoMelt/compare/main...EpicStuff:main), [platformio.ini](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/platformio.ini), [src/spin_control.cpp](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/src/spin_control.cpp), [src/melty_config.h](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/src/melty_config.h), [README.md](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/README.md).

13. **Author-reported problems, failures and evidence limits.** Author-specific hardware failure log: not found. README still leaves hardware TODO and supplies no verified motion results. Inherited code comments describe concern about calibration factors affecting PID, but this snapshot actually assigns the corrected value to PID input. [README.md](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/README.md), [src/spin_control.cpp](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/src/spin_control.cpp).

14. **License and reuse notice.** LICENSE is nonstandard: its heading reads GNU JUSTIFIED PUBLIC LICENSE, Version 3, while the body discusses the GNU General Public License. GitHub metadata classifies it NOASSERTION. It is therefore not identified here as an unmodified standard GPL text; exact intended reuse terms are unresolved. [LICENSE](https://github.com/EpicStuff/NSL-Susan-Code/blob/4536038ff4bf17d43ae75bb3fa1dd7e7ab2ed0bb/LICENSE), [repository metadata](https://api.github.com/repos/EpicStuff/NSL-Susan-Code).

<a id="p117"></a>

## P117. wengdahl/whirlwind-combat-SW

1. **Identity, authorship, URLs and visible dates.** Repository owner: wengdahl. Inspected latest default-branch commit credited to wengdahl. Repository created 2023-06-25T14:53:21Z (UTC). Inspected commit 78b9771f9cce1d213741d007da3a764cf68623e6 dated 2024-08-27T21:08:34Z (UTC). [repository metadata](https://api.github.com/repos/wengdahl/whirlwind-combat-SW); [inspected commit](https://github.com/wengdahl/whirlwind-combat-SW/commit/78b9771f9cce1d213741d007da3a764cf68623e6).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [ESC-Run/ESC-Run.ino](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/ESC-Run/ESC-Run.ino), [ESC-Run/position.cpp](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/ESC-Run/position.cpp), [whirlwind-robot/whirlwind-robot.ino](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/whirlwind-robot/whirlwind-robot.ino), [whirlwind-controller/whirlwind-controller.ino](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/whirlwind-controller/whirlwind-controller.ino), [README.md](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/README.md). Hardware tests/builds/simulations were not run by this survey. Changes from upstream not established; no verified parent-branch comparison was available/performed.

3. **Robot context and reported status.** Reported: in-progress meltybrain combat robot; hardware concept uses a Markforged X7 carbon-fiber reinforced shell, off-the-shelf parts and simple machined/PCB components. Final CAD/PCB release was planned. Exact mass and completed event result: not found. [README.md](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/README.md).

4. **Hardware and exact parts.** Reported controller: ESP32-WROOM-32D, with planned ESP32-S3 external-antenna revision. Robot code identifies ESP32-S3, ADXL375, NeoPixels and MCPWM ESC pulses; repository also contains ESP-NOW controller/robot experiments. Exact motors/ESCs, battery and finished PCB revision: not found. [README.md](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/README.md), [ESC-Run/ESC-Run.ino](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/ESC-Run/ESC-Run.ino), [whirlwind-controller/whirlwind-controller.ino](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/whirlwind-controller/whirlwind-controller.ino), [whirlwind-robot/whirlwind-robot.ino](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/whirlwind-robot/whirlwind-robot.ino).

5. **Heading sensing and mounting.** Confirmed in ESC-Run: ADXL375 X-axis minus 7.69 m/s² feeds radial model; DISTANCE_TO_SENSOR=0.03 m. Tare is TODO. Measured sensor orientation/radius and a validated offset: not found. [ESC-Run/ESC-Run.ino](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/ESC-Run/ESC-Run.ino), [ESC-Run/position.cpp](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/ESC-Run/position.cpp).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed: updateAccel uses EMA alpha=0.8, omega=sqrt(abs(int(filtered_accel/radius))), restoring sign if filtered force is negative. updateHeading integrates omega×elapsed_microseconds×57.2958 into microdegrees. Sensor reads occur when elapsed milliseconds >10; actual loop rate and estimator accuracy were not measured. [ESC-Run/position.cpp](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/ESC-Run/position.cpp), [ESC-Run/ESC-Run.ino](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/ESC-Run/ESC-Run.ino).

7. **Drift and correction.** Confirmed/planned: hard-coded force offset exists; tare/calibration procedure is TODO. Automatic absolute-heading correction and quantified drift result: not found. [ESC-Run/ESC-Run.ino](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/ESC-Run/ESC-Run.ino), [ESC-Run/position.cpp](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/ESC-Run/position.cpp).

8. **Translation timing, phase width and stick mapping.** Confirmed in inspected ESC-Run path: direct mode uses speed×cos/sin(angle) for forward/turn mixing. Point-and-shoot branch is empty; melty branch simply applies fixed −250/+250 µs around neutral. Phase-gated translation is not implemented in that sketch. Other repository experiments were not established as a working melty controller. [ESC-Run/ESC-Run.ino](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/ESC-Run/ESC-Run.ino).

9. **Heading LED/display.** Confirmed: three NeoPixels are configured; heading halves switch red/blue and another pixel shows a 90–270° sector. Physical LED location/visibility and timing performance: not found. [ESC-Run/ESC-Run.ino](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/ESC-Run/ESC-Run.ino).

10. **Calibration and persistence.** Planned: tare and a lights-guided calibration procedure. Source contains a fixed offset and unused tare input; completed calibrated operation: not found. [README.md](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/README.md), [ESC-Run/ESC-Run.ino](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/ESC-Run/ESC-Run.ino).

11. **Controls, modes, arming and failsafe.** Reported: custom controller over Bluetooth, with TODO for reliable BLE connection handling; later sketches use ESP-NOW. ESC-Run mode commands are parsed from BLE characteristics. End-to-end arming, fresh-input timeout and verified failsafe: not found in the inspected melty sketch. [README.md](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/README.md), [ESC-Run/ESC-Run.ino](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/ESC-Run/ESC-Run.ino), [whirlwind-controller/whirlwind-controller.ino](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/whirlwind-controller/whirlwind-controller.ino), [whirlwind-robot/whirlwind-robot.ino](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/whirlwind-robot/whirlwind-robot.ino).

12. **Distinctive ideas and implementation.** Distinctive exploratory work: carbon-fiber shell manufacturing, custom wireless controls, simple EMA acceleration-derived heading and both BLE/ESP-NOW communication experiments. A finished integrated translation algorithm is not established. [README.md](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/README.md), [ESC-Run/position.cpp](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/ESC-Run/position.cpp), [ESC-Run/ESC-Run.ino](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/ESC-Run/ESC-Run.ino).

13. **Author-reported problems, failures and evidence limits.** Author-reported latest-commit limitation: control timing remained slow/unreliable and the machine could not yet attend competition. README separately lists reliability, core separation/jitter and tare cleanup as TODO. These remain reported limitations. [inspected commit](https://github.com/wengdahl/whirlwind-combat-SW/commit/78b9771f9cce1d213741d007da3a764cf68623e6), [README.md](https://github.com/wengdahl/whirlwind-combat-SW/blob/78b9771f9cce1d213741d007da3a764cf68623e6/README.md).

14. **License and reuse notice.** GitHub repository metadata identifies MIT. This survey did not audit all dependency or asset licenses. [repository metadata](https://api.github.com/repos/wengdahl/whirlwind-combat-SW).

<a id="p118"></a>

## P118. Dean27817/FizzBee-V2

1. **Identity, authorship, URLs and visible dates.** Repository owner: Dean27817. Inspected latest default-branch commit credited to dean27817. Repository created 2025-12-23T21:19:31Z (UTC). Inspected commit a36fc6525400465ebc1a6011a7c7fda74d6c64b9 dated 2026-05-16T01:28:38Z (UTC). [repository metadata](https://api.github.com/repos/Dean27817/FizzBee-V2); [inspected commit](https://github.com/Dean27817/FizzBee-V2/commit/a36fc6525400465ebc1a6011a7c7fda74d6c64b9).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [code/src/accel.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/accel.cpp), [code/src/kinimatics.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/kinimatics.cpp), [code/src/main.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/main.cpp), [code/src/reciver.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/reciver.cpp), [code/src/motor.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/motor.cpp), [code/platformio.ini](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/platformio.ini), [README.md](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/README.md). Hardware tests/builds/simulations were not run by this survey. Changes from upstream not established; no verified parent-branch comparison was available/performed.

3. **Robot context and reported status.** Reported repository description: a new FizzBee meltybrain version with custom hardware. README is only a title; claimed improvement is not a measured validation. Weight, chassis details and event results: not found. [README.md](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/README.md), [repository metadata](https://api.github.com/repos/Dean27817/FizzBee-V2).

4. **Hardware and exact parts.** Confirmed: Waveshare ESP32-S3 Zero PlatformIO target; two LIS331HH 24 g sensors on I2C SDA5/SCL4 at 100 kHz, addresses 0x19/0x18; iBus RX44; motors GPIO17/18 at 50 Hz, 12-bit LEDC; heading outputs GPIO13/14. Exact physical motor/ESC/battery/receiver model: not found. [code/platformio.ini](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/platformio.ini), [code/src/accel.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/accel.cpp), [code/src/main.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/main.cpp), [code/src/reciver.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/reciver.cpp), [code/src/motor.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/motor.cpp).

5. **Heading sensing and mounting.** Confirmed: sensor X/Y hypot magnitudes and dual-sensor speed model. main.cpp constructs kinematics with knownRadius=1 and an explicit placeholder comment. That is not a verified 1 m mounting measurement; real geometry remains unresolved. [code/src/main.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/main.cpp), [code/src/accel.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/accel.cpp), [code/src/kinimatics.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/kinimatics.cpp).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed: findAngle integrates angular speed using elapsed millis()/1000 and wraps into 0–2π. Sensors are configured for 1 kHz ODR; actual estimator cadence is not established by that ODR. No additional temporal noise filter was found in these inspected acceleration/kinematics paths. Motor output is configured for 50 Hz. [code/src/accel.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/accel.cpp), [code/src/kinimatics.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/kinimatics.cpp), [code/src/main.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/main.cpp), [code/src/motor.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/motor.cpp).

7. **Drift and correction.** Confirmed: flash radius load/save functions exist, but main.cpp does not call calibrateRadius in its melty loop. The placeholder radius and any loaded values were not validated by this survey. Drift compensation results: not found. [code/src/main.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/main.cpp), [code/src/kinimatics.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/kinimatics.cpp).

8. **Translation timing, phase width and stick mapping.** Confirmed: findMotorSpeeds uses s=sin(currentAngle−stickAngle)×spin, then motor0=spin+s×clamped_translation_magnitude and motor1=−spin+s×clamped_translation_magnitude, clamped ±1. Stick direction comes from atan2. This is continuous sinusoidal modulation, with no narrow square-pulse width parameter in the inspected path. [code/src/kinimatics.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/kinimatics.cpp), [code/src/main.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/main.cpp).

9. **Heading LED/display.** Confirmed: main.cpp calls heading LED onLoop(currentAngle) in melty mode and stopped/error patterns as applicable. LED implementation itself was not read; exact display arc width, physical placement and brightness: not found in inspected evidence. [code/src/main.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/main.cpp).

10. **Calibration and persistence.** Confirmed: kinematics save/load stores knownRadius and foundRadius in a flash config file. Accel::calibrate is empty in the inspected snapshot. A completed stationary offset procedure or actual calibration/test data: not found. [code/src/kinimatics.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/kinimatics.cpp), [code/src/accel.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/accel.cpp).

11. **Controls, modes, arming and failsafe.** Confirmed: iBus inputs normalize six channels to ±1; throttle below −0.8 selects tank, otherwise melty. Startup waits for low throttle but after 10 s logs a warning and continues. No fresh-frame/lost-radio timeout was found in the inspected receiver/main source. GPIO motor command conversion maps ±1 to 1000–2000 µs pulses. [code/src/main.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/main.cpp), [code/src/reciver.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/reciver.cpp), [code/src/motor.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/motor.cpp).

12. **Distinctive ideas and implementation.** Distinctive implementation: two acceleration magnitudes, a radius-difference estimator foundRadius=(a1×knownRadius)/(a1−a2), and sinusoidal vector translation. Near-zero denominator is guarded. This is source math, not proof that the inferred radius is physically correct in every condition. [code/src/kinimatics.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/kinimatics.cpp).

13. **Author-reported problems, failures and evidence limits.** Reported latest commit says PWM was made working; no supporting measurement was supplied in inspected files. Source still has a placeholder kinematic radius, an empty accelerometer calibrate method and a startup gate that times out. Treat these as unfinished/static findings, not reproduced failures. [inspected commit](https://github.com/Dean27817/FizzBee-V2/commit/a36fc6525400465ebc1a6011a7c7fda74d6c64b9), [code/src/main.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/main.cpp), [code/src/accel.cpp](https://github.com/Dean27817/FizzBee-V2/blob/a36fc6525400465ebc1a6011a7c7fda74d6c64b9/code/src/accel.cpp).

14. **License and reuse notice.** License: not found in inspected repository metadata/material. Reuse terms are unresolved; a public repository alone is not treated as a license. [repository metadata](https://api.github.com/repos/Dean27817/FizzBee-V2).

<a id="p119"></a>

## P119. Dean27817/Universal-Melty-AIO

1. **Identity, authorship, URLs and visible dates.** Repository owner: Dean27817. Inspected latest default-branch commit credited to dean27817. Repository created 2025-06-05T21:00:32Z (UTC). Inspected commit 60f1a4233163c7a5640a5012d8e3fe3531272d12 dated 2026-01-09T23:24:57Z (UTC). [repository metadata](https://api.github.com/repos/Dean27817/Universal-Melty-AIO); [inspected commit](https://github.com/Dean27817/Universal-Melty-AIO/commit/60f1a4233163c7a5640a5012d8e3fe3531272d12).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [code/src/accel.cpp](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/src/accel.cpp), [code/src/kinimatics.cpp](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/src/kinimatics.cpp), [code/src/main.cpp](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/src/main.cpp), [code/src/reciver.cpp](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/src/reciver.cpp), [code/src/motor.cpp](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/src/motor.cpp), [code/platformio.ini](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/platformio.ini), [README.md](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/README.md). Hardware tests/builds/simulations were not run by this survey. Changes from upstream not established; no verified parent-branch comparison was available/performed.

3. **Robot context and reported status.** Reported intended use: a universal two-accelerometer PCB meant to work in different meltybrain battlebots. This is an author goal; universal compatibility, measured weight and combat results are not established. [README.md](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/README.md).

4. **Hardware and exact parts.** Confirmed: Waveshare ESP32-S3 Zero build target; two LIS331HH 24 g sensors on I2C SDA8/SCL9 at 0x18/0x19; Xbox controller library; motors GPIO10/42, 50 Hz 12-bit LEDC; heading LED GPIO48 and board power output GPIO11. Exact motor/ESC/battery model: not found. [code/platformio.ini](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/platformio.ini), [code/src/accel.cpp](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/src/accel.cpp), [code/src/main.cpp](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/src/main.cpp), [code/src/motor.cpp](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/src/motor.cpp).

5. **Heading sensing and mounting.** Confirmed: two X/Y magnitudes; knownRadius defaults to 0.00313, with secondary foundRadius recalculated during the sensor task. Comments restrict the radius estimator to sensors on the same side of the robot. An actual mechanical mounting drawing/measurement was not inspected. [code/src/main.cpp](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/src/main.cpp), [code/src/accel.cpp](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/src/accel.cpp), [code/src/kinimatics.cpp](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/src/kinimatics.cpp).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed: findAngle integrates mean sqrt(a/r) with millis()-derived dt; 1 kHz sensor ODR. A secondary task reads both sensors, updates angle/radius and yields one RTOS tick; a seqlock publishes angle to the main loop. That task yield and sensor ODR do not establish a measured fixed estimator frequency. Motors use 50 Hz LEDC. [code/src/main.cpp](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/src/main.cpp), [code/src/kinimatics.cpp](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/src/kinimatics.cpp), [code/src/accel.cpp](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/src/accel.cpp), [code/src/motor.cpp](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/src/motor.cpp).

7. **Drift and correction.** Confirmed: live left-stick horizontal changes an angle offset; D-pad up/down adjusts known radius, and runtime sensor task recalculates foundRadius. Share saves tuning. External heading lock and quantified drift performance: not found. [code/src/main.cpp](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/src/main.cpp), [code/src/kinimatics.cpp](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/src/kinimatics.cpp).

8. **Translation timing, phase width and stick mapping.** Confirmed: findMotorSpeeds uses s=sin(currentAngle−stickAngle)×spin, then motor0=spin+s×clamped_translation_magnitude and motor1=−spin+s×clamped_translation_magnitude, clamped ±1. Stick direction comes from atan2. This is continuous sinusoidal modulation, with no narrow square-pulse width parameter in the inspected path. [code/src/kinimatics.cpp](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/src/kinimatics.cpp), [code/src/main.cpp](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/src/main.cpp).

9. **Heading LED/display.** Confirmed: main.cpp calls heading LED onLoop(currentAngle) in melty mode and stopped/error patterns as applicable. LED implementation itself was not read; exact display arc width, physical placement and brightness: not found in inspected evidence. [code/src/main.cpp](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/src/main.cpp).

10. **Calibration and persistence.** Confirmed: kinematics save/load stores knownRadius and foundRadius in a flash config file. Accel::calibrate is empty in the inspected snapshot. A completed stationary offset procedure or actual calibration/test data: not found. [code/src/kinimatics.cpp](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/src/kinimatics.cpp), [code/src/accel.cpp](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/src/accel.cpp).

11. **Controls, modes, arming and failsafe.** Confirmed: without LB, two vertical sticks drive tank at ×0.3; holding LB requests melty at fixed spin=0.3 with right-stick vector translation. Xbox disconnect sends both motors zero and error LED. Xbox button starts OTA; Share saves tuning. Complete fresh-packet or sensor-failure safeguards beyond connection state were not established. [code/src/main.cpp](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/src/main.cpp).

12. **Distinctive ideas and implementation.** Distinctive implementation: nonblocking seqlock snapshot between sensor and main tasks, continuous radius-difference calibration, persistent tuning and Xbox-controlled modes/OTA. The two-sensor model is implemented but its asserted generality is not independently validated. [code/src/main.cpp](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/src/main.cpp), [code/src/kinimatics.cpp](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/src/kinimatics.cpp).

13. **Author-reported problems, failures and evidence limits.** Author-reported hardware failure diary: not found in the short README. Source exposes unfinished work: Accel::calibrate is empty. Other snapshot-specific limitations are stated below; successful sustained heading/translation is not established. [README.md](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/README.md), [code/src/accel.cpp](https://github.com/Dean27817/Universal-Melty-AIO/blob/60f1a4233163c7a5640a5012d8e3fe3531272d12/code/src/accel.cpp).

14. **License and reuse notice.** License: not found in inspected repository metadata/material. Reuse terms are unresolved; a public repository alone is not treated as a license. [repository metadata](https://api.github.com/repos/Dean27817/Universal-Melty-AIO).

<a id="p120"></a>

## P120. royce24864/vibemelt

1. **Identity, authorship, URLs and visible dates.** Repository owner: royce24864. Inspected latest default-branch commit credited to royce24864. Repository created 2026-09-05T07:05:37Z (UTC). Inspected commit eca043a56c48b38c2e75fd61551c12c3db2b3627 dated 2026-09-05T07:05:16Z (UTC). [repository metadata](https://api.github.com/repos/royce24864/vibemelt); [inspected commit](https://github.com/royce24864/vibemelt/commit/eca043a56c48b38c2e75fd61551c12c3db2b3627).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [src/main/Heading.ino](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/src/main/Heading.ino), [src/main/Motor_Control.ino](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/src/main/Motor_Control.ino), [src/main/RC_Handler.ino](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/src/main/RC_Handler.ino), [src/main/main.ino](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/src/main/main.ino), [README.md](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/README.md). Hardware tests/builds/simulations were not run by this survey. Changes from upstream not established; no verified parent-branch comparison was available/performed.

3. **Robot context and reported status.** Reported: Vibemelt ESP32-C3 controller firmware and simulator, crediting AriM224’s kit and skysdottir’s PotatoMelt-ESP32. Exact robot weight, mechanical dimensions, motors and competition outcomes: not found. Documentation describes current source behavior, not an independently verified build. [README.md](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/README.md).

4. **Hardware and exact parts.** Reported/confirmed: XIAO ESP32-C3; H3LIS331DL I2C 0x18 on GPIO6/7; serial iBus RX20; two AM32-compatible DShot300 outputs GPIO21/10; two ten-NeoPixel strips GPIO5/4; battery divider ADC2; 3S/4S configuration. Exact motor/ESC board/receiver model: not found. [README.md](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/README.md), [src/main/main.ino](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/src/main/main.ino).

5. **Heading sensing and mounting.** Confirmed/reported geometry: die offsets X=8.55 mm, Y=12.30 mm, radius≈14.9797 mm. Corrected X/Y are projected on that radial unit vector and absolute value used. Axes are assumed aligned with robot X/Y; no magnetometer/optical/external heading index is used. [README.md](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/README.md), [src/main/Heading.ino](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/src/main/Heading.ino), [src/main/main.ino](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/src/main/main.ino).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed/reported: H3LIS331DL configured ±400 g, 1 kHz ODR, read estimator 400 Hz; median-of-three then EWMA alpha=0.4084. RPM=sqrt(radial_g)/sqrt(g_per_RPM²_per_mm×radius_mm). Motor/phase task at 2 kHz integrates dt×(RPM/rotation_offset)×6°; DShot publishes at 1 kHz. Timing is configured/source-described, not measured by this survey. [src/main/Heading.ino](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/src/main/Heading.ino), [src/main/Motor_Control.ino](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/src/main/Motor_Control.ino), [src/main/main.ino](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/src/main/main.ino), [README.md](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/README.md).

7. **Drift and correction.** Confirmed/reported: open-loop integrated phase uses an interpolated RPM correction table with endpoint clamping; CH4 changes drive-heading phase while LED-only heading offset is separate. Precession remains possible because there is no absolute reference. Quantified hardware drift measurement: not found. [README.md](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/README.md), [src/main/Heading.ino](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/src/main/Heading.ino), [src/main/Motor_Control.ino](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/src/main/Motor_Control.ino).

8. **Translation timing, phase width and stick mapping.** Confirmed/reported: field vector uses atan2(right,forward) and max(abs(X),abs(Y)) magnitude. Two opposing square motor windows start at target phase and +180°; width=percentdecel×3.6°, default 15%=54°. Translation_scale_factor default0.60 scales differential from base, and sign guard prevents reversal. Translation is gated above 400 RPM. No independent motion result is established. [README.md](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/README.md), [src/main/Motor_Control.ino](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/src/main/Motor_Control.ino).

9. **Heading LED/display.** Reported/source-described: dual-strip heading windows, green/cyan phase markers and dark-red translation display, with separate calibrated LED offset. Lower-priority SPI/DMA LED task coalesces frames; high-speed edges may be skipped. Exact physical mounting photographs and measured visibility: not found. [README.md](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/README.md), [src/main/main.ino](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/src/main/main.ino).

10. **Calibration and persistence.** Reported: stationary zero, stable RPM correction points with 750 ms stability gate, LED-only offset and persistent NVS configuration. WiFi drive configurator adjusts translation factor, angular width and acceleration-rate limit. This survey read the firmware/README, not a live device or completed calibration data. [README.md](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/README.md), [src/main/Heading.ino](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/src/main/Heading.ino), [src/main/main.ino](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/src/main/main.ino).

11. **Controls, modes, arming and failsafe.** Confirmed/reported: armed-idle/tank/spin-up/melty/config/WiFi/failsafe/low-battery/sensor-fault states. iBus invalid-frame rejection and 250 ms freshness gate; sensor register health checks; critical battery halt latches until reboot; WiFi forces motor output off. These are source safeguards, not independently exercised tests. [README.md](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/README.md), [src/main/RC_Handler.ino](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/src/main/RC_Handler.ino), [src/main/Motor_Control.ino](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/src/main/Motor_Control.ino), [src/main/main.ino](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/src/main/main.ino).

12. **Distinctive ideas and implementation.** Distinctive source features: radial projection, median+EMA filtering, separate fixed-rate motor task, guarded same-sign translation, RAM circular session logs, local WiFi diagnostics and a Python simulator/robustness suite. The tools are supplied assets; this survey did not run their checks or verify real hardware timing. [README.md](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/README.md), [src/main/Heading.ino](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/src/main/Heading.ino), [src/main/Motor_Control.ino](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/src/main/Motor_Control.ino).

13. **Author-reported problems, failures and evidence limits.** Author-documented limitations: axis clipping is accepted without forcing stop; configured geometry reaches Y-axis mathematical full scale near 5393 RPM, after which heading/RPM become unreliable. NeoPixel rendering can miss high-speed edges; synchronous WiFi requests can starve ordinary parsing. These are documented bounds/concerns, not measured test outcomes here. [README.md](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/README.md).

14. **License and reuse notice.** Repository-level license: not found in inspected metadata/root material. README says bundled libraries retain their own notices; dependency licenses do not establish a license for the controller as a whole. [repository metadata](https://api.github.com/repos/royce24864/vibemelt), [README.md](https://github.com/royce24864/vibemelt/blob/eca043a56c48b38c2e75fd61551c12c3db2b3627/README.md).

<a id="p121"></a>

## P121. TGower/rotation_sensing

1. **Identity, authorship, URLs and visible dates.** Repository owner: TGower. Inspected latest default-branch commit credited to TGower. Repository created 2026-01-11T17:08:15Z (UTC). Inspected commit 585d0a25411233ff8aafb96f5dd6b3d997775a80 dated 2026-05-01T23:00:10Z (UTC). [repository metadata](https://api.github.com/repos/TGower/rotation_sensing); [inspected commit](https://github.com/TGower/rotation_sensing/commit/585d0a25411233ff8aafb96f5dd6b3d997775a80).

2. **Source type, actual inspection and upstream changes.** Primary GitHub repository/code inspection; read README and targeted source excerpts where available. Actual files inspected: [receiver/README.md](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/receiver/README.md), [receiver/main/main.c](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/receiver/main/main.c), [receiver/main/main.h](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/receiver/main/main.h), [sender/main/main.c](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/sender/main/main.c), [README.md](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/README.md). Hardware tests/builds/simulations were not run by this survey. Changes from upstream not established; no verified parent-branch comparison was available/performed.

3. **Robot context and reported status.** Reported: meltybrain/translational-drift combat-robot control using radio-signal variation to infer rotation; README discusses one-wheel simplicity and targets around 3000–6000 RPM, not achieved performance results. Actual robot mass/mechanics/event outcomes: not found. [README.md](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/README.md).

4. **Hardware and exact parts.** Reported: two ESP32-S3 Supermini boards, one sender outside arena and one receiver aboard robot; Android USB-serial app relays Bluetooth gamepad controls; ESP-NOW radio. Confirmed receiver code has DShot ESC GPIO8/9 and LED GPIO48 defaults. Exact motors/ESCs/battery: not found. [README.md](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/README.md), [receiver/main/main.c](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/receiver/main/main.c).

5. **Heading sensing and mounting.** Confirmed/reported: heading sensing uses RSSI variation as the chip antenna rotates relative to sender/obstructions, not an inertial sensor. Receiver supports ESP-NOW or CSI RSSI source selection. Exact antenna orientation/robot mount and multipath environment: not found. [README.md](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/README.md), [receiver/main/main.c](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/receiver/main/main.c), [receiver/main/main.h](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/receiver/main/main.h).

6. **Angle/RPM algorithm, filters, rates and code locations.** Confirmed: linearly interpolate RSSI onto 100 µs grid in a 6000-sample circular buffer. calculate_autocorr_error uses summed absolute differences with SIMD helper; rotation_task searches lags200–<1000 (20–<100 ms), default step5/window1000, then refines a dip. Period=lag×100 µs; rate=1e6/period. Phase uses I/Q demodulation over up to four periods with atan2 and a predicted peak timestamp. A motor/estimator task tick yield is not a measured fixed rate. [receiver/main/main.c](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/receiver/main/main.c).

7. **Drift and correction.** Confirmed: phase comes from radio waveform rather than accumulated accelerometer speed; user phase_offset is applied. Source comments say heading still jumps at times and suggest alternative template/dead-reckoning approaches. No quantitative long-term arena tracking result is established. [receiver/main/main.c](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/receiver/main/main.c).

8. **Translation timing, phase width and stick mapping.** Confirmed: vector direction=atan2(−vy,vx)+π/2; magnitude threshold0.1; selectable square, sine and linear-ramp differential modulation about scaled throttle. Outputs clamp48–1023 for throttle, with low command values stopped; bidirectional support is TODO. Default translation method is square. Separate narrow pulse-width parameter is not found. [receiver/main/main.c](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/receiver/main/main.c), [receiver/main/main.h](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/receiver/main/main.h).

9. **Heading LED/display.** Confirmed: white heading LED for phase π±π/8 (45° total), red when control stale. README proposes the onboard LED for POV. Physical visibility and measured phase-marker accuracy: not found. [receiver/main/main.c](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/receiver/main/main.c), [README.md](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/README.md).

10. **Calibration and persistence.** Confirmed/reported: configuration packets, persistent NVS config and user phase_offset; Android app config UI; receiver can dump buffers to flash for analysis. A full calibrated arena setup procedure or successful calibration result: not found. [README.md](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/README.md), [receiver/main/main.c](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/receiver/main/main.c), [receiver/main/main.h](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/receiver/main/main.h).

11. **Controls, modes, arming and failsafe.** Confirmed: if control age exceeds 1000000 µs, motor task sends DShot zero and red LED. README describes unplugging sender from Android as an emergency communication stop. Packet-level controls/config/telemetry are defined; a complete arming/fault-injection test is not supplied. [receiver/main/main.c](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/receiver/main/main.c), [receiver/main/main.h](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/receiver/main/main.h), [README.md](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/README.md).

12. **Distinctive ideas and implementation.** Distinctive idea: reuse the control radio as the rotation sensor, with high-rate packet RSSI resampling, SIMD period matching, I/Q phase, and configurable motor waveform. Sender rate around6000 Hz is an author statement; it was not measured here. [README.md](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/README.md), [receiver/main/main.c](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/receiver/main/main.c).

13. **Author-reported problems, failures and evidence limits.** Author-reported in code: global autocorrelation minimum often selects a harmonic, motivating a first-real-dip heuristic; I/Q heading sometimes jumps and only remains stable for some time. README discusses reflection/lighting limits of alternative IR sensing as background, not failure evidence of this radio method. [receiver/main/main.c](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/receiver/main/main.c), [README.md](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/README.md).

14. **License and reuse notice.** Receiver/sender main.c headers retain an example-code public-domain-or-CC0 notice. A repository-wide license covering all later application additions was not found; these headers are the available file-level notices, not a completed license audit. [receiver/main/main.c](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/receiver/main/main.c), [sender/main/main.c](https://github.com/TGower/rotation_sensing/blob/585d0a25411233ff8aafb96f5dd6b3d997775a80/sender/main/main.c).

<a id="p122"></a>

## P122. Halo — Spencer Allen and team

1. **Identity/date/URLs:** Reported Halo, Spencer Allen with mechanical partner Pierce; development posts 2018–2022. [Design](https://www.swallenhardware.io/battlebots/2018/4/29/halo-pt-3-the-big-idea).
2. **Source/code inspection:** Builder's technical blog; inline code/algorithm discussion read, repository implementation not read for this entry. [Code architecture](https://www.swallenhardware.io/battlebots/2018/5/23/halo-pt-6-the-code).
3. **Robot:** Reported beetleweight competing at Bugglebots; exact dimensions not found. [Gen 2](https://www.swallenhardware.io/battlebots/2019/5/10/halo-pt-12-gen-2-electronics).
4. **Hardware:** Original custom PCB: Teensy 3.2, XBee Series 1, H3LIS331DL, TSOP75xx IR receiver, five APA102C LEDs, NLSV2T244 translators, TS30015 5V/TPS62172 3.3V regulators; two 750kV outrunners, Readytosky 40A BLHeli ESCs, two 7.4V 2000mAh packs in series. [Electronics](https://www.swallenhardware.io/battlebots/2018/4/29/halo-pt-4-the-electronics). Gen 2 changed to STM32F446RE and analog IR reception using PD333-3B/H0/L2 photodiode. [Gen 2](https://www.swallenhardware.io/battlebots/2019/5/10/halo-pt-12-gen-2-electronics).
5. **Sensing/placement:** Accelerometer mounted at ring wall; radial axis measures centripetal acceleration; vertical axis detects inversion. IR supplies an external directional reference. [Code architecture](https://www.swallenhardware.io/battlebots/2018/5/23/halo-pt-6-the-code).
6. **Angle/RPM/filter/rate:** Original beacon algorithm linearly extrapolates between successive 360° edges. Later version fits a parabola to three edges. Accelerometer integration upgraded from rectangles to trapezoids, with extrapolation between samples and integer-friendly microseconds/degree arithmetic. Exact final rates not found. [Beacon algorithm](https://www.swallenhardware.io/battlebots/2018/6/7/halo-pt-7-improved-algorithms), [accelerometer algorithm](https://www.swallenhardware.io/battlebots/2018/6/30/halo-pt-8-improved-accelerometer-algorithm).
7. **Drift correction:** Beacon is absolute directional reference; accelerometer supports between-edge prediction. Missing beacon edges corrupt period estimates, particularly with the three-edge history. [Beacon algorithm](https://www.swallenhardware.io/battlebots/2018/6/7/halo-pt-7-improved-algorithms).
8. **Translation:** Motors pulsed at heading-dependent times; exact pulse shape/window not established from blog. [Meltybrain explanation](https://www.swallenhardware.io/battlebots/2018/4/29/halo-pt2-meltybrain).
9. **LED:** Persistence-of-vision heading indication; original hardware also intended five-LED text/graphics. [Electronics](https://www.swallenhardware.io/battlebots/2018/4/29/halo-pt-4-the-electronics).
10. **Calibration:** Test stand spin-up/down records paired accelerometer raw counts and beacon-derived period; XBee sends readings through controller USB; Python rejects missed-edge artifacts and curve-fits counts directly to microseconds/degree. One unexplained data artifact was filtered out. [Calibration](https://www.swallenhardware.io/battlebots/2018/8/12/halo-pt-9-accelerometer-calibration).
11. **RC/failsafe:** Idle/tank/spin states; timeout or deadman release commands zero motor speed. Tristating outputs caused ESC anomalies. Tank is actually arcade control. Later automated initial juke and button-triggered forward escape were added. [Architecture](https://www.swallenhardware.io/battlebots/2018/5/23/halo-pt-6-the-code), [Gen 2](https://www.swallenhardware.io/battlebots/2019/5/10/halo-pt-12-gen-2-electronics).
12. **Unusual ideas:** Ring chassis; planned rotational lidar mapping, explicitly untested in Gen 2. [Design](https://www.swallenhardware.io/battlebots/2018/4/29/halo-pt-3-the-big-idea), [Gen 2](https://www.swallenhardware.io/battlebots/2019/5/10/halo-pt-12-gen-2-electronics).
13. **Problems/failures:** Ring-mounted accelerometer expected >300g; direct-drive motor rotor bending loads. Gen 2 analog filter initially oscillated; MCU instability later associated with missing VCAP capacitor and BOOT0 pull-down. Robot Ruckus 2021 saw motor bearing failures, tire wear and cracking battery box. [Design](https://www.swallenhardware.io/battlebots/2018/4/29/halo-pt-3-the-big-idea), [Gen 2](https://www.swallenhardware.io/battlebots/2019/5/10/halo-pt-12-gen-2-electronics), [2021 report](https://www.swallenhardware.io/battlebots/2021/12/10/event-report-robot-ruckus-2021).
14. **Code/license:** Blog links public code; license not verified here. [Code architecture](https://www.swallenhardware.io/battlebots/2018/5/23/halo-pt-6-the-code).

<a id="p123"></a>

## P123. Hit 'N Spin — Spencer Allen

1. **Identity/date/URL:** Reported Hit 'N Spin, Spencer Allen, 3 November 2019. [Build](https://www.swallenhardware.io/battlebots/2019/10/16/hit-n-spin).
2. **Source/code:** Builder blog; code linked, not read here. [Build](https://www.swallenhardware.io/battlebots/2019/10/16/hit-n-spin).
3. **Robot:** Antweight; blade tip 183mm from center, rear guard 108mm. [Build](https://www.swallenhardware.io/battlebots/2019/10/16/hit-n-spin).
4. **Hardware:** One drive wheel, 5mm titanium blade, enclosure printed around blade, integrated FingerTech breaker/15A fuse; Halo-style electronics plus LIS3MDL. [Build](https://www.swallenhardware.io/battlebots/2019/10/16/hit-n-spin).
5. **Sensing:** IR and accelerometer; experimental magnetometer. [Build](https://www.swallenhardware.io/battlebots/2019/10/16/hit-n-spin).
6. **Math/rate:** Pared-down Halo code; reported maximum approximately 1300RPM. Rates not found. [Build](https://www.swallenhardware.io/battlebots/2019/10/16/hit-n-spin).
7. **Drift:** Halo-derived sensing; exact changes not found. [Build](https://www.swallenhardware.io/battlebots/2019/10/16/hit-n-spin).
8. **Translation:** One wheel changes speed across rotation; waveform not found. [Build](https://www.swallenhardware.io/battlebots/2019/10/16/hit-n-spin).
9. **LED:** Top/bottom heading LEDs; no text display. [Build](https://www.swallenhardware.io/battlebots/2019/10/16/hit-n-spin).
10. **Calibration:** Accelerometer recalibrated for new layout. [Build](https://www.swallenhardware.io/battlebots/2019/10/16/hit-n-spin).
11. **RC/failsafe:** Not found for this revision.
12. **Unusual:** Spins initially around blade tip, then around center; blade lifts into one-wheel undercutter operation. [Build](https://www.swallenhardware.io/battlebots/2019/10/16/hit-n-spin).
13. **Failures:** Original magnetometer data unusable; enclosure needed clearance iterations. Later UHMW chassis replaced fragile printed structure; 2021 plastic arena floor allowed spin-up but insufficient traction for translation. [Build](https://www.swallenhardware.io/battlebots/2019/10/16/hit-n-spin), [2021 report](https://www.swallenhardware.io/battlebots/2021/12/10/event-report-robot-ruckus-2021).
14. **License:** Not verified; [repository link](https://github.com/swallenhardware/MeltyHitNSpinV1_1).

<a id="p124"></a>

## P124. Rotating-coil heading experiment — Spencer Allen

1. **Identity/date/URLs:** Builder's separate sensor test rig and intended robot integration, September 2022–April 2023. [Experiment](https://www.swallenhardware.io/battlebots/2022/9/18/magnetometers-for-meltybrains), [failure analysis](https://www.swallenhardware.io/battlebots/2023/1/20/a-magnetometer-collides-with-reality).
2. **Source/code:** Builder technical articles; equations read; standalone code not found/read.
3. **Robot:** Bench proof followed by robot installation; robot weight/class not specified in these articles.
4. **Hardware:** Wound coil, analog amplification/filtering and comparator; example design 3000 turns, 25×38mm area. Actual later coil produced about 4mV at 18Hz, 500Ω. [Experiment](https://www.swallenhardware.io/battlebots/2022/9/18/magnetometers-for-meltybrains).
5. **Sensing:** Earth's field induces voltage as entire coil rotates. [Experiment](https://www.swallenhardware.io/battlebots/2022/9/18/magnetometers-for-meltybrains).
6. **Math/filter:** ε = −NABω cosθ. Considered direct inverse-trig amplitude conversion with slope to disambiguate quadrants; selected comparator zero crossings and interpolation/extrapolation between 180° references. Sample rate not found. [Experiment](https://www.swallenhardware.io/battlebots/2022/9/18/magnetometers-for-meltybrains).
7. **Drift:** Absolute field reference; constant phase offset acceptable, speed-dependent phase lag problematic. [Experiment](https://www.swallenhardware.io/battlebots/2022/9/18/magnetometers-for-meltybrains).
8. **Translation:** Not the scope of rig.
9. **LED:** Not found.
10. **Calibration:** Direct-conversion option normalizes to measured waveform peaks; zero-crossing option avoids amplitude calibration. [Experiment](https://www.swallenhardware.io/battlebots/2022/9/18/magnetometers-for-meltybrains).
11. **RC/failsafe:** Not found.
12. **Unusual:** Uses rapid body rotation to create magnetic signal rather than treating it only as a disturbance. [Experiment](https://www.swallenhardware.io/battlebots/2022/9/18/magnetometers-for-meltybrains).
13. **Failures:** Rig wobble distorted half-turn timings. Robot drive magnets overwhelmed signal; comparator and subsequent analog-sampling/digital-filter attempt failed. Team converted analog front end to IR photodiode immediately before competition. [Experiment](https://www.swallenhardware.io/battlebots/2022/9/18/magnetometers-for-meltybrains), [failure analysis](https://www.swallenhardware.io/battlebots/2023/1/20/a-magnetometer-collides-with-reality).
14. **License:** Not found.

<a id="p125"></a>

## P125. Meltycompass — adaptive-sampling Goertzel experiment, Spencer Allen

1. **Identity/date/URLs:** Reported experimental heading implementation, April–July 2023. [Theory/simulation](https://www.swallenhardware.io/battlebots/2023/4/20/magnetometers-way-forward), [implementation](https://www.swallenhardware.io/battlebots/2023/7/22/magnetometers-software-implementation).
2. **Source/code:** Builder articles/embedded excerpts read; author links [MagnetoMelty](https://gitlab.com/team-mind-melt/magnetomelty) and [magnetometer-investigation branch](https://gitlab.com/team-mind-melt/magnetomelty/-/tree/magnetometer-investigation). Repository code not read here.
3. **Robot:** Intended for author's melties; separate final combat demonstration not found.
4. **Hardware:** RP2040, H3LIS331DL and BMM150. [Theory](https://www.swallenhardware.io/battlebots/2023/4/20/magnetometers-way-forward), [implementation](https://www.swallenhardware.io/battlebots/2023/7/22/magnetometers-software-implementation).
5. **Sensing:** Magnetometer supplies phase; accelerometer supplies current rotation speed to schedule equal-angle samples. Placement not found. [Theory](https://www.swallenhardware.io/battlebots/2023/4/20/magnetometers-way-forward).
6. **Math/filter/rate:** Goertzel extracts target-frequency phase; naive fixed-time sampling fails under acceleration. Adapt rate proportionally to accelerometer speed. H3LIS331DL 1kHz; BMM150 up to 300Hz; 32-sample window; design target 25Hz rotation/300Hz sampling, k=3. Uses Hamming-style window and fixed-point math on RP2040's second core. [Theory](https://www.swallenhardware.io/battlebots/2023/4/20/magnetometers-way-forward), [implementation](https://www.swallenhardware.io/battlebots/2023/7/22/magnetometers-software-implementation).
7. **Drift:** Magnetic phase constrains cumulative integration error; adaptive timing addresses acceleration. Simulations reported around 20° worst-case error in illustrated case, not a general validated bound. [Theory](https://www.swallenhardware.io/battlebots/2023/4/20/magnetometers-way-forward).
8. **Translation:** Not documented in these articles.
9. **LED:** Not found.
10. **Calibration:** Proposed FFT of captured windows to verify target-bin k. [Implementation](https://www.swallenhardware.io/battlebots/2023/7/22/magnetometers-software-implementation).
11. **RC/failsafe:** Not found.
12. **Unusual:** Warps sampling to match fixed coefficients; PIO handles SPI. [Implementation](https://www.swallenhardware.io/battlebots/2023/7/22/magnetometers-software-implementation).
13. **Problems:** Article explicitly warns an unidentified flaw still prevents correct operation; work remains experimental. [Implementation](https://www.swallenhardware.io/battlebots/2023/7/22/magnetometers-software-implementation).
14. **License:** Not verified; [linked branch](https://gitlab.com/team-mind-melt/magnetomelty/-/tree/magnetometer-investigation) inaccessible. Later RP2350 forum experiment identity not established by these2023 posts.

<a id="p126"></a>

## P126. Room-Ba — Joe Earlam / IrregularJoe

1. **Identity/date/URL:** Reported Room-Ba, August–October 2026. [Builder thread](https://forum.bristolbotbuilders.com/t/weaponised-mathematics-the-anatomy-of-a-meltybrain/758).
2. **Source/code:** First-person build/theory log; embedded code read; complete code was pending upload.
3. **Robot:** Small test/combat puck; exact weight not established.
4. **Hardware:** Two salvaged Maxxon brushed motors, PLA-ST chassis, Seeed XIAO RP2040, Flysky FS-A8S iBUS, repurposed Fatal Deviant ESC; later brushless.
5. **Sensing:** H3LIS331DL over I²C at configured radius; exact placement not found.
6. **Math/filter/rate:** RPM = sqrt(g/(radius_mm × 1.118e−6)); below 5g treated stationary. 37Hz sensor low-pass; 20-sample average at 400Hz. **Inferred inconsistency:** that buffer spans 50ms, although author calls it 20ms.
7. **Drift:** Manual radius trim.
8. **Translation:** Opposed triangle/vector waveforms added/subtracted around spin duty; clipped symmetrically. Cosine also tested, with no clear observed difference. Motor-output task 100μs; PWM 16kHz.
9. **LED:** Three pink LEDs/MOSFET powered from 3S; scheduler times 60° flash.
10. **Calibration:** Transmitter knob adjusts effective radius until LED drift stops.
11. **RC/failsafe:** iBUS; steering alters period; failsafe not found.
12. **Unusual:** TaskScheduler; tooth counterbalanced for testing.
13. **Failures:** Incorrect bushing shimming destroyed spare motor; heat persisted with fan features; brushed ESC failure interrupted quantitative comparison.
14. **License:** Not found. All reported details above from [builder thread](https://forum.bristolbotbuilders.com/t/weaponised-mathematics-the-anatomy-of-a-meltybrain/758).

<a id="p127"></a>

## P127. Project LiftOff — Andrew and Jim Kazmer

1. **Identity/date/URL:** Reported development since March 2019. [NHRL technical history](https://wiki.nhrl.io/wiki/index.php?title=Project_LiftOff).
2. **Source/code:** Event-hosted project history, no implementation code read.
3. **Robot:** 3lb, approximately 2000–4000RPM, NHRL.
4. **Hardware:** Latest indexed revision: Teensy 4.0, two H3LIS331DL, SBUS/UART, dShot600 via SPI at 8kHz; PropDrive 2836 1200kV hubmotors, titanium cleat wheels, TPU and AR500.
5. **Sensing:** Dual opposed accelerometers, mounted 45°; no heading IR beacon. Separate active IR sensors detect objects.
6. **Math/rate:** Exact equations not found. Earlier revisions tried MPU6050, then wheel eRPM via bidirectional dShot without accelerometer, then H3LIS331DL.
7. **Drift:** Dual sensors reported to handle shifted center of rotation; exact estimator not found.
8. **Translation:** Exact modulation not found.
9. **LED:** Front/back, top/bottom; green identifies robot-relative front.
10. **Calibration:** Tuning mentioned; procedure not found.
11. **RC/failsafe:** SBUS; failsafe not found.
12. **Unusual:** Multiple materially different estimator/drive revisions; symmetric weapons reduced counterweight-related ricochet.
13. **Failures:** Pointed tooth stuck in walls; thrust bearings, then axles/set screws failed; hub misalignment caused heat/friction. HDPE/UHMW failures prompted TPU.
14. **License:** Not found. All reported details from [NHRL project history](https://wiki.nhrl.io/wiki/index.php?title=Project_LiftOff).

<a id="p128"></a>

## P128. DeepMelt — Team Liftoff

1. **Identity/date/URL:** Reported DeepMelt, debuted November 2022; also fought as Deep Melt-3 in November 2025. [NHRL](https://wiki.nhrl.io/wiki/index.php/DeepMelt).
2. **Source/code:** League project record; no code read.
3. **Robot:** 3lb autonomous meltybrain.
4. **Hardware:** TPU/AR500, two PropDrive 2836 1400kV, 1.55-inch titanium cleat wheels, two 4S 550mAh packs.
5. **Sensing:** Object detection sensors react to surroundings; exact parts and placements not found.
6. **Math/filter/rates:** Not found; do not assume all LiftOff revisions apply.
7. **Drift correction:** Not found.
8. **Translation:** Autonomous behavior reported; exact motor waveform not found.
9. **LED:** Not found in this source.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Fully autonomous fight control reported; arming/override/failsafe not found.
12. **Unusual:** Physically identical to contemporary Project Liftoff but different autonomous program.
13. **Failures:** Engineering failure explanations not found; recorded fights alone do not identify causes.
14. **License:** Not found. All reported details from [NHRL](https://wiki.nhrl.io/wiki/index.php/DeepMelt).

<a id="p129"></a>

## P129. Torment Nexus — Alberta Big Bot Builders

1. **Identity/date/URLs:** Reported team project, RoboGames 2024. [Team](https://tormentnexus.ca/), [recap by Matt Inglot](https://tormentnexus.ca/blog/torment-nexus-robogames-2024-recap).
2. **Source/code:** First-person team site; no code found/read.
3. **Robot:** 60lb; 27lb outer shell. [Recap](https://tormentnexus.ca/blog/torment-nexus-robogames-2024-recap).
4. **Hardware:** VESC-controlled drive, urethane tires, AR500 teeth, aluminum inner motor rails; exact motors/controller model not found. [Recap](https://tormentnexus.ca/blog/torment-nexus-robogames-2024-recap).
5. **Sensing:** Radio displays RPM; sensor type/placement not found.
6. **Math/filter/rate:** Not found.
7. **Drift:** Not found.
8. **Translation:** Team reports translation code still needed refinement at debut. [Recap](https://tormentnexus.ca/blog/torment-nexus-robogames-2024-recap).
9. **LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes:** Spin and ramming modes; current-command throttle made enforcing 1000RPM limit difficult, requiring teammate monitoring telemetry. Failsafe not found. [Recap](https://tormentnexus.ca/blog/torment-nexus-robogames-2024-recap).
12. **Unusual:** Brian Cassin adapted firmware from his Super Nintendo Chalmers antweight. [Team](https://tormentnexus.ca/).
13. **Failures:** Tires detached/jammed motors/melted; motor rails bent on impact. Riveted bicycle tread and steel-wire retention were infeasible; superglue temporarily retained tires. Further hit disabled one drive side. [Recap](https://tormentnexus.ca/blog/torment-nexus-robogames-2024-recap).
14. **License:** Not found.

<a id="p130"></a>

## P130. Super Nintendo Chalmers — Brian Cassin

1. **Identity/date/URL:** Reported Brian Cassin's robot; date not found. [Builder team biography](https://tormentnexus.ca/).
2. **Source/code:** First-person team site; no code read/found.
3. **Robot:** 1lb antweight; competed at Kilobots. [Team biography](https://tormentnexus.ca/).
4. **Hardware:** Not found.
5. **Sensing:** Not found.
6. **Math/filter/rate:** Not found.
7. **Drift:** Not found.
8. **Translation:** Reported meltybrain; algorithm not found. [Team biography](https://tormentnexus.ca/).
9. **LED:** Not found.
10. **Calibration:** Not found.
11. **RC/failsafe:** Not found.
12. **Unusual:** Firmware became basis for Torment Nexus. [Team biography](https://tormentnexus.ca/).
13. **Failures:** Not found; team reports successful competition use without technical performance measures. [Team biography](https://tormentnexus.ca/).
14. **License:** Not found.

<a id="p131"></a>

## P131. Light Seeking Spinner — Dale A. Heatherington

1. **Identity/date/URL:** Reported experimental platform, 31 October 2006. [Builder](https://robots.wa4dsy.net/light-seeking-spinner).
2. **Source/code:** Builder circuit description/schematic; explicitly no microprocessor.
3. **Robot:** Three-wheel proof of translational motion; no combat weight found.
4. **Hardware:** Three CDS photocells, MOSFETs, DPDT relays and series-connected motors.
5. **Sensing:** Each wheel has light-dependent circuit; bright external light supplies absolute direction.
6. **Math/filter/rate:** Analog threshold; no angular estimator or software rate.
7. **Drift:** Direct light response, not integrated heading.
8. **Translation:** Lit sensor reverses its motor; shared series current causes that motor to stall and others accelerate, pivoting around stalled wheel. Repeated angle-dependent stalling moves toward light; reversing all polarities moves away.
9. **LED:** Not found; light is external reference.
10. **Calibration:** Preset light threshold; procedure not found.
11. **RC/failsafe:** No RC in demonstrated prototype. Joystick/microprocessor/directional-radio or IR reference planned.
12. **Unusual:** Analog electromechanical synchronization; phase/duration-controlled reversal was proposed as next step.
13. **Failures:** Not found; successful light following reported, no combat result.
14. **License:** No code; site marks work CC BY-SA 3.0 US. All reported details from [builder](https://robots.wa4dsy.net/light-seeking-spinner).

<a id="p132"></a>

## P132. Small radio-controlled full-body-spinner prototype — Dale Heatherington

1. **Identity/date/URL:** Dale's pre-2007 precursor. [Retrospective](https://robots.wa4dsy.net/scary-go-round).
2. **Source/code:** Builder retrospective; dedicated page unavailable, no code read.
3. **Robot:** Small prototype; weight not found.
4. **Hardware:** 900MHz RC, IR LEDs.
5. **Sensing:** Controller-mounted IR beacon.
6. **Math/filter/rate:** Not found.
7. **Drift:** Beacon reference; details not found.
8. **Translation:** Successful trial reported; timing not found.
9. **LED:** Not found.
10. **Calibration:** Not found.
11. **RC/failsafe:** Failsafe not found.
12. **Unusual:** Intermediate prototype.
13. **Failures:** Reflections reportedly resolved.
14. **License:** Not found. All reported claims: [retrospective](https://robots.wa4dsy.net/scary-go-round).

<a id="p133"></a>

## P133. Scary-Go-Round — Dale Heatherington

1. **Identity/date/URL:** Dale's2007 combat build. [Builder](https://robots.wa4dsy.net/scary-go-round).
2. **Source/code:** Build/test log; no code read.
3. **Robot:** 29.44lb,30-inch diameter; Robot Battles.
4. **Hardware:** Three RC-car drives,24:1,4-inch wheels; relay control.
5. **Sensing:** Central13-inch tower, two sensors0.3 inches apart/cylindrical lens; upward command receiver via threaded Lexan.
6. **Math/filter/rate:** Revolution reference pulse; rejects simultaneous illumination; optional270° inhibit. Rate not found.
7. **Drift:** Controller IR heading reference.
8. **Translation:** Synchronized wheel stalls/acceleration; phase law not found.
9. **LED:** Facing-transmitter diagnostics; tank-front flag.
10. **Calibration:** Simulated0.4s reference for stationary debugging.
11. **RC/failsafe:** Reverse deploys skid under third wheel for tank mode; failsafe not found.
12. **Unusual:** Retracting smart wedges replaced spring bumpers.
13. **Failures:** Springs recoiled robot; floor ridges defeated spinning traversal; loose wire caused competition braking.
14. **License:** Code license not found. All reported claims: [builder](https://robots.wa4dsy.net/scary-go-round).

<a id="p134"></a>

## P134. Spinning Compass — Dale Heatherington

1. **Identity/date/URL:** Reported heading experiment, 24 February 2008. [Builder](https://robots.wa4dsy.net/spinning-compass).
2. **Source/code:** Circuit/test article; no code read.
3. **Robot:** Motorized turntable proof for combat heading, not evidence of a separate fighting robot.
4. **Hardware:** Honeywell HMC1021Z, differential amplifier gain 200, 0.01μF feedback capacitor; comparator AC coupled through 4.7μF.
5. **Sensing:** Sensor rotates in Earth's field.
6. **Math/filter/rate:** Amplified sine; bandwidth below 100Hz; zero crossings intended for CPU interrupt.
7. **Drift:** Magnetic absolute reference; AC coupling removes fixed DC offsets from nearby magnets.
8. **Translation:** Not implemented in shown rig; intended synchronization source.
9. **LED:** Comparator directly drives LED for half-turn visual proof.
10. **Calibration:** Not found.
11. **RC/failsafe:** Not found.
12. **Unusual:** Replaces Scary-Go-Round's limited-range, line-of-sight IR; author also mentions iron-core coil possibility.
13. **Problems:** Switching-current/motor interference and opponent fields remained concerns; steel-floor behavior explicitly unknown. Demonstration establishes bench LED behavior only.
14. **License:** No code found; site work CC BY-SA 3.0 US. All reported details from [builder](https://robots.wa4dsy.net/spinning-compass).

<a id="p135"></a>

## P135. Lobotomi — Dylan Park / Georgia Tech RoboJackets

1. **Identity/date/URL:** Reported v1.0, 2025. [Team wiki](https://wiki.robojackets.org/Lobotomi).
2. **Source/code:** Builder organization wiki; OpenMelt2 linked, implementation not read here.
3. **Robot:** Beetleweight; April 2025 in-house event heading appears but results remain placeholders.
4. **Hardware:** INJORA 540 55T brushed motor, HUF76423P3 35A N-channel MOSFET plus Arduino Micro; RadioMaster ER4 ELRS and Pocket ELRS; OVONIC 2S 1000mAh.
5. **Sensing:** Position sensing required; actual sensor not specified.
6. **Math/filter/rate:** Not found for this robot; OpenMelt2 named as control software.
7. **Drift:** Not found.
8. **Translation:** Reported intended controlled translation; specific output implementation not found.
9. **LED:** Not found.
10. **Calibration:** Not found.
11. **RC/failsafe:** ELRS hardware above; configuration/failsafe not found.
12. **Unusual:** Concrete brushed MOSFET implementation of OpenMelt2.
13. **Failures:** Not found; problems section is an unfilled template, not evidence of no problems.
14. **License:** Robot code license not found/verified. All reported details from [team wiki](https://wiki.robojackets.org/Lobotomi).

<a id="p136"></a>

## P136. DangerCone — UCLA ASME 2016–2017

1. **Identity/date/URL:** Reported 2016–17 flagship by seven ASME members; source author Disha Samaiyar built scaled control prototype. [Portfolio](https://www.dishasamaiyar.com/dangercone).
2. **Source/code:** Team-member portfolio with manufacturing photos; no code read/found.
3. **Robot:** 60lb, intended RoboGames San Mateo; 1400RPM was an expectation, not reported measurement.
4. **Hardware:** Steel outer shells with rubber tread grooves, 7075 aluminum center, bearing/shaft assemblies; exact electrical components not found.
5. **Sensing:** Not found.
6. **Math/filter/rate:** Not found.
7. **Drift:** Not found.
8. **Translation:** Meltybrain control intended to combine shell-wheel rotation and translation; algorithm not found.
9. **LED:** Not found.
10. **Calibration:** Not found.
11. **RC/failsafe:** Not found.
12. **Unusual:** Cylindrical shells serve as weapons and wheels; interlocking center. **Inferred possible alias/shared project:** same school year and distinctive design as Barrel Roll below; relationship not explicitly established.
13. **Failures:** Not found; assembled hardware shown, competition/control success not established by source.
14. **License:** Not found. All reported details from [team-member portfolio](https://www.dishasamaiyar.com/dangercone).

<a id="p137"></a>

## P137. Barrel Roll — UCLA ASME, Ryan's portfolio

1. **Identity/date/URL:** Reported 2016–17 flagship; team of six under Sean Oh. [Portfolio](https://ryanp543.github.io/portfolio/barrelroll/).
2. **Source/code:** Participant's design/manufacturing account; no code found/read.
3. **Robot:** Weight not specified on this page; no competition result found.
4. **Hardware:** 4140 steel shells, 7075 aluminum cores, custom motor/gearbox casings; spherical and needle bearings; motor/controller models not found.
5. **Sensing:** Not found.
6. **Math/filter/rate:** Not found.
7. **Drift:** Not found.
8. **Translation:** Author reports meltybrain control; no method or measurement provided.
9. **LED:** Not found.
10. **Calibration:** Not found.
11. **RC/failsafe:** Not found.
12. **Unusual:** Counterrotating cylindrical arms; jigsaw center joint distributes impact load; wedged center self-righting geometry. **Inferred possible alias/shared project with DangerCone:** retained separately as requested; not confirmed distinct physical robots.
13. **Failures:** Not found; FEA/shaft shortening discusses breakage prevention, not a documented test failure.
14. **License:** Not found. All reported details from [participant portfolio](https://ryanp543.github.io/portfolio/barrelroll/).

<a id="p138"></a>

## P138. Disperse — William / Team UR (translational drift planned only)

1. **Identity/date/URL:** MKI/MKII, July–October2025. [Builder](https://forum.bristolbotbuilders.com/t/disperse-a-dumb-meltybrain-build-log/521).
2. **Source/code:** Log; code unread.
3. **Robot:** 150g; GROCS/Bristol Ant Social.
4. **Hardware:** DYS BE1806 2300kV, LEGO tire, Malenki Nano, BBB20A ESC,2S300mAh; MKII2205/larger tire.
5. **Sensing:** Not found.
6. **Math/filter/rate:** Not found.
7. **Drift:** Not implemented.
8. **Translation:** Future plan; documented robot spins without timed translation.
9. **LED:** Not found.
10. **Calibration:** Not found.
11. **RC/failsafe:** Unidirectional ESC trapped robot in corner; failsafe not found.
12. **Unusual:** One-wheel design; dovetail module joint.
13. **Failures:** Weapon snapped, tire detached, counterbores failed; lifting attributed to gyroscopic effects by author.
14. **License:** CAD license unchecked. Reported claims: [builder](https://forum.bristolbotbuilders.com/t/disperse-a-dumb-meltybrain-build-log/521).

# Additional NHRL entries with sparse public methods

The league [meltybrain category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners) lists the following additional names. These are separate source records. Category membership establishes the league classification only; it does not prove working translation or a distinct chassis. Individual pages were retrieved where the text below supplies details; several others were unavailable through the research tool. No hardware, tuning or code is inferred from name or appearance.

<a id="p139"></a>

## P139. (Liftoff)² — NHRL record

1. **Identity/date/URLs:** Reported (Liftoff)²; author/team not found; date not found. [Project page](https://wiki.nhrl.io/wiki/index.php?title=%28Liftoff%29%C2%B2); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League category inspected; individual methods page not accessible/available; no code found/read.
3. **Weight/size/competition:** Not found.
4. **Hardware:** Not found.
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Category-only evidence; detailed implementation not found.
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p140"></a>

## P140. AC/RC — NHRL record

1. **Identity/date/URLs:** Reported AC/RC; author/team Alex K and Richie C (drivers); date March/December 2021. [Project page](https://wiki.nhrl.io/wiki/index.php?title=AC%2FRC); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League-hosted record; no code found/read.
3. **Weight/size/competition:** 12lb; NHRL [League page](https://wiki.nhrl.io/wiki/index.php?title=AC%2FRC).
4. **Hardware:** Wood/aluminum body, two wheels; electrical parts not found. [League page](https://wiki.nhrl.io/wiki/index.php?title=AC%2FRC).
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** League calls weapon a vertiginous mass accelerator; category supplies melty classification. [League page](https://wiki.nhrl.io/wiki/index.php?title=AC%2FRC).
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p141"></a>

## P141. Alicorn — NHRL record

1. **Identity/date/URLs:** Reported Alicorn; author/team not found; date March 2025. [Project page](https://wiki.nhrl.io/wiki/index.php?title=Alicorn); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League-hosted record; no code found/read.
3. **Weight/size/competition:** 3lb; NHRL [League page](https://wiki.nhrl.io/wiki/index.php?title=Alicorn).
4. **Hardware:** Not found.
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Meltybrain Spinner recorded; method not found. [League page](https://wiki.nhrl.io/wiki/index.php?title=Alicorn).
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p142"></a>

## P142. Ankle-breaker (II) — NHRL record

1. **Identity/date/URLs:** Reported Ankle-breaker (II); author/team Erli Ye; date 2023. [Project page](https://wiki.nhrl.io/wiki/index.php?title=Ankle-breaker_%28II%29); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League-hosted record; no code found/read.
3. **Weight/size/competition:** 3lb; NHRL [League page](https://wiki.nhrl.io/wiki/index.php?title=Ankle-breaker_%28II%29).
4. **Hardware:** 2WD; other parts not found. [League page](https://wiki.nhrl.io/wiki/index.php?title=Ankle-breaker_%28II%29).
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Page labels horizontal spinner while category labels meltybrain; exact method unresolved. [League page](https://wiki.nhrl.io/wiki/index.php?title=Ankle-breaker_%28II%29).
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p143"></a>

## P143. Brian — NHRL record

1. **Identity/date/URLs:** Reported Brian; author/team not found; date March 30, 2024. [Project page](https://wiki.nhrl.io/wiki/index.php?title=Brian); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League-hosted record; no code found/read.
3. **Weight/size/competition:** 3lb; NHRL [League page](https://wiki.nhrl.io/wiki/index.php?title=Brian).
4. **Hardware:** Not found.
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Indexed historical page has two forfeits and no hardware; current category identifies meltybrain. No performance inferred. [League page](https://wiki.nhrl.io/wiki/index.php?title=Brian).
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p144"></a>

## P144. Doom — NHRL record

1. **Identity/date/URLs:** Reported Doom; author/team not found; date not found. [Project page](https://wiki.nhrl.io/wiki/index.php?title=Doom); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League category inspected; individual methods page not accessible/available; no code found/read.
3. **Weight/size/competition:** Not found.
4. **Hardware:** Not found.
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Category-only evidence; detailed implementation not found.
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p145"></a>

## P145. Emotional Trauma — NHRL record

1. **Identity/date/URLs:** Reported Emotional Trauma; author/team not found; date not found. [Project page](https://wiki.nhrl.io/wiki/index.php?title=Emotional_Trauma); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League category inspected; individual methods page not accessible/available; no code found/read.
3. **Weight/size/competition:** Not found.
4. **Hardware:** Not found.
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Category-only evidence; detailed implementation not found.
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p146"></a>

## P146. Flip N' Cut — NHRL record

1. **Identity/date/URLs:** Reported Flip N' Cut; author/team Andrew Kazmer / Team Liftoff; date 2020–2023. [Project page](https://wiki.nhrl.io/wiki/index.php?title=Flip_N%27_Cut); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League-hosted record; no code found/read.
3. **Weight/size/competition:** 3lb; NHRL [League page](https://wiki.nhrl.io/wiki/index.php?title=Flip_N%27_Cut).
4. **Hardware:** TPU/AR500; 2× PropDrive 2836 1000kV; 1.55-inch titanium cleat wheels; 2×4S550mAh LiPo. [League page](https://wiki.nhrl.io/wiki/index.php?title=Flip_N%27_Cut).
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Reported flying-wedge meltybrain with modified TPU shell/teeth; intended to get under opponents and toss them. Do not assume LiftOff firmware details. [League page](https://wiki.nhrl.io/wiki/index.php?title=Flip_N%27_Cut).
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p147"></a>

## P147. Flip-N-Cut 12 — NHRL record

1. **Identity/date/URLs:** Reported Flip-N-Cut 12; author/team not found; date not found. [Project page](https://wiki.nhrl.io/wiki/index.php?title=Flip-N-Cut_12); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League category inspected; individual methods page not accessible/available; no code found/read.
3. **Weight/size/competition:** Not found.
4. **Hardware:** Not found.
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Category-only evidence; detailed implementation not found.
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p148"></a>

## P148. Hockii — NHRL record

1. **Identity/date/URLs:** Reported Hockii; author/team GT RoboJackets; date March 2023 / April 2025. [Project page](https://wiki.nhrl.io/wiki/index.php?title=Hockii); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League-hosted record; no code found/read.
3. **Weight/size/competition:** 12lb; NHRL [League page](https://wiki.nhrl.io/wiki/index.php?title=Hockii).
4. **Hardware:** League page leaves hardware blank; see Hocki project description below. [League page](https://wiki.nhrl.io/wiki/index.php?title=Hockii).
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Likely related to Hocki (inferred from team/name/class); exact revision identity not established. [League page](https://wiki.nhrl.io/wiki/index.php?title=Hockii).
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p149"></a>

## P149. Jerry — NHRL record

1. **Identity/date/URLs:** Reported Jerry; author/team not found; date August 10, 2019. [Project page](https://wiki.nhrl.io/wiki/index.php?title=Jerry); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League-hosted record; no code found/read.
3. **Weight/size/competition:** 3lb; NHRL [League page](https://wiki.nhrl.io/wiki/index.php?title=Jerry).
4. **Hardware:** Not found.
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** League page includes meltybrain category; algorithm not found. [League page](https://wiki.nhrl.io/wiki/index.php?title=Jerry).
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p150"></a>

## P150. Karoomba — NHRL record

1. **Identity/date/URLs:** Reported Karoomba; author/team not found; date September 14, 2024. [Project page](https://wiki.nhrl.io/wiki/index.php?title=Karoomba); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League-hosted record; no code found/read.
3. **Weight/size/competition:** 3lb; NHRL [League page](https://wiki.nhrl.io/wiki/index.php?title=Karoomba).
4. **Hardware:** Not found.
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** League explicitly labels meltybrain; algorithm not found. [League page](https://wiki.nhrl.io/wiki/index.php?title=Karoomba).
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p151"></a>

## P151. Katrina — NHRL record

1. **Identity/date/URLs:** Reported Katrina; author/team not found; date not found. [Project page](https://wiki.nhrl.io/wiki/index.php?title=Katrina); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League category inspected; individual methods page not accessible/available; no code found/read.
3. **Weight/size/competition:** Not found.
4. **Hardware:** Not found.
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Category-only evidence; detailed implementation not found.
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p152"></a>

## P152. LiftOff — NHRL record

1. **Identity/date/URLs:** Reported LiftOff; author/team not found; date not found. [Project page](https://wiki.nhrl.io/wiki/index.php?title=LiftOff); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League category inspected; individual methods page not accessible/available; no code found/read.
3. **Weight/size/competition:** Not found.
4. **Hardware:** Not found.
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Category-only evidence; detailed implementation not found.
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p153"></a>

## P153. Little Melty — NHRL record

1. **Identity/date/URLs:** Reported Little Melty; author/team not found; date January 20, 2024. [Project page](https://wiki.nhrl.io/wiki/index.php?title=Little_Melty); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League-hosted record; no code found/read.
3. **Weight/size/competition:** 3lb; NHRL [League page](https://wiki.nhrl.io/wiki/index.php?title=Little_Melty).
4. **Hardware:** Not found.
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** League explicitly labels meltybrain; algorithm not found. [League page](https://wiki.nhrl.io/wiki/index.php?title=Little_Melty).
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p154"></a>

## P154. Lobotomizer Prime — NHRL record

1. **Identity/date/URLs:** Reported Lobotomizer Prime; author/team not found; date not found. [Project page](https://wiki.nhrl.io/wiki/index.php?title=Lobotomizer_Prime); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League category inspected; individual methods page not accessible/available; no code found/read.
3. **Weight/size/competition:** Not found.
4. **Hardware:** Not found.
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Category-only evidence; detailed implementation not found.
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p155"></a>

## P155. Marceline — NHRL record

1. **Identity/date/URLs:** Reported Marceline; author/team not found; date not found. [Project page](https://wiki.nhrl.io/wiki/index.php?title=Marceline); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League category inspected; individual methods page not accessible/available; no code found/read.
3. **Weight/size/competition:** Not found.
4. **Hardware:** Not found.
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Category-only evidence; detailed implementation not found.
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p156"></a>

## P156. Neether — NHRL record

1. **Identity/date/URLs:** Reported Neether; author/team not found; date not found. [Project page](https://wiki.nhrl.io/wiki/index.php?title=Neether); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League category inspected; individual methods page not accessible/available; no code found/read.
3. **Weight/size/competition:** Not found.
4. **Hardware:** Not found.
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Category-only evidence; detailed implementation not found.
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p157"></a>

## P157. Omnipotence — NHRL record

1. **Identity/date/URLs:** Reported Omnipotence; author/team not found; date not found. [Project page](https://wiki.nhrl.io/wiki/index.php?title=Omnipotence); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League category inspected; individual methods page not accessible/available; no code found/read.
3. **Weight/size/competition:** Not found.
4. **Hardware:** Not found.
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Category-only evidence; detailed implementation not found.
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p158"></a>

## P158. OpenHELL — NHRL record

1. **Identity/date/URLs:** Reported OpenHELL; author/team not found; date not found. [Project page](https://wiki.nhrl.io/wiki/index.php?title=OpenHELL); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League category inspected; individual methods page not accessible/available; no code found/read.
3. **Weight/size/competition:** Not found.
4. **Hardware:** Not found.
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Category-only evidence; detailed implementation not found.
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p159"></a>

## P159. OrbitR and RotatR — NHRL record

1. **Identity/date/URLs:** Reported OrbitR and RotatR; author/team not found; date May 3, 2025. [Project page](https://wiki.nhrl.io/wiki/index.php?title=OrbitR_and_RotatR); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League-hosted record; no code found/read.
3. **Weight/size/competition:** 3lb; NHRL [League page](https://wiki.nhrl.io/wiki/index.php?title=OrbitR_and_RotatR).
4. **Hardware:** Not found.
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Listed together as one league entry; no assumption that this is one physical chassis. [League page](https://wiki.nhrl.io/wiki/index.php?title=OrbitR_and_RotatR).
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p160"></a>

## P160. Project LiftOff-12 — NHRL record

1. **Identity/date/URLs:** Reported Project LiftOff-12; author/team not found; date March 2, 2024. [Project page](https://wiki.nhrl.io/wiki/index.php?title=Project_LiftOff-12); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League-hosted record; no code found/read.
3. **Weight/size/competition:** 12lb; NHRL [League page](https://wiki.nhrl.io/wiki/index.php?title=Project_LiftOff-12).
4. **Hardware:** Not found.
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Explicit meltybrain; estimator details not found. [League page](https://wiki.nhrl.io/wiki/index.php?title=Project_LiftOff-12).
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p161"></a>

## P161. Project LiftOff-30 — NHRL record

1. **Identity/date/URLs:** Reported Project LiftOff-30; author/team Jim Kazmer; date March 2, 2024. [Project page](https://wiki.nhrl.io/wiki/index.php?title=Project_LiftOff-30); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League-hosted record; no code found/read.
3. **Weight/size/competition:** 30lb; NHRL [League page](https://wiki.nhrl.io/wiki/index.php?title=Project_LiftOff-30).
4. **Hardware:** 2WD; other exact components not found. [League page](https://wiki.nhrl.io/wiki/index.php?title=Project_LiftOff-30).
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Two recorded forfeits establish registration, not demonstrated translation. [League page](https://wiki.nhrl.io/wiki/index.php?title=Project_LiftOff-30).
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p162"></a>

## P162. R.U.D. — NHRL record

1. **Identity/date/URLs:** Reported R.U.D.; author/team not found; date not found. [Project page](https://wiki.nhrl.io/wiki/index.php?title=R.U.D.); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League category inspected; individual methods page not accessible/available; no code found/read.
3. **Weight/size/competition:** Not found.
4. **Hardware:** Not found.
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Category-only evidence; detailed implementation not found.
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p163"></a>

## P163. Scramble — NHRL record

1. **Identity/date/URLs:** Reported Scramble; author/team not found; date April 2025. [Project page](https://wiki.nhrl.io/wiki/index.php?title=Scramble); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League-hosted record; no code found/read.
3. **Weight/size/competition:** 12lb; NHRL [League page](https://wiki.nhrl.io/wiki/index.php?title=Scramble).
4. **Hardware:** Not found.
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Explicit meltybrain; algorithm not found. [League page](https://wiki.nhrl.io/wiki/index.php?title=Scramble).
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p164"></a>

## P164. Sir Pops A Lot — NHRL record

1. **Identity/date/URLs:** Reported Sir Pops A Lot; author/team not found; date not found. [Project page](https://wiki.nhrl.io/wiki/index.php?title=Sir_Pops_A_Lot); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League category inspected; individual methods page not accessible/available; no code found/read.
3. **Weight/size/competition:** Not found.
4. **Hardware:** Not found.
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Category-only evidence; detailed implementation not found.
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p165"></a>

## P165. Spin-a-ma-thing — NHRL record

1. **Identity/date/URLs:** Reported Spin-a-ma-thing; author/team Ethan Barrieau; date September 18, 2021. [Project page](https://wiki.nhrl.io/wiki/index.php?title=Spin-a-ma-thing); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League-hosted record; no code found/read.
3. **Weight/size/competition:** 3lb; NHRL [League page](https://wiki.nhrl.io/wiki/index.php?title=Spin-a-ma-thing).
4. **Hardware:** 2WD; other exact components not found. [League page](https://wiki.nhrl.io/wiki/index.php?title=Spin-a-ma-thing).
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Explicit meltybrain; algorithm not found. [League page](https://wiki.nhrl.io/wiki/index.php?title=Spin-a-ma-thing).
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p166"></a>

## P166. T T — NHRL record

1. **Identity/date/URLs:** Reported T T; author/team not found; date not found. [Project page](https://wiki.nhrl.io/wiki/index.php?title=T_T); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League category inspected; individual methods page not accessible/available; no code found/read.
3. **Weight/size/competition:** Not found.
4. **Hardware:** Not found.
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Category-only evidence; detailed implementation not found.
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p167"></a>

## P167. The arena floor — NHRL record

1. **Identity/date/URLs:** Reported The arena floor; author/team not found; date not found. [Project page](https://wiki.nhrl.io/wiki/index.php?title=The_arena_floor); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League category inspected; individual methods page not accessible/available; no code found/read.
3. **Weight/size/competition:** Not found.
4. **Hardware:** Not found.
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Category-only evidence; detailed implementation not found.
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p168"></a>

## P168. The Greatest Challenge — NHRL record

1. **Identity/date/URLs:** Reported The Greatest Challenge; author/team Team Alfredo; Jacob Williams / Julian Berla drivers; date 2022/2024. [Project page](https://wiki.nhrl.io/wiki/index.php?title=The_Greatest_Challenge); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League-hosted record; no code found/read.
3. **Weight/size/competition:** 3lb; NHRL [League page](https://wiki.nhrl.io/wiki/index.php?title=The_Greatest_Challenge).
4. **Hardware:** 6061 aluminum, Emax ECO II 2807 1300kV, 2WD, 950mAh4S LiPo. [League page](https://wiki.nhrl.io/wiki/index.php?title=The_Greatest_Challenge).
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Exact control implementation not found; keep separate from The Greatest Danger. [League page](https://wiki.nhrl.io/wiki/index.php?title=The_Greatest_Challenge).
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p169"></a>

## P169. The Greatest Danger — NHRL record

1. **Identity/date/URLs:** Reported The Greatest Danger; author/team Team Alfredo; Jacob Williams / Julian Berla drivers; date 2021–2022. [Project page](https://wiki.nhrl.io/wiki/index.php?title=The_Greatest_Danger); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League-hosted record; no code found/read.
3. **Weight/size/competition:** 3lb; NHRL / Motorama photo [League page](https://wiki.nhrl.io/wiki/index.php?title=The_Greatest_Danger).
4. **Hardware:** 6061 aluminum, Emax ECO II 2807 1300kV, 2WD, 950mAh4S LiPo. [League page](https://wiki.nhrl.io/wiki/index.php?title=The_Greatest_Danger).
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Exact control implementation not found; keep separate from The Greatest Challenge. [League page](https://wiki.nhrl.io/wiki/index.php?title=The_Greatest_Danger).
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p170"></a>

## P170. Ti Grrr — NHRL record

1. **Identity/date/URLs:** Reported Ti Grrr; author/team not found; date not found. [Project page](https://wiki.nhrl.io/wiki/index.php?title=Ti_Grrr); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League category inspected; individual methods page not accessible/available; no code found/read.
3. **Weight/size/competition:** Not found.
4. **Hardware:** Not found.
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Category-only evidence; detailed implementation not found.
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p171"></a>

## P171. Wheel of Misfortune — NHRL record

1. **Identity/date/URLs:** Reported Wheel of Misfortune; author/team not found; date not found. [Project page](https://wiki.nhrl.io/wiki/index.php?title=Wheel_of_Misfortune); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League category inspected; individual methods page not accessible/available; no code found/read.
3. **Weight/size/competition:** Not found.
4. **Hardware:** Not found.
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Category-only evidence; detailed implementation not found.
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

<a id="p172"></a>

## P172. WhirlWax — NHRL record

1. **Identity/date/URLs:** Reported WhirlWax; author/team not found; date not found. [Project page](https://wiki.nhrl.io/wiki/index.php?title=WhirlWax); [league category](https://wiki.nhrl.io/wiki/index.php?title=Category%3AMeltybrain_Spinners).
2. **Source/code:** League category inspected; individual methods page not accessible/available; no code found/read.
3. **Weight/size/competition:** Not found.
4. **Hardware:** Not found.
5. **Heading sensing/placement:** Not found.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing/mapping:** Not found.
9. **Heading LED:** Not found.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Ideas/status:** Category-only evidence; detailed implementation not found.
13. **Builder problems/failures:** Not found; match outcomes do not identify engineering causes.
14. **Code/license:** Not found; league text license is not a code license.

# Further builder and historical records

<a id="p173"></a>

## P173. Take Cover — Gareth Barnaby

1. **Identity/date/URL:** Reported builder log, 10 October 2018. [Builder](https://community.robotshop.com/robots/show/take-cover-translational-drift-featherweight-fighting-robot).
2. **Source/code:** First-person build log; code not read/found.
3. **Robot:** 13.7kg featherweight; Insomnia events.
4. **Hardware:** Two sensored 1200W200kV skateboard hubmotors, VESCs, custom STM32F4 board; nylon stack, approximately 8kg steel bar.
5. **Sensing:** Accelerometer; part/placement not found.
6. **Math/filter/rate:** Rotation speed from acceleration; exact estimator/rate not found.
7. **Drift:** Not found.
8. **Translation:** Reverses drives during selected rotational sectors; exact windows not found.
9. **LED:** High-power POV LED marks phase zero.
10. **Calibration:** Tinkering reported, procedure not found.
11. **RC/failsafe:** Conventional drive and translational spin modes; six-channel receiver interface; failsafe not found.
12. **Unusual:** Board also used in Nuts2; CAN, optoisolated PPM, UART/I²C/SPI.
13. **Failures:** PLA wheels melted; silicone-hose tires rapidly wore. Centrifugal load depressed reset switch. Circlip loss caused motor/wheel rubbing and heat. VESC braking-before-reversal impeded control.
14. **License:** Not found. All reported details from [builder](https://community.robotshop.com/robots/show/take-cover-translational-drift-featherweight-fighting-robot).

<a id="p174"></a>

## P174. TRAC — Gareth Barnaby

1. **Identity/date/URL:** Reported revision after Take Cover, posted November 2018, updated May 2019. [Builder](https://community.robotshop.com/robots/show/trac-my-second-meltybrain-featherweight-fighting-robot).
2. **Source/code:** Builder log; no code read/found.
3. **Robot:** 13.7kg featherweight; Extreme Robots Portsmouth.
4. **Hardware:** Two 3350W crop-drone BLDC motors, added rear magnetic encoders, VESCs, Melty-arm PCB; ABS fan wheels, Polycraft FC8000 tires, thrust bearings, layered nylon chassis.
5. **Sensing:** Rotor encoders aid commutation; body-heading sensing not specified here.
6. **Math/filter/rate:** Not found.
7. **Drift:** Not found.
8. **Translation:** Builder reports working before tuning; waveform not found.
9. **LED:** Not found.
10. **Calibration:** Tuning planned; details not found.
11. **RC/failsafe:** Very sensitive ordinary steering reported; failsafe not found.
12. **Unusual:** Wheel turbine fans/air scoops intended to cool motors; approximately 53cm single-tooth/counterweight bar, 7.9kg.
13. **Failures:** Air in first molded tires made them brittle. Initial test destroyed ESC and MCU; replacement and reduced current limits restored drive. Impact-broken encoder/ESC wires immobilized both debut fights.
14. **License:** Not found. All reported details from [builder](https://community.robotshop.com/robots/show/trac-my-second-meltybrain-featherweight-fighting-robot).

<a id="p175"></a>

## P175. Nuts 2 — Rory Mangles / Team Nuts

1. **Identity/date/URLs:** Reported designed/built by Rory Mangles. [Builder's professional project account](https://uk.linkedin.com/in/rory-mangles-28329285).
2. **Source/code:** Builder account and controller builder's related project log; no Nuts2 code read/found.
3. **Robot:** Robot Wars competitor; exact primary-source weight not recovered. [Official specs currently inaccessible](https://www.robotwars.tv/competitors/season-10/week-4/nuts-2/).
4. **Hardware:** Gareth Barnaby identifies Take Cover's custom STM32F4 controller as the one used in Nuts2; cannot assume Take Cover's motors or complete electronics were shared. [Controller builder](https://community.robotshop.com/robots/show/take-cover-translational-drift-featherweight-fighting-robot).
5. **Heading sensing/placement:** Not established for Nuts2.
6. **Angle/RPM/filter/rate:** Not found.
7. **Drift correction:** Not found.
8. **Translation timing:** Builder reports motor-control system enabled movement while spinning; exact sectors not found. [Builder](https://uk.linkedin.com/in/rory-mangles-28329285).
9. **Heading LED:** Not established by accessible primary text.
10. **Calibration:** Not found.
11. **RC/modes/failsafe:** Not found.
12. **Unusual:** Builder reports custom electronics/mechanics and SketchUp design. [Builder](https://uk.linkedin.com/in/rory-mangles-28329285).
13. **Problems/failures:** Not found in accessible primary sources; secondary traction reports not treated as builder evidence here.
14. **Code/license:** Not found.

<a id="p176"></a>

## P176. Nuts 1 — Rory Mangles / Team Nuts (predecessor; meltybrain unconfirmed)

1. **Identity/date/URL:** Builder reports designing and constructing Nuts 1 and 2. [Rory Mangles](https://uk.linkedin.com/in/rory-mangles-28329285).
2. **Source/code:** Builder professional account; no code read/found.
3. **Robot:** Robot Wars predecessor; exact specifications not recovered from primary source.
4. **Hardware:** Not found.
5. **Sensing/placement:** Not found.
6. **Math/filter/rate:** Not found.
7. **Drift:** Not found.
8. **Translation:** Not established. Builder specifically associates meltybrain operation with Nuts2, so Nuts1 must not be described as a demonstrated meltybrain. [Builder](https://uk.linkedin.com/in/rory-mangles-28329285).
9. **LED:** Not found.
10. **Calibration:** Not found.
11. **RC/failsafe:** Not found.
12. **Unusual:** Contextual predecessor, retained separately; no claimed translational-drift completion.
13. **Failures:** Not found.
14. **License:** Not found.

<a id="p177"></a>

## P177. Hocki — Georgia Tech RoboJackets

1. **Identity/date/URL:** Team project led by Varun Madabushi with Juan Elizondo and Afshan Chandani; April 2021 article. [Team](https://robojackets.org/2021/04/07/hocki-a-new-kind-of-battlebot/).
2. **Source/code:** Organization technical feature; code not read.
3. **Robot:** 12lb; planned 3600RPM, not validated full-speed result.
4. **Hardware:** Teensy4.1 at600MHz; four accelerometers, two IR sensors, one magnetometer; exact sensor models not found.
5. **Placement:** Accelerometers near center of mass; IR/LED/radio toward perimeter.
6. **Math/filter/rate:** Hybrid Extended Kalman Filter; acceleration→angular speed→orientation. Exact loop rate not found; microsecond-scale goal.
7. **Drift:** Redundant sensing and opposing 0°/180° arena IR beacons; signal-strength discrimination needed.
8. **Translation:** Far-side wheel faster, near-side slower, equal at parallel alignment; reverses rule when inverted.
9. **LED:** Top LED band shows heading.
10. **Calibration:** Not found.
11. **RC/failsafe:** Driver spin-speed and motion-direction inputs; failsafe not found.
12. **Unusual:** MATLAB simulations before hardware; sensor fusion includes motor commands.
13. **Problems:** Saturation, low magnetometer rate, beacon ambiguity, balance and packaging constraints; full-system testing still planned in article.
14. **License:** Not found. All reported details from [team](https://robojackets.org/2021/04/07/hocki-a-new-kind-of-battlebot/). Hockii league entry above may be later revision; identity link is inferred.

<a id="p178"></a>

## P178. Herr Gepoünden — Team Zwölfpack

1. **Identity/date/URLs:** Opponent's firsthand 2024 recap identifies team and meltybrain operation. [Recap](https://tormentnexus.ca/blog/torment-nexus-robogames-2024-recap).
2. **Source/code:** Firsthand opponent account and event results; no builder implementation or code recovered.
3. **Robot:** 60lb class at RoboGames2024. [Event record](https://rank.robocore.net/history/2292).
4. **Hardware:** Hammer/linkage described; exact electrical parts not found. [Recap](https://tormentnexus.ca/blog/torment-nexus-robogames-2024-recap).
5. **Sensing:** Not found.
6. **Math/filter/rate:** Not found.
7. **Drift:** Not found.
8. **Translation timing:** Not found; opponent account establishes spinning engagement, not its estimator.
9. **LED:** Not found.
10. **Calibration:** Not found.
11. **RC/failsafe:** Not found.
12. **Unusual:** Historical and 2024 identity represented by one source entry; no assumed unchanged controller.
13. **Failures:** A hammer linkage detached in the described impact; cause not independently diagnosed. [Recap](https://tormentnexus.ca/blog/torment-nexus-robogames-2024-recap).
14. **License:** Not found.

<a id="p179"></a>

## P179. Y-POUT — Team Whyachi

1. **Identity/date/URL:** Primary team roster lists retired Y-POUT; date not found. [Team](https://whyachi.com/bots/).
2. **Source/code:** Builder roster plus external RioBotz textbook description, pp188–189; not builder-verified; no code read.
3. **Robot:** Heavyweight. [Team](https://whyachi.com/bots/).
4. **Hardware:** Textbook describes three powered wheels spaced120°, steering rods and cam on ground-referenced NavBot. [External description](https://www.evvaa.com/images/riobotz_combot_tutorial.pdf).
5. **Sensing:** Mechanical NavBot retains orientation; no electronic sensor details found. [Textbook](https://www.evvaa.com/images/riobotz_combot_tutorial.pdf).
6. **Math/filter/rate:** Textbook models sinusoidal ±3° wheel steering, phases120° apart; electronic update rate inapplicable to described cam. [Textbook](https://www.evvaa.com/images/riobotz_combot_tutorial.pdf).
7. **Drift:** Not found.
8. **Translation:** Cam cyclically steers wheels; textbook gives translation speed v·sin3°, tied to wheel speed. Exact build settings unverified. [Textbook](https://www.evvaa.com/images/riobotz_combot_tutorial.pdf).
9. **LED:** Not found.
10. **Calibration:** Not found.
11. **RC/failsafe:** Not found.
12. **Unusual:** Ground-referenced mechanical steering; shared textbook explanation does not establish identical construction to Why Not.
13. **Failures:** Not found.
14. **License:** Not found.

<a id="p180"></a>

## P180. Why Not — Team Whyachi

1. **Identity/date/URL:** Primary roster lists retired Why Not; date not found. [Team](https://whyachi.com/bots/).
2. **Source/code:** Builder roster; [historical team technical PDF](https://web.archive.org/web/20160806030703/http://www.teamwhyachi.com:80/Why-not1.pdf) inaccessible in this check; no code read.
3. **Robot:** Middleweight. [Team](https://whyachi.com/bots/).
4. **Hardware:** RioBotz textbook describes three120° powered wheels with cam-linked steering rods. Exact parts not found. [External description](https://www.evvaa.com/images/riobotz_combot_tutorial.pdf).
5. **Sensing:** Textbook describes floor-referenced NavBot orientation, not an electronic heading estimate. [Textbook](https://www.evvaa.com/images/riobotz_combot_tutorial.pdf).
6. **Math/filter/rate:** External textbook describes ±3° cyclic steering; exact build settings unverified. [Textbook](https://www.evvaa.com/images/riobotz_combot_tutorial.pdf).
7. **Drift:** Not found.
8. **Translation:** Textbook derives translation from varying wheel steering angles through cam phase; not builder-verified here. [External description](https://www.evvaa.com/images/riobotz_combot_tutorial.pdf).
9. **LED:** Not found.
10. **Calibration:** Not found.
11. **RC/failsafe:** Not found.
12. **Unusual:** Mechanical reference method; retained separately from Y-POUT. Team PDF inaccessible, external description explicitly attributed.
13. **Failures:** Not found.
14. **License:** Not found.

<a id="p181"></a>

## P181. CycloneBot — CM Robotics / Michael Worry and team

1. **Identity/date/URL:** October2004 firsthand event report and builder interviews. [Kevin Morris](https://www.eejournal.com/article/20041012_cyclonebot/).
2. **Source/code:** Contemporary reporting, observed demonstrations and builder explanations; no code read.
3. **Robot:** 220lb, near700RPM at 2004 RFL Nationals. [Report](https://www.eejournal.com/article/20041012_cyclonebot/).
4. **Hardware:** Altera Cyclone FPGA/Nios development board, custom DSP, Linksys802.11, two MC1HV controllers; 2:1 gearing, six-inch wheels, four SLA batteries, half-inch titanium. Later builder interview reports replacing two Eteks with four long Magmotors/Whyachi gearboxes and Odyssey24V supply. [2004](https://www.eejournal.com/article/20041012_cyclonebot/), [2008 interview, pp23–24](https://www.scribd.com/document/122502774/Servo-2008-02).
5. **Sensing:** Magnetometer originally between motors; quadrature wheel encoders. [2004](https://www.eejournal.com/article/20041012_cyclonebot/).
6. **Math/filter/rate:** DSP fuses filtered magnetic data and encoder signals; encoder resolution0.4°. Equations/rate not found. [2004](https://www.eejournal.com/article/20041012_cyclonebot/).
7. **Drift:** Magnetic reference; floor interference improved by relocating sensor onto raised shell mounting. [2004](https://www.eejournal.com/article/20041012_cyclonebot/).
8. **Translation:** Torque increased at desired travel tangent, decreased opposite; waveform not specified. [2004](https://www.eejournal.com/article/20041012_cyclonebot/).
9. **LED:** Side columns display timed messages (TauntWare); heading display not specified. [2004](https://www.eejournal.com/article/20041012_cyclonebot/).
10. **Calibration:** Lock after three rotations through eight compass directions. [2004](https://www.eejournal.com/article/20041012_cyclonebot/).
11. **RC/failsafe:** Laptop USB joystick/WiFi, telemetry and backup tank mode; timeout not found. [2004](https://www.eejournal.com/article/20041012_cyclonebot/).
12. **Unusual:** Hardware DSP plus soft processor. [2004](https://www.eejournal.com/article/20041012_cyclonebot/).
13. **Failures:** Battery internal busbar fractured; floor confused magnetic lock; RF lead sheared. Later builder reports battery chemistry failures and motor magnets dislodging. [2004](https://www.eejournal.com/article/20041012_cyclonebot/), [interview](https://www.scribd.com/document/122502774/Servo-2008-02).
14. **License:** Not found.

<a id="p182"></a>

## P182. Blade Runner 1 — Ilya Polyakov / Team Carnivore

1. **Identity/date/URL:** Builder retrospective published February2008. [Interview, p23](https://www.scribd.com/document/122502774/Servo-2008-02).
2. **Source/code:** Builder's contributed recollections, reproduced magazine issue; no code read.
3. **Robot:** BattleBots predecessor; exact specifications not found here.
4. **Hardware:** Not found.
5. **Sensing:** Not found.
6. **Math/filter/rate:** Not found.
7. **Drift:** Not found.
8. **Translation:** Planned meltybrain ancestry; builder reports mostly pushbot operation with sideways thwacking. Implemented translational drift not established. [Interview](https://www.scribd.com/document/122502774/Servo-2008-02).
9. **LED:** Not found.
10. **Calibration:** Not found.
11. **RC/failsafe:** Not found.
12. **Unusual:** Builder explains that a teammate's reaction to the mathematics supplied the “melty brain” name. [Interview](https://www.scribd.com/document/122502774/Servo-2008-02).
13. **Failures:** Not found for this version.
14. **License:** Not found.

<a id="p183"></a>

## P183. Blade Runner 2 — Ilya Polyakov / Team Carnivore (unfinished controller)

1. **Identity/date/URL:** Builder retrospective, February2008. [Interview, pp23–24](https://www.scribd.com/document/122502774/Servo-2008-02).
2. **Source/code:** Builder interview reproduced in magazine scan; no code read.
3. **Robot:** 120lb middleweight. [Interview](https://www.scribd.com/document/122502774/Servo-2008-02).
4. **Hardware:** Kevlar monocoque, two four-inch Magmotors; motors/batteries approximately80lb. [Interview](https://www.scribd.com/document/122502774/Servo-2008-02).
5. **Sensing:** Not found.
6. **Math/filter/rate:** Not found.
7. **Drift:** Not found.
8. **Translation:** Builder explicitly says no time remained to implement meltybrain; competed unfinished. [Interview](https://www.scribd.com/document/122502774/Servo-2008-02).
9. **LED:** Not found.
10. **Calibration:** Not found.
11. **RC/failsafe:** Not found.
12. **Unusual:** Structural and armor functions combined in composite shell. [Interview](https://www.scribd.com/document/122502774/Servo-2008-02).
13. **Failures:** Kevlar mount alignment consumed schedule; wheel retention and combat damage also reported. [Interview](https://www.scribd.com/document/122502774/Servo-2008-02).
14. **License:** Not found.

<a id="p184"></a>

## P184. ZAP — Team Bolt / Team Panic (2022 application design)

1. **Identity/date/URL:** Team Panic's March5 2022 application video. [Video](https://www.youtube.com/watch?v=DLCBpzJVusE).
2. **Source/code:** Indexed creator video description and builder replies; video frames/transcript not inspected, direct page fetch failed; no code read.
3. **Robot:** Planned250lb dual-spinner meltybrain for BattleBots. Completed heavyweight performance not established. [Creator description](https://www.youtube.com/watch?v=DLCBpzJVusE).
4. **Hardware:** Electronics placement still in CAD and tight; exact MCU/sensors not found. [Builder replies](https://www.reddit.com/r/battlebots/comments/t76bs8/team_bolts_2022_application_zap/).
5. **Sensing:** Not found.
6. **Math/filter/rate:** Not found.
7. **Drift:** Not found.
8. **Translation:** Design described as meltybrain; timing/window not found. [Creator](https://www.youtube.com/watch?v=DLCBpzJVusE).
9. **LED:** Not found.
10. **Calibration:** Not found.
11. **RC/failsafe:** Not found.
12. **Unusual:** Separate spinning weapons on a planned translational-drift platform; shock mounting intended, weapon structures also protective. [Creator](https://www.youtube.com/watch?v=DLCBpzJVusE), [builder](https://www.reddit.com/r/battlebots/comments/t76bs8/team_bolts_2022_application_zap/).
13. **Problems:** Builder reports earlier applications rejected and requested evidence of competitiveness; final motor positioning remained changeable. These are development/application issues, not evidence of tested mechanical failure. [Builder](https://www.reddit.com/r/battlebots/comments/t76bs8/team_bolts_2022_application_zap/).
14. **License:** Not found.

<a id="p185"></a>

## P185. Pac-Attac — RoboWarner / Warner

1. **Identity/date/URL:** Builder account, original2021 and versions through5. [Project](https://robowarner.com/portfolio/pac-attac-1lb-meltybrain/).
2. **Source/code:** Technical blog read; downloadable Arduino file linked but fetch failed, code not read.
3. **Robot:** 1lb antweight; builder reported approximately1600RPM in2021. [Builder discussion](https://www.reddit.com/r/battlebots/comments/nf2wtj/).
4. **Hardware:** Original Arduino Nano, MPU6050, FlySky iBUS, MOSFET drivers; V3–5 ESP8266 custom PCB, V5 dual16g/200g sensors. BR2207S2200kV eventually selected. [Project/comments](https://robowarner.com/portfolio/pac-attac-1lb-meltybrain/).
5. **Sensing:** Acceleration, manual period or one-wheel reflective tachometer; comparator cutoff adjustable. MPU6050 near center keeps readings below16g. [Project](https://robowarner.com/portfolio/pac-attac-1lb-meltybrain/), [builder](https://www.reddit.com/r/battlebots/comments/nf2wtj/).
6. **Math/filter/rate:** Average100 samples, acceleration→rotations/sec, integrate elapsed microseconds; V5 sensor switching around1500RPM. Rate not found. [Project](https://robowarner.com/portfolio/pac-attac-1lb-meltybrain/).
7. **Drift:** RC angular correction; no external beacon. [Project](https://robowarner.com/portfolio/pac-attac-1lb-meltybrain/).
8. **Translation:** Each motor on180°; left vertical spin speed, right horizontal heading, right vertical binary forward command. [Project](https://robowarner.com/portfolio/pac-attac-1lb-meltybrain/).
9. **LED:** Animated Pac-Man mouth, later COB strip/RGB status; central always-powered armed indicator. [Project](https://robowarner.com/portfolio/pac-attac-1lb-meltybrain/).
10. **Calibration:** Copier-motor test platform at1044RPM; formal procedure not found. [Project](https://robowarner.com/portfolio/pac-attac-1lb-meltybrain/).
11. **RC/failsafe:** FlySky ten-channel iBUS; failsafe not found. [Project](https://robowarner.com/portfolio/pac-attac-1lb-meltybrain/).
12. **Unusual:** Multiple selectable period sources and dual-range accelerometry. [Project](https://robowarner.com/portfolio/pac-attac-1lb-meltybrain/).
13. **Failures:** Sunlight obscured animated mouth, changed to heading line; wall impact weakened/detached tooth. [Builder](https://www.reddit.com/r/battlebots/comments/nf2wtj/).
14. **License:** Not found; [linked code](https://robowarner.com/wp-content/uploads/2021/05/pacAttacVer2.ino) unread.

<a id="p186"></a>

## P186. Pong — Backslash Robotics (translation unconfirmed)

1. **Identity/date/URL:** Version1 retired; competed2025. [Builder](https://backslashrobotics.com/pong).
2. **Source/code:** Builder hardware/CAD page; no code found/read.
3. **Robot:** 1lb plastic class, actual0.902lb, diameter145mm. [Builder](https://backslashrobotics.com/pong).
4. **Hardware:** FingerTech S2838 inrunner, MB30020 20A ESC, OVONIC3S1000mAh80C, Flysky FS2A four-channel, FingerTech Mini Power Switch; SuperPLA+ shell/freewheel and95A TPU drivewheel. [Builder](https://backslashrobotics.com/pong).
5. **Sensing:** Not found; no heading sensor/controller listed.
6. **Math/filter/rate:** Not found.
7. **Drift:** Not found.
8. **Translation:** Builder calls it meltybrain/full-body spinner; actual controlled translational drift not established by page. [Builder](https://backslashrobotics.com/pong).
9. **LED:** Not found.
10. **Calibration:** Not found.
11. **RC/failsafe:** Receiver above; control modes and failsafe not found.
12. **Unusual:** Single drive motor and freewheel; reused electronics from Vasilis1.0/Hyphen1.0. [Builder](https://backslashrobotics.com/pong).
13. **Failures:** Severe motor overheating; ribbed mount designed for airflow. [Builder](https://backslashrobotics.com/pong).
14. **License:** Not found.

<a id="p187"></a>

## P187. Unnamed UofT meltybrain — Nirmal Arunkumar / Combat Robotics Association

1. **Identity/date/URL:** Author leads eight-person UofT meltybrain subteam; robot name/project date not found. [Portfolio](https://nirmalarunkumar.github.io/).
2. **Source/code:** Builder portfolio technical account; code not read. Identity overlap with other UofT repositories unresolved.
3. **Robot:** Reported built, targeting3000+RPM; weight/dimensions not found. Target is not measured speed. [Portfolio](https://nirmalarunkumar.github.io/).
4. **Hardware:** ATmega32U4, H3LIS331DL±400g over I2C; four-layer2oz PCB rated20A continuous, thermal vias,4S LiPo telemetry, printed chassis. [Portfolio](https://nirmalarunkumar.github.io/).
5. **Placement:** Not found.
6. **Math/filter/rate:** Centripetal RPM;50Hz PID Kp0.3/Ki0.2/Kd0.1; Timer3 loop2kHz, Timer1 DShot500Hz. Heading integration details not found. [Portfolio](https://nirmalarunkumar.github.io/).
7. **Drift:** EEPROM correction-table interpolation reported for RPM, not an established absolute heading correction. [Portfolio](https://nirmalarunkumar.github.io/).
8. **Translation:** Translational drift claimed; waveform/window/mapping not found. [Portfolio](https://nirmalarunkumar.github.io/).
9. **LED:** Not found.
10. **Calibration:** Two-point zero-g calibration and EEPROM-persisted correction table with linear interpolation. [Portfolio](https://nirmalarunkumar.github.io/).
11. **RC/failsafe:** Transmitter targetRPM, stale-checksum3s timeout, hardware watchdog, two-tier battery monitoring. [Portfolio](https://nirmalarunkumar.github.io/).
12. **Unusual:** Explicit separate estimator/control/communication timing. [Portfolio](https://nirmalarunkumar.github.io/).
13. **Failures:** Not found.
14. **License:** Not found.

<a id="p188"></a>

## P188. Persistence of Memory — Meditative Resistance

1. **Identity/date/URLs:** Named team in December2025 event registration; implementation described by local event organization. [Registration](https://www.robotcombatevents.com/events/6230/competitions/6791), [SCAR](https://www.socalattackrobots.com/30lb-featherweight.html).
2. **Source/code:** Event-organizer submitted robot showcase; code not read here. Cross-reference separate [Persistence of Memory code project](https://github.com/jkadin/persistence_of_memory); source/platform entry does not independently verify repository-to-build correspondence. Registration indexed, direct fetch403.
3. **Robot:** 30lb, approximately2000RPM reported. [SCAR](https://www.socalattackrobots.com/30lb-featherweight.html).
4. **Hardware:** Two Flipsky5048 200kV,75100VESC, two6S4400mAh batteries in series,7.5lbAR600 steel ring; laser-cut steel/UHMW/carbon fiber. [SCAR](https://www.socalattackrobots.com/30lb-featherweight.html).
5. **Sensing:** Not found.
6. **Math/filter/rate:** Not found.
7. **Drift:** Not found.
8. **Translation:** Organization identifies meltybrain; exact modulation/mapping not found. VESC listed as drive hardware does not prove where heading estimation runs. [SCAR](https://www.socalattackrobots.com/30lb-featherweight.html).
9. **LED:** Top clock display, hands indicate heading and translation directions. [SCAR](https://www.socalattackrobots.com/30lb-featherweight.html).
10. **Calibration:** Not found.
11. **RC/failsafe:** Not found.
12. **Unusual:** Melting-clock theme references Dalí's painting. [SCAR](https://www.socalattackrobots.com/30lb-featherweight.html).
13. **Failures:** Not found.
14. **License:** Not found.

---

# Search exclusions, dead links and inaccessible material

**Confirmed dead links:** none conclusively established by this survey. Failed retrievals below were skipped for substantive code claims unless another accessible primary source independently supplied the information.

### Excluded name matches

- **satriobio/openmelt** — R Shiny app for high-resolution-melting experiment analysis, including HRM instrument support and clustering; this is a molecular-analysis name match, not a meltybrain robot controller. [readme.md](https://github.com/satriobio/openmelt/blob/a6463bb4edc30d58d2a36e11eb9027fafc6a610f/readme.md); [repository metadata](https://api.github.com/repos/satriobio/openmelt).

- **Julianzz/openmelt** — Rust project whose Chinese README discusses unified storage for logs, metrics and traces; this is an observability-storage name match, not a meltybrain robot controller. [README.md](https://github.com/Julianzz/openmelt/blob/16cda5c26cdcdcf0314da8654013a99c5f721b7e/README.md); [repository metadata](https://api.github.com/repos/Julianzz/openmelt).

### Missing/inaccessible material and inspection limits

All assigned repository metadata endpoints were accessible. These scoped file lookups returned no README/source content; that is distinct from an inaccessible repository:

- rtforsy/openmelt — `README.md` not found at inspected ref. [repository metadata](https://api.github.com/repos/rtforsy/openmelt).

- acklenx/openmelt — `README.md` not found at inspected ref. [repository metadata](https://api.github.com/repos/acklenx/openmelt).

- qbnut/openmelt — `README.md` not found at inspected ref. [repository metadata](https://api.github.com/repos/qbnut/openmelt).

- gentry-atkinson/openmelt — `README.md` not found at inspected ref. [repository metadata](https://api.github.com/repos/gentry-atkinson/openmelt).

- dinoceros/The-Wheel-of-Power — `README.md` not found at inspected ref. [repository metadata](https://api.github.com/repos/dinoceros/The-Wheel-of-Power).

- SaintSampo/The-Wheel-of-Power — `README.md` not found at inspected ref. [repository metadata](https://api.github.com/repos/SaintSampo/The-Wheel-of-Power).

- TomasSiauliaiNights/openmelty — `README.md` not found at inspected ref. [repository metadata](https://api.github.com/repos/TomasSiauliaiNights/openmelty).

- TomasSiauliaiNights/Openmeltyy — empty repository; no commit/source/README was returned. [repository metadata](https://api.github.com/repos/TomasSiauliaiNights/Openmeltyy).


No hardware run, compilation, simulator execution or fault injection was performed. Reported numerical targets, configured sensor rates and expected behavior are not relabeled as achieved measurements. License summaries identify the notices/metadata found; they do not audit contributions, dependencies or all repository assets.

# Access notes and unresolved leads

These are observed access limitations, not claims that the linked material is dead. Indexed excerpts were used only where explicitly described above. No inaccessible code was counted as read.

- [Dale's small RC full-body spinner](https://robots.wa4dsy.net/full-body-spinner): fetch failed; retrospective builder account provides limited evidence.
- [Old CycloneBot technical page](https://www.maccanikill.com/MacCanIKill-Cyclone.html): cache miss; contemporary interview/report recovered elsewhere.
- [Original Melty B page](https://www.spambutcher.com/meltyb.html): cache miss. Other agents cover OpenMelt/Melty B code.
- [Team Whyachi historical technical PDF](https://web.archive.org/web/20160806030703/http://www.teamwhyachi.com:80/Why-not1.pdf): archive fetch unavailable. [Original](http://www.teamwhyachi.com/Why-not1.pdf) also inaccessible in this check. Mechanical description above is explicitly external textbook evidence.
- [Official Nuts2 profile](https://www.robotwars.tv/competitors/season-10/week-4/nuts-2/): robots.txt access limitation.
- [Hocki team article](https://robojackets.org/2021/04/07/hocki-a-new-kind-of-battlebot/): direct opening503; indexed full technical text read.
- [ZAP application video](https://www.youtube.com/watch?v=DLCBpzJVusE) and [later creator video](https://www.youtube.com/watch?v=XIvKi9H8dbU): direct fetch failed. Only recovered creator description and replies support entry.
- [Pac-Attac Arduino file](https://robowarner.com/wp-content/uploads/2021/05/pacAttacVer2.ino): cache miss, code not inspected.
- [Dual Differential RPM Sensing](https://www.servomagazine.com/magazine/article/dual-dif_ferential_rpm_sensing_or_a_melty_brain_translational_drift_robot), June2010: subscriber body inaccessible; no detailed algorithm inferred from title/teaser.
- [Brushless.zone 2023 article](https://brushless.zone/2023/06/16/): timeout; no substantive claims taken from it.
- [Beyblade of Death HackClub project](https://blueprint.hackclub.com/projects/1039): cache miss in this subtask; parent survey has separately retrieved indexed creator material.
- Recoil/Bambi lead: no primary meltybrain implementation evidence recovered; no project entry inferred from the names alone.


## Parent researcher access notes and exclusions

- [cstoker2/altimeter](https://github.com/cstoker2/altimeter): repository metadata describes meltybrain code based on melontype, but inspected `altimeter2026_v2/altimeter2026_v2.ino` and `notes.h` implement rocket altitude/launch/apogee/brake/latch logging on Pico2 with ICM20649 and BMP3XX. A meltybrain control implementation was not established in those files. Preserve this as a conflicting-metadata lead, excluded from melty project count. Earlier versions were not exhaustively audited.
- [GitLab MagnetoMelty README](https://gitlab.com/team-mind-melt/magnetomelty/-/blob/main/README.md) returned a loading shell; raw URL returned cache miss. Shell page accessible: not a confirmed dead link.
- [Codeberg](https://codeberg.org/) searches were blocked by robots.txt; no source contents retrieved. Not a dead link.
- Public-host direct network fallback failed DNS resolution for GitLab in the local shell. This is an environment access restriction, not evidence that GitLab is down.
- [MTSU thesis landing handle](https://jewlscholar.mtsu.edu/handle/mtsu/8699) could not be reopened; indexed abstract and direct bitstream were available. Do not call the thesis deleted.
- [Beyblade of Death](https://blueprint.hackclub.com/projects/1039) was available as indexed primary-page text during initial search but later direct fetches failed/cache-missed. The record is limited to the retrieved journal excerpt, not code review or video inspection.
- Additional searches for GitLab, Codeberg, Bitbucket, SourceForge and the phrase TD spinner produced either blocked hosts or irrelevant lexical matches. No matching project should be inferred from irrelevant results.


## Research validation record

- Every indexed record has fourteen separately numbered fields in the requested order.
- Index labels and anchors are checked against the detailed sections.
- Forks remain separate, including unchanged/behind forks; matching trees and compare results are stated only where inspected.
- Missing and unfinished implementations are retained. Source inspection findings are not represented as reproduced physical faults.
- Names that might be aliases, source/platform overlaps and planned-only melty conversions are explicitly qualified.
- Source-derived summaries were reviewed for shared-page budgets and short quotation limits. No complete external articles or codebases are reproduced.
- This is a research deliverable. It makes no claim that listed failsafes, sensor ranges, motor waveforms or autonomous behaviors are safe, effective or competition-approved on a new build.
