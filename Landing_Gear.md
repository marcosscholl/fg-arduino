# Landing Gear #

The landing gear has the following general indication scenario
  * when their down their green - if there are 6 "wells" then six lights
  * when their being lifted or lowered their RED
  * when their up there's no lights

check this Vid at 1:40

<a href='http://www.youtube.com/watch?feature=player_embedded&v=klZPGhxTk-s' target='_blank'><img src='http://img.youtube.com/vi/klZPGhxTk-s/0.jpg' width='425' height=344 /></a>

Arduino ports ?
Landing gear is controlled from the cockpit with a lever.

A move of the lever would
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

?? is there a set of colours ??
Glass cockpits just show a prompt on the screen.

![http://www.b737.org.uk/images/main_gear_ng_labelled.jpg](http://www.b737.org.uk/images/main_gear_ng_labelled.jpg)

![http://www.atsb.gov.au/publications/investigation_reports/2005/AAIR/images/aair200500167_001.jpg](http://www.atsb.gov.au/publications/investigation_reports/2005/AAIR/images/aair200500167_001.jpg)

![http://www.viperpanels.com/wp-content/uploads/2009/08/111111111.jpg](http://www.viperpanels.com/wp-content/uploads/2009/08/111111111.jpg)

> Actually I was a little bit overboard. The Seneca II has thre indepentent landing indicators (green or off), however there's a light on the left hand side at the top of the dash. It will be red when the gear is neither up or down and locked.

Just found an example where you can have three reds as well as three greens.

Taken from http://www.b737.org.uk/landinggear.htm:-
<blockquote>
<img src='http://www.b737.org.uk/images/gearleverthumb.jpg' /> The landing gear panel is located between  the engine instruments and F/O's instrument panel.<br>
<br>
The Green lights tell you that the gear is down and locked and the red lights warn you if the landing gear is in disagreement with the gear lever position.<br>
<br>
With the gear UP and locked and the lever UP or OFF, all lights should be extinguished.<br>
<br>
On a couple of occasions I have seen 3 reds and 3 greens after the gear has been selected down. This was because the telescopic gear handle had not fully compressed back toward the panel. If this happens to you, give it a tap back in and the red lights will extinguish.<br>
</blockquote>