---
title: "PCB design workflow example"
author: "Davide Scalcon"
theme: "Luebeck"
colortheme: "whale"
date:
- January 30, 2026
aspectratio: 169
toc: false
# titlegraphic: img/logo.png   # Title slide graphic
# logo: img/logo.png     # Corner logo
---

# Mount PCB for Somerville box
![3D rendering of the designed PCB using kicad 9.0](img/20260129_08h53m42s_grim.png){width=75%}



# Steps in PCB design and manufacture
  1. Collect requirements and specs
  1. Circuit design
  1. Components selection
  1. Creation of custom symbols/footprint
  1. Schematic
  1. PCB layout
  1. Submission to manufacturer
  1. Firmware development and testing
  1. Go back to the step where you made some stupid mistake and reiterate the process



# Tool: Kicad
![](img/kicad_logo_small.png){.center width=20%}

- Open source electronic CAD (ECAD, aka EDA)
- Targets only PCB design \footnote{I'm sure it is potentially possible to extend its capabilities to chip design}
- Can be used as graphic frontend for ngspice (or other spice-like network simulators)
- Provides graphic and a python (socket-based) interface, especially useful to automate PCB layout
- Can generate 3D models of the final product



# Collect requirements and specs
- Ask for the most detailed description, fill the gaps and feed back
- Once fixed do not change, if needed start over
- Make fewer assumptions as possible



# Circuit design and components selection
* Divide the circuits into functional blocks and find a topology that implement the target functionality.
* Select components depending on requirements and availability.
* Run simulations if possible/required.

In this presentation example:

- Somerville DC pad analog frontend (next slide)
- AD/DA conversion
- TEC control
- Controller

# Example: Analog frontend for Somerville DC pin

::: columns

:::: column
Each pin can be configured as:

- Voltage source, capable of driving 200mA, $\pm$ 10V
- Ground reference
- Ground reference with current sensing
- Transimpedance amplifier

---

Configuration is done during assembly.

::::

:::: column
![Schematic](img/sch.jpg)
::::

:::


# Creation of custom symbols/footprint

* The workflow of in PCB design is: schematic -> DRC -> layout -> DRC

* In the schematic you place and connect symbols, documenting the functionalities.

* In the layout phase, footprints associated with the symbols are placed on the PCB, electrical connections are made using traces.

* Symbols and footprints for lot of components can be found online, it is sometimes needed to make custom ones (e.g. somerville box)


:::: column
![Custom footprint of the Somerville box](img/sch.jpg)
::::

:::



# Schematic
- Think about testing



# PCB layout
- Think about testing



# Submission to manufacturer



# Firmware development and testing

