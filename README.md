Note: This was a conceptual/on-paper design project and was not physically built or flight-tested. The focus was on feasibility analysis and system design.
# BlackPanther-F450-Banner-Drone
The BlackPanther F450 Banner Towing UAV is a low-speed advertising platform designed to tow a lightweight banner while maintaining stability under high-drag payload conditions. The project focuses on aerodynamic stability, low-speed control optimization, and safe autonomous operation.

**Project Objectives**


* To design a UAV which can tow a banner at very low speeds (≈0.8–1.2 m/s)
* To keep the UAV stable in spite of the aerodynamic drag and dynamic effect of the payload
* To perform repeat missions between A and B autonomously
* To include safety features in the UAV, especially for demo purposes


**Key Engineering Learnings**

* The effect of banner drag on endurance is considerable even at low speeds

* The thrust margin is a critical parameter for high-drag payload missions

* Tow line damping reduces oscillatory instability

* Mission planning must include battery reserve margins

**System Architecture**

**Frame:**

* **BlackPanther F450** (450 x 450 mm)

**Configuration:**

* **Quadcopter UAV**

**Flight Controller:**

* **ArduPilot**-based system

**Navigation:**

* **GPS** waypoint mission control

**Control Mode:**

* **Autonomous** mission with manual override capability

**Component Selection**

**Motors:**

* **Selected** in 2206-2212 class
* **KV** rating matched for battery voltage for thrust and efficiency balance
* **Selected** for thrust-to-weight ratio for payload operations

**Propellers:**

* **7-9** inch props for improved static thrust at low forward speeds
* **Efficiency** rather than high-speed performance

**ESC:**

* **4-in-1** ESC (30-45A)
* **Compact** and current headroom

**Battery:**

* **4S/6S** LiPo (1500-2200 mAh)
* **Estimated** power consumption and mission duration

**Banner Design & Tow System**

* Made of lightweight ripstop nylon/polyester banner material
* Maximum banner area ≤ 0.25 m² to prevent excessive drag
* Location of spreader rod at top edge of banner to prevent excessive banner flutter
* Dual bridle tow system
* Tow attachment located ahead of the CG for maximum stability
* Weak link and swivel assembly
* A banner will be trailing, and as it trails, it will cause aerodynamic drag.

**Performance Analysis**


**Endurance vs Battery Capacity**

An endurance sensitivity analysis has been performed to determine the effect of battery capacity on mission duration during banner towing.

**Assumptions:**

* Average propulsion power: 160 W

* Battery fraction: 80% (safety reserve)

* Flight condition: low-speed banner towing

**4S LiPo Analysis**

(insert 4S graph image here)

**6S LiPo Analysis**

(insert 6S graph image here)

**Observations:**
4S 1500–2200 mAh packs are sufficient for the 5-minute mission requirement with reserve.

**Theoretical Calculations**

Estimation calculations were carried out as per the following steps to ensure the feasibility of the project:

* **Drag Estimation**

  Estimated Drag:
  D = 0.5 * ρ * Cd * A * V^2

  Values:
  ρ ≈ 1.2 kg/m³
  Cd ≈ 1.4 (for flat banner)
  A ≤ 0.25 m^2
  V ≈ 1 m/s

* **Result:**

  Estimated Drag ≈ 0.21 N

  Considering the oscillatory effect:

  ~60-90 gf effective load.


* **Power Budget**

  Estimated Power Required for Hover:
  ~140-220 W for 1 kg AUW

  Estimated Power Required for Banner Drag:
  ~15-30 W

  **These calculations were used for the selection of the motor and the batteries.**


**Safety and Compliance**

* Weak Link Tow Connection

* Visual Line of Sight Operation

* Defined Flight Corridor

* Battery Failsafe Logic

* Manual Override

* Wind Limit < 3 m/s

**Testing Methodology**

* Bench Testing and Electrical Validation
* Hover Testing without Banner
* Ballast Testing
* Tethered Banner Testing
* Autonomous Mission Testing

**Team & My Role**

My contributions to the project:

* Component Selection and System Configuration

* Avionics Setup and ArduPilot Tuning

* Theoretical Performance Calculations

* Tow System Integration


**Tow attachment location significantly influences stability.**

Low-speed flight requires different tuning compared to standard quadcopters.
