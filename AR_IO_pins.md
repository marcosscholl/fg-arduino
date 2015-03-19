# Introduction #
This page is ideas for pin usage, and the possible input output combinations

Arduino has
  * 6 analog inputs
  * 14 digital as either IN or OUT

The issue is really about state and the number of ports to utilize/sacrifice.

  * **[Parking\_Brake](Parking_Brake.md)**
  * **[Throttle](Throttle.md)**
  * **[Flaps](Flaps.md)**
  * **[Landing\_Gear](Landing_Gear.md)**

For example, the landing gear switch. A flick of this switch would
  * send a state event  from arduino to FG ie up or down
  * FG recieves the signal and changes landing gear state.
  * and an indicator light on the "plane" cockpit in the SIM will change
  * A real local led indicator light could be switched on/off Local to switch with no logic to indicate state, just followinfg the siwtch.

The addition to the above would be to aqquire the real local indicator light from FG and that would in probability be a tristate ie
  * gear up
  * gear intermediate
  * gear down

So
  1. one digital switch IN  to arduino sent to FG - landing gear state
  1. A state out from FG. sent to arduino and a pair of digital OUT to make tristate
  1. 3 digital pins in total

## Alternate Landing Gear Solution ##
At least one plane in FlightGear is able to fail the landing gear independently for Left, Right and Nose gear.

While introduces more complexity but for a more enjoyable environment.

The indicator states are
  * Gear up
  * Gear Down
  * Gear indicator bulb failed.

This will require six digital output pins for the lights and one input for the switch.

It is possible to multiplex the pins for illuminating the six pins. This will save I/O pins for other task.


## 6 Analog Ports ##
  1. - Throttle
  1. - pitch
  1. - brakes
  1. - mixture
  1. - rudder pedals
  1. - ?


## Digital Ports ##
  1. Autopilot on
  1. altitude hold
  1. speed hold
  1. speed ?



# Parking Brakes #
Either ON or off
  * single digital input > FG
  * single digital output <  to big red bulb from FG

# Landing gear #
  * Gear Up/Down switch > digital in to FG
  * Landing gear lights < from FG < tri state with down/intermideatte/up ie 2 pins

# Brakes #


# Flaps #
An analog Switch input that can step maybe 5 or 6 > Fg input as -1.0 thru -0.5 to 0.0