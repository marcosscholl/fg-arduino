Flaps are extensions of the wing surface required to fly at low speed. [(wikipedia)](http://en.wikipedia.org/wiki/Flap_%28aircraft%29)

![http://quest.arc.nasa.gov/aero/virtual/demo/aeronautics/tutorial/images/FlapsAilerons.gif](http://quest.arc.nasa.gov/aero/virtual/demo/aeronautics/tutorial/images/FlapsAilerons.gif)

The flaps are normally controlled from the cockpit by a lever next to the throttles, although they can appear elsewhere.

![http://i.ehow.com/images/GlobalPhoto/Articles/2000153/flap_Full.jpg](http://i.ehow.com/images/GlobalPhoto/Articles/2000153/flap_Full.jpg)

Flaps are down for take off, after take off and as the aircraft attains speed in a climb, they are stepped back. for example at 220 knots its efficient to flay at flap 3, then at 250 knots flap 2 , etc etc.

Landing is the sequence the opposite way around.

Flaps normally have a value such as flaps 0 - 5 or 0 degrees to 35 degrees.

With input from Arduino this could be achieved by a few techiques, ad it depends on the number fo flap position required. (TODO)

Lets take for example flaps 0-5 = six positions

the Lever could be
  * analog -  could be a "stepped" pot with positions, of resistance which creates a value range
  * a 6 position switch - digital
  * a multiplex switch - digital

Outputs from flight gear would be the flap position as it takes a few moments for the flaps to mode to the new position (as we all know that sound).

This output could be int eh form of a dial, an led bar, or its on the glass cockpit display.

![http://farm4.static.flickr.com/3111/2636267807_544617ee8d_o.jpg](http://farm4.static.flickr.com/3111/2636267807_544617ee8d_o.jpg)
