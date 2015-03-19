# Introduction #
The general concept is to create a simple, generic set of buttons, knobs and displays that physically emulate the real thing, this is then fed into the the flight dynamics model of flight gear via arduino, and vice versa.

Background:
Autopilot as within physically commanding and aircraft is the norm,

hence those capabilities would be within FG. However autopilot within FG is the PID process, and does not embrace FMS (Flight Magament Systems) fuels flow cos to airline, et all..

This page is work in progress and being developed with thanks to lzd772 and the youtube channel http://www.youtube.com/user/lzd772. So below are the edited feedback of the discussion.

## Questions with Answers from lzd772 ##

### Can you confirm that there are three areas of autopilot. ie speed, height (vnav), direction (lnav) ?? ###

Yes, there are 3 areas - think of it as trajectory -
  * forward (speed),
  * lateral (HDG/LNAV)
  * and vertical (VNAV/FLCH/VS/FPA).

There are basically 2 modes - basic modes in which you, the pilot, inputs simple straightforward commands to the autopilot (i.e. SPEED, HEIGHT, HEADING) via the FCU/MCP/glareshield. The long term managed modes are more complicated as the autopilot is managed by the FMC and pilot's inputs are done through the CDU.

more questions what are FCU/MCP ? and CDU ?

### Does the A/P button arm or disarm the lot?? ###

Yes. It either engages or disengages the whole thing.

more questions, can it reset itself to current state ?

### If the altitude hold button is engaged, I assume the aircraft goes for that target height? ###

If the altitude hold button is pressed, the aircraft will go for the altitude which was captured at the moment the button was pressed. For example, if the plane was descending and while passing FL250, the altitude hold button is pressed, the plane will continue to descend through FL250 for a little while due to momentum but it will then start to climb back up to FL250. It will disregard what is set in the target altitude window.

### If I want to change altitude, I'm not sure how the button works. Do i just turn it and it goes for it, or does it have to be pushed to "execute" the height? ###

Ah....this is tricky. It depends when you change the altitude. If the plane is already in ALT HOLD mode, then you need to turn it and push/execute it. However, if the plane was climbing/descending (in FLCH mode), then you only need to turn it.

More questions, what is FLCH mode ?

### Can i cancel the above "switch" and make the height indication reset itself to current height.?? ###

No. You have to dial it back to the original value. Best to keep it simple....

### Can I command throttle and vnav at the same time? ###

Erm..I'm not sure what you mean....VNAV is a vertical trajectory mode but it has a SPD/THRUST component. The throttles managed the SPD/THRUST part only. So I guess the answer is yes.
