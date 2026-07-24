# SOPHON
SOPHON: **S**calable, **O**pen, **PH**otobioreactor: **O**xygenation **N**ode.
(also a Remembrance of Earth's Past reference)

SOPHON is a semi-closed carbon-negative photobioreactor that costs **less than $500** in components. It uses the algae _Arthrospira platensis_. It converts atmospheric carbon into biomass while serving as a classroom STEM teaching tool. The 2 liter cylindrical acrylic tube measures ~3.5” ID x 16” height. It uses ambient air and modified Zarrouk media nutrient source.
SOPHON takes in nutrients, carbon dioxide, and light. It produces biomass and oxygen in return.

Main Components:
+ Air Pump (around 5L/min)
+ Peristaltic Pumps (1 high-flow foralgae harvest; 3 low-flow for inputs like nutrients)
+ Acrylic Vessel
+ Arduino UNO R4 for data collection and control
+ Reused Car COB light (halo/angel eye) for artificial light growth

Future Additions:
+ pH Sensor for autonomous data collection and regulation of pH
+ Custom zero-carbon media
+ Automatic Harvesting via solenoid valves
+ Custom PCB
## Status
Rev 1 is assembled and has **never been** inoculated. All testing to date has used water and food coloring; **no culture** has been grown in this device. Here be dragons, EMI, and faulty wiring. 
What works: full-system power, dosing state machine, colored-water transfer through all four lines, pump calibration.
Known-bad: pump calibration drifts, intermittent bubbles in the multiplexed path, EMI on sensor lines, counterfeit DS3231 modules (using NTP instead).
Cut on 2026-06-02 (scope freeze): LCD, joystick, turbidity sensor.
Under revision: fluid handling is being redesigned from one-motor multiplexing to independent pumps — the shared wetted path risks harvest contaminating the input lines, and concentrated nutrients precipitate on contact with the salt feed.
Carbon accounting: SOPHON is not currently carbon-negative. It runs on grid power and uses dissolved inorganic carbon. See the notebook entry of 2026-03-22 for the reasoning.
Active development is paused. No timeline. The repo stays up and the license stands; fork it if you want to build one. You can create issues if you have any questions; I check this repo often.
## Team
Rakin Molla<sup>1</sup>, Arjun Lakshmanan<sup>1</sup>, Jason Zhang<sup>2</sup>

<sup>1</sup>Hallie Wells Middle School 

<sup>2</sup>Roberto Clemente Middle School

## License

**ALL** of SOPHON's hardware is licensed under the [CERN OHL-S v2](LICENSE-HARDWARE), while software/firmware is licensed under the [GPL v3](LICENSE-SOFTWARE).

Thank you to Montgomery County RecXtra's Youth Development Program and the Hallie Wells Green Team for funding and supporting this project.



