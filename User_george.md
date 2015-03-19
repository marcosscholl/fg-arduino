# Introduction #

I am a long time FlightGear user since the 0.9.7 days.


# Details #

I became interested in this project when I grew dissatisfied with having to reach for the keyboard and mouse for various functions.

I am primarily interested in
  * creating a throttle quadrant (in pipeline)
  * some switches for landing gear, avionics and the like.

Later I'd like to emulate
  * engine rpm and fuel usage
  * While the design is very sketchy, I would like to build a Radio stack (partial to begin with)


# My Sandbox #

## Overview ##

The Arduino uses a virtual serial port to connect over the USB port.
<img src='http://cloud.github.com/downloads/georgepatterson/Flightgear-Console/host_computer.jpeg' align='left' border='1' alt='host computer diagram' />While the serial port appears to be slow, by carefully determining something which has changed and updatding the value.

We could also cache the responses for queried respones which does not change often. An easy example is the property /sim/aero which is the value of the aircraft in use by the FlightGear player. The parameter can only change when the FlightGear is restarted. There fore we can probably cache it for 30 seconds at a time, to allow for fairly prompt changes when FlightGear is reloaded.

The other extreme is a throttle or rudder pedals need to be more real time. It is of little benefit to cache those values as they may change frequently and needs to be current.

## System Components ##

The simpit script is having to talk to three devices:-
  * Arduino via serial port
  * FlightGear via the generic protocol
  * Telnet interface for debugging and expansion to other programs.<br>
We might need a glue script to allow the simpit script to connect to another server. This should be fairly straight forward but considered out of scope for the time being.</li></ul>


<h3>Serial port access to the Arduino ###
The Arduino will be programmed with the assistance of [AikoLibrary](http://groups.google.com/group/connected-community-hackerspace/web/project-aiko---arduino-modular-software-framework). Aiko has two very handy features, one being an event handler, the other being [S-Expressions](SymbolicExpressions.md) also known as S-Expressions (the hyphen is required to avoid human parse errors).



Using S-Expressions makes parsing of the serial stream easier.

Information sent from the serial port is parsed and acted on.

The gist of it is that there are two format

To Set Pin1 to 1, Pin2 to 2, Pin3 to 3 you'd use the following<br>
<pre><code>((pin1 1)(pin2 2)(pin3 3))<br>
</code></pre>
or<br>
<pre><code>(deviceName (a 1) (b 2) (c 3))<br>
</code></pre>
to send the request to the Arduino deviceName. While we may not use the second example, it does provide flexibility as needed.<br>
<br>
The S-Expression is currently not documented, something I intend to remedy later.<br>
<br>
We may use S-Expression through out the system.<br>
<br>
<h2>Data Flow Scenarios</h2>

This is a high level but should explain what is suggested.<br>
<br>
<h4>User flips switch to raise landing gear</h4>
Requirements:<br>
<ol><li>landing gear is connected to Pin3.<br>
</li><li>Landing gear light is connectted to pin4.</li></ol>

Data flow as follows:-<br>
<ol><li>Arduino has noted that the state of Pin3 has changed and sends an update to the Host PC as follows:<br><i>(pin3=1);</i>
</li><li>The computer waits for the semicolon and then parses the string to obtain the substrings pin3 and 1.<br>
</li><li>The computer then processes that pair to assemble a string to be sent to the FlightGear instance. <br> <i>1:400:0</i><br> Where the first column is the part of the string which we have altered.<br>
</li><li>In the third column, is the value of landing gear locked property, we will split a similar string to obtain the value. <br> If the value is a one, we pull Pin4 high. <i>(Pin4 1);</i></li></ol>



