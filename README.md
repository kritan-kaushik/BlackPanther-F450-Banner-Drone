> **Note:** This was a conceptual/on-paper design project and was not physically built or flight-tested.  
> The focus was on feasibility analysis and system-level UAV design.

# BlackPanther F450 Banner Towing UAV

---

## Project Summary

This project presents the conceptual design and feasibility analysis of a quadcopter UAV capable of towing a lightweight advertising banner at very low speeds.

The study focuses on propulsion sizing, drag estimation, endurance analysis, and safe mission planning to determine whether a standard F450-class quadcopter can operate effectively under high-drag payload conditions.

---

# Project Objectives

- Design a UAV capable of towing a banner at very low speeds (≈0.8–1.2 m/s)  
- Maintain flight stability under aerodynamic drag and dynamic payload effects  
- Enable repeat autonomous missions between two waypoints  
- Integrate safety features suitable for demonstration environments  

---

# Key Engineering Learnings

- Banner drag significantly affects endurance even at low speeds  
- Thrust margin is critical for high-drag payload missions  
- Towline damping reduces oscillatory instability  
- Mission planning must include battery reserve margins  
- Low-speed operation reduces drag but requires careful tuning  

---

# System Architecture

## Frame
- BlackPanther F450 (450 × 450 mm)

## Configuration
- Quadcopter UAV

## Flight Controller
- ArduPilot-based system

## Navigation
- GPS waypoint mission control

## Control Mode
- Autonomous mission with manual override capability

---

# Component Selection

## Motors
- 2206–2212 class  
- KV matched to battery voltage  
- Sized for thrust-to-weight margin under payload conditions  

## Propellers
- 7–9 inch props  
- Selected for static thrust and efficiency  

## ESC
- 4-in-1 ESC (30–45A)  
- Compact with current headroom  

## Battery
- 4S/6S LiPo (1500–2200 mAh)  
- Sized using endurance estimates  

---

# Banner Design & Tow System

- Lightweight ripstop nylon/polyester banner  
- Banner area ≤ 0.25 m²  
- Spreader rod at top edge to reduce flutter  
- Dual-bridle tow system  
- Tow point located ahead of CG for stability  
- Weak link and swivel assembly  

The trailing banner introduces additional aerodynamic drag and dynamic oscillatory loads on the UAV.

---

# Performance Analysis

## Endurance vs Battery Capacity

An endurance sensitivity study was conducted for banner towing missions.

### Assumptions
- Average propulsion power: 160 W  
- Usable battery fraction: 80%  
- Low-speed banner towing condition  

---

### 4S LiPo Endurance
![4S Endurance](4s%20Mark%20copter.png)

---

### 6S LiPo Endurance
![6S Endurance](6s%20Mark%20copter.png)

---

### Observation
- 4S 1500–2200 mAh packs meet the 5-minute mission requirement with reserve  
- 6S packs provide higher endurance but increase system weight and cost  

---

# Drag vs Speed Analysis

Drag force was estimated using:

D = 0.5 × ρ × Cd × A × V²

Where:
- ρ = 1.2 kg/m³  
- Cd = 1.4  
- A = 0.25 m²  

| Speed (m/s) | Drag (N) |
|------------|---------|
| 0.5 | 0.05 |
| 1.0 | 0.21 |
| 1.5 | 0.47 |
| 2.0 | 0.84 |
| 2.5 | 1.31 |

### Insight
Drag increases **quadratically** with speed.  
This confirms that very low-speed flight is optimal for banner towing missions.

---

# Theoretical Calculations

## Drag Estimation
Estimated drag at 1 m/s:

≈ 0.21 N  

Accounting for oscillations:

≈ 60–90 gf effective load

---

## Power Budget

Hover power (~1 kg AUW):  
140–220 W  

Additional banner drag power:  
15–30 W  

These estimates guided propulsion sizing.

---

# Safety and Compliance

- Weak-link tow connection  
- Visual Line of Sight (VLOS) operation  
- Defined flight corridor  
- Battery failsafe logic  
- Manual override capability  
- Wind limit < 3 m/s  

---

# Testing Methodology (Conceptual Plan)

- Bench electrical validation  
- Hover testing without banner  
- Ballast testing  
- Tethered banner trials  
- Autonomous mission evaluation  

---

# Team & My Role

My contributions:

- Component selection and system configuration  
- Avionics setup and ArduPilot tuning  
- Theoretical performance calculations  
- Tow system integration  

---

# Limitations

- No physical prototype or flight testing conducted  
- Drag model simplified  
- Banner aeroelastic behavior not modeled  
- Environmental disturbances not simulated  

---

# Conclusion

This conceptual study demonstrates the feasibility of a banner-towing UAV using an F450 platform.

Analysis indicates that low-speed banner towing is viable with proper propulsion sizing, damping strategies, and mission planning.

Future work would include CFD validation and real-world flight testing.
