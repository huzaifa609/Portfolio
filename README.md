# Color-Sorting Conveyor System

A mechatronic color-sorting system designed in SOLIDWORKS and built as a working prototype. The system uses a belt conveyor to move colored cubes past a color sensor, which triggers servo-actuated pushers to sort each cube into its matching collection bin (red, blue, or default/green pass-through).

![CAD Overview](images/01-overview-render.png)

## Overview

This project demonstrates an end-to-end mechatronic design workflow: 3D CAD modeling and assembly in SOLIDWORKS, followed by physical prototyping and Arduino-based control.

- **CAD Model:** Full assembly modeled in SOLIDWORKS, including conveyor frame, belt/roller system, sensor mounts, and pusher-actuator stations.
- **Prototype:** A working physical build using wood framing, a belt conveyor, servo-driven pushers, and an Arduino-based control system.
- **Function:** Cubes are placed on the conveyor belt, travel past a TCS3200-type color sensor, and are sorted by color into designated bins via servo/actuator-driven pushers along the belt.

## How It Works

1. A DC motor drives the conveyor belt, moving cubes from the infeed end toward the outfeed end.
2. As each cube passes the color sensor station, the **TCS3200 color sensor** reads the cube's color.
3. Based on the detected color, the Arduino triggers the corresponding **servo/actuator pusher** to sweep the cube off the belt and into its matching bin (e.g., red cubes → red bin, blue cubes → blue bin).
4. Cubes that don't match a sorting station pass through to the end-of-line bin.

## System Components

| Subsystem | Description |
|---|---|
| Conveyor Frame | Structural frame supporting the belt and drive system |
| Belt & Roller Assembly | Conveyor belt with driven/idler rollers |
| Drive Motor | DC motor at the outfeed end, drives the belt |
| Color Sensor | TCS3200-type sensor for detecting cube color |
| Sorting Actuators | Servo-driven pushers at each sorting station |
| Collection Bins | Color-coded bins (red, blue, yellow/green) positioned below sorting stations |
| Controller | Arduino Uno/Nano running the sorting logic |

## Electronics

- Arduino Uno/Nano (main controller)
- TCS3200 color sensor module
- Servo motors (sorting pushers)
- DC motor (belt drive)
- Supporting wiring/breadboard for prototype build

See [`firmware/`](firmware/) for the control code.

## Gallery

| CAD Render | Schematic Views |
|---|---|
| ![Overview](images/01-overview-render.png) | ![Schematic](images/02-schematic-views.png) |

| CAD vs. Prototype | Orthographic Views |
|---|---|
| ![CAD vs Prototype](images/03-cad-vs-prototype.png) | ![Orthographic](images/04-orthographic-views.png) |

## Repository Structure

```
color-sorting-conveyor/
├── images/          # Renders, schematics, and prototype photos
├── cad/             # SOLIDWORKS files / STEP exports
├── firmware/         # Arduino sorting logic code
├── docs/            # Design notes, BOM, reports
└── README.md
```

## Status

- [x] CAD assembly design (SOLIDWORKS)
- [x] Physical prototype built
- [x] Basic color-sorting logic
- [ ] Full documentation / BOM
- [ ] Final firmware cleanup

## Author

Muhammad Huzaifa Aftab — Mechanical Engineering, UET Taxila
