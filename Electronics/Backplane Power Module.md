# [Projects](http://vlarko.com/Projects)
# Backplane Power Module
<img src="/Photos/power mod real2.jpg" height="400" style="border:7px solid black">

# Overview
Networked power module for the RIT Launch Initiative 2022-2023 flight computer, The Backplane. 

The Backplane is a student-built modular flight computer built by the RIT Launch Initiative. It consists of 4 independent and networked modules: Autopilot, Radio, Sensor, and Power, all of which connect through an Ethernet-capable central Backplane board.

Each module was assigned to an avionics hardware engineer on the team, and my module was Power.

<img src="/Photos/power mod altium.png" height="400" style="border:7px solid black">

# Specifications
- 5V & 3V3 power rails, each capable of supplying 3A to The Backplane, via two TPS565208DDCT switchers
- Voltage sense on battery/umbilical input
- Current sense on battery/umbilical input, as well as on both output rails
- Ethernet communication capability via a WIZnet W5500 chip
- Team project documentation page [here](https://wiki.rit.edu/display/ritlaunch/Power+Module+-+Backplane)

<img src="/Photos/power mod backplane.jpg" height="400" style="border:7px solid black">

# Final Results
After a year long development cycle, The Backplane was completed in time for our competition. Each module, including Power, had 5 prototypes ordered. Power Module was designed to have the two power inductors soldered on by hand after the boards had been assembled, since JLCPCB did not stock the power inductors I wanted to us. This presented a problem. The power inductors had significant thermal mass, which meant hand soldering would not work. I attempted holding the iron onto the pads for a significant amount of time, but the board got hot enough to risk damaging the other ICs, so I had to pivot. I ended up borrowing a hot plate and using solder paste to solder the inductors, which worked beautifully. The Power module was tested, and demonstrated that it could successfully power both The Backplane and the other modules, with voltage ranges comparable to the expected ripple.

Moving forward, I plan to develop a version 2 of the Power Module. I primarily want to improve the following:
- Improve routing of switchers
- Switch to a JLCPCB power inductor so it can come pre-soldered
- Look into adding 1.8V rail
