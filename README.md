# Icarus: UKSEDS National Rocketry Championship 2026-27

**Kent Icarus** is a student rocketry team from the **University of Kent**, entered by the **Kent Engineering Society (KES)** in the **UKSEDS National Rocketry Championship (NRC) 2026-27**. This repository is the team's full project record, organised by subsystem: propulsion and simulation, structures, recovery, payload, avionics, firmware, systems engineering and design reviews, and supporting documentation.

> **Status:** Project kickoff (November 2026). Roles are assigned and the design phase is starting. Specifications below are placeholders until the competition requirements and our design are confirmed.

<!-- ![Icarus rocket](Figures/rocket.png) -->
<!-- ![Team Logo](Figures/Icarus_logo.png) -->

## Mission

*To be confirmed against the 2026-27 NRC rules.*

- **Target apogee:** 2000ft
- **Payloads:** competition customer payload (CPD) and the team's own rideshare payload (RPD), TBD
- **Data:** record flight data on-board and recover it after flight
- **Recovery:** safe recovery within the competition landing radius
- **Safety:** full compliance with UKSEDS NRC safety rules

## Team

University of Kent; entered by the Kent Engineering Society (KES).

| Name | Role | Course |
| --- | --- | --- |
| Calum Lewis | Team Captain / Payload Lead / Systems & Integration | Stage 3 Electrical and Electronic Engineering |
| Mubarak Ladipo | Vice Captain / Avionics Lead / Structures | Stage 3 Electronic and Computer Engineering |
| Grace Ezeh | Project Manager / Documentation & Reviews / Avionics | Stage 3 Bioengineering |
| Lucian Willcock | Propulsion & Simulation Lead / Payload | Stage 2 Physics with Astrophysics |
| Rishabesh Suthaar | Firmware & Software Lead / Payload / Outreach | Stage 3 Electrical and Electronic Engineering |
| Alex Murphy | Structures Lead / Recovery Lead | Stage 2 Mechanical Engineering |
| Yonghua (Lucas) Liao | Structures Lead / Propulsion | Stage 2 Mechanical Engineering |
| Hussein Alrodan | Firmware / Recovery Electronics | Stage 3 Electronic and Computer Engineering |
| Sadan Adnan | Avionics / Firmware | Stage 3 Electronic and Computer Engineering |

Roles are a starting point, not fixed boundaries; people are encouraged to work across subsystems.

## Subsystems

Each subsystem has its own folder. Owners and scope are below; design details will be added as they are developed.

**Systems** (`Systems/`; Calum, Grace). Mission definition, requirement compliance matrix, mass, power and financial budgets, interface definitions, the integration test plan, and design review submissions.

**Propulsion & Simulation** (`Propulsion/`; Lucian, Lucas). Motor selection, thrust-curve analysis, motor mount, and the OpenRocket model covering apogee, stability and descent rates, kept current as the build changes.

**Structures** (`Structures/`; Alex, Lucas, Mubarak). Body tube, nose cone, fins, couplers and bulkheads; CAD, manufacturing and load testing.

**Recovery** (`Recovery/`; Alex, Hussein). Parachute sizing, deployment system, flight computer deployment logic and ground ejection testing.

**Payload** (`Payload/`; Calum, Lucian, Risha). Rideshare payload design and customer payload integration, mechanical and electrical.

**Avionics** (`Avionics/`; Mubarak, Sadan, Grace). Custom PCB, sensors, data logging and power design.

**Firmware** (`Firmware/`; Risha, Hussein, Sadan). Code for avionics and payload, sensor reading, logging, flight event handling, and post-flight data processing and plotting.

## Lessons carried over from AstraNova (NRC 2025-26)

Several members flew with UKC AstraNova last year. The key lessons from that flight shape this design from the start:

- **Do not rely on a single accelerometer threshold for apogee.** AstraNova's rocket pitched over at apogee instead of falling vertically, so a freefall-based deploy trigger never fired. Apogee detection and deployment need redundant, cross-checked conditions (e.g. barometric descent plus timer backup).
- **Size power with real headroom.** AstraNova's data logger browned out because the battery ran close to its discharge limit with no bulk capacitance for transients. Budget peak current, not just steady draw, and test the full power system under load.
- **Plan for a motor change.** AstraNova flew on a substitute motor it hadn't been simulated for. Simulate backup motor options so the design has margin either way.
- **Ground-test the full recovery chain** before flight, from the flight computer to the ejection charge.

See the AstraNova repository and its post-mortem for full details.

## Timeline

*Dates to be confirmed against the UKSEDS schedule.*

| Milestone | Target |
| --- | --- |
| Team kickoff | November 2026 |
| Preliminary design | TBD |
| Critical Design Review (CDR) | 19th February |
| Manufacturing Review (MR) | 10th April |
| Flight Readiness Review (FRR) | 2nd June |
| Launch | 22nd June |

## Quick specs

| Parameter | Value |
| --- | --- |
| Competition | UKSEDS National Rocketry Championship 2026-27 |
| University | University of Kent |
| Target apogee | 2000ft |
| Motor | TBD |
| Airframe | TBD |
| Length / mass | TBD |
| Stability | TBD |
| Rail exit speed | TBD |
| Recovery | TBD |
| Avionics MCU | TBD |
| Battery | TBD |

## Repository structure

```
Avionics/        flight electronics, PCB design, power
Payload/         rideshare payload and customer payload integration
Firmware/        avionics and payload code, data processing scripts
Propulsion/      motor selection, mount, OpenRocket model
Recovery/        recovery system design and deployment testing
Structures/      airframe, nose cone, fins, bulkheads
Systems/         requirements, budgets, interfaces, test plans
Documentation/   design reviews (CDR, MR, FRR) and design notes
Outreach/        outreach, sponsorship and media
Figures/         photos and renders used in the README
LICENSE
README.md
```

## Supporters

- Kent Engineering Society (KES)
- University of Kent School of Engineering lab technicians
- Nathan Brabon: PCB manufacturing and code design support

## License

Released under the MIT License; see [`LICENSE`](LICENSE).
