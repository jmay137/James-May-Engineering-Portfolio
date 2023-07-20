# [Projects](http://vlarko.com/Projects)
# Modular Light Cell

<img src="/Photos/mlc altium 3d.png" height="400" style="border:7px solid black">

# Overview
The goal of this project is to create a system for generating large & scalable LED displays, using cheap and commonly available 3mm LEDs. The makerspace I currently work at gets thousands of these LEDs donated & desperately needs projects to do with them. This was the inspiration for this board. By using a BJT transistor as a current-controlled switch to toggle the 16 LEDs at will, you can string together many of these boards and create complex, large scale light displays out of the most readily available LED out there. The design also includes a jumper, if the end user would simply like the LEDs on 24/7.

<img src="/Photos/mlc altium route design.png" height="400" style="border:7px solid black">

# Specifications
Component list:

- 16x 3mm LEDs
- 17x 200ohm 1/4W chip resistors
- 1x 2N2222 BJT transistor  
  
Board size: 4200 mil by 900 mil (4.2" by 0.9")  
  
4x 3mm holes included for mounting with M3 bolts.

<img src="/Photos/mlc ltspice sim.png" height="400" style="border:7px solid black">

# Design Process
The circuit was designed in Altium using a hierarchal schematic design, simulated in LTspice, and then the physical layout and routing was done in Altium.  
  
Some quick napkin hand calculations told me that to drive 16 3mm LEDs at around 10mA, I would need a ~200 ohm current limiting resistor on the input to the 2N2222 BJT. An LTspice simulation was run to verify this & get more accurate data. The simulation gave me a current of 10.3mA through each LED, which is in agreement with my hand calculations.  
  
Based off the LTspice simulation, a 200ohm resistor would be sufficient for both the current limiting for the BJT, as well as the current limiting for the LEDs, which simplified the design by only requiring one resistor.  
  
After this, the component layout & routing was done. Fortunately, since the traces would only be DC (barring any potential low-speed PWM signals from the CTRL input), not many considerations had to be made for RF. The design only required 2 vias to make all necessary connections.

<img src="/Photos/mlc schematic led array.png" height="400" style="border:7px solid black">

# Manufacturing and Final Results
After the design was completed, the board was exported as Gerber files and sent to JLCPCB for manufacture, as well as SMT assembly of the surface mount resistors. 5 prototypes were received, soldered, and work beautifully! 
  
Future goals of this project are as follows:

- Fix any PCB issues that may come up once physical boards arrive
- Create a 3d-printable jig that holds the LEDs and BJT in place for easy soldering
    - This will allow many of these boards to be produced in a relatively short period of time
- Run a mass order of these boards
- Begin experimenting with scaling up & making large displays
