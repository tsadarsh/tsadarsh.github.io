# Project: Pressure Injury Prevention System

## Outline of Project Page Implementation
Write all the page contents in first-person voice. It should feel natural and written in simple words. Usage of technical words are allowed but avoid using too many filler words.

Project page sections:
1. Project Title
2. Brief description of the project
3. Clickable tabs with short text of my contibution/work in the research project.
4. Blueprint of entire system

## Details of Project Page Implementation
### Project Title
Use a bold font that looks modern and tech oriented. TechCrunch website fonts is a good inspiration. The title should be big and centered.

### Brief description of the project
Summraize the following formal text describing the project:
Originally prototyped as the Pressure Ulcer Prevention System (PUPS), the technology has subsequently
evolved into PIPS 2.0, representing a monumental paradigm shift toward continuous, unobtrusive, and
data-driven patient monitoring.The PIPS 2.0 architecture integrates a highly advanced "smart fabric"
sensor network directly into a fitted mattress sheet, rendering it capable of mapping localized pressure
magnitudes and microclimate moisture variations in real-time. The data acquired from this physical
piezoresistive sensor matrix is processed through a robust, multi-layered Internet of Things (IoT)
architecture, translating raw, fluctuating analog signals into actionable clinical interventions. This
technical report provides an exhaustive, component-level deconstruction of the PIPS 2.0 architecture,
analyzing its foundational hardware engineering, mathematical compensation models, algorithmic
backend processing, and frontend visualization frameworks to satisfy the rigorous analytical requirements
of advanced materials science and engineering systems.

### Clickable tabs with short text of my contibution/work in the research project.
Use HTML style tabs that a user can choose to select the specific sub-part of the project that I have worked on. 

My Contribution in the Research Project:
1. Designed PCBs:
	1. Flexible PCB that is sewn on the textile material that has the pressure and moisture sensors
	2. Four layer PCB with ESP32 microcontroller that gathers data from a section of sensor mat through flexible PCBs, filters and sends it the Raspberry Pi through I2C
2. Firmware for the ESP32 microcontroller with both BLE and I2C transmission modes to send data to the Raspberry Pi
3. Python server for aggregating the data from multiple ESP32s, running compensation algorithms, logging data and pushing it to Firebase

When the specific sub part is clicked, the brief description of the project text is replaced with the brief summary of the work done by me in the specific sub part of thr project. Clicking on the project title text should reset the view by unselecting the tabs and bringing back the project summary.