=====================
Quadcopter
=====================


APM
==========

Configuration
---------------

RTL
^^^^^^^^^^^^^^
RTL mode (Return To Launch mode) navigates Copter from its current position to hover above the home position. 
When RTL mode is selected, the copter will return to the home location. The copter will first rise to RTL_ALT 
before returning home or maintain the current altitude if the current altitude is higher than RTL_ALT. The 
default value for RTL_ALT is 15m.

RTL is a GPS-dependent move, so it is essential that GPS lock is acquired before attempting to use this mode. 
Before arming, ensure that the APM’s blue LED is solid and not blinking. For a GPS without compass, the LED 
will be solid blue when GPS lock is acquired. For the GPS+Compass module, the LED will be blinking blue when 
GPS is locked.

The home position is always supposed to be your copter’s actual GPS takeoff location. For Copter if you get 
GPS lock and then ARM your copter, the home position is the location the copter was in when it was armed. 

In RTL mode the flight controller uses a barometer as the primary means for determining altitude (“Pressure 
Altitude”) and if the air pressure is changing in your flight area, the copter will follow the air pressure 
change rather than actual altitude (unless you are within 20 feet of the ground and have SONAR installed and 
enabled).

Options (User Adjustable Parameters)
"""""""""""""""""""""""""""""""""""""""
RTL_ALT: The minimum altitude the copter will move to before returning to launch.

* Set to zero to return at the current altitude.

* The return altitude can be set from 1 to 8000 centimeters.

* The default return altitude Default is 15 meters (1500)

RTL_ALT_FINAL: The altitude the copter will move to at the final stage of “Returning to Launch” or after 
completing a Mission.

* Set to zero to automatically land the copter.

* The final return altitude may be adjusted from 0 to 1000 centimeters.

RTL_LOIT_TIME: Time in milliseconds to hover/pause above the “Home” position before beginning final descent.

* The “Loiter” time may be adjusted from 0 to 60,000 milliseconds.

WP_YAW_BEHAVIOR: Sets how the autopilot controls the “Yaw” during Missions and RTL.

* 0 = Never change Yaw.

* 1 = Face Next Waypoint including facing home during RTL.

* 2 = Face Next Waypoint except for RTL (i.e. during RTL vehicle will remain pointed at it’s last heading)

LAND_SPEED: The descent speed for the final stage of landing in centimeters per second.

* The landing speed is adjustable from 20 to 200 centimeters per second.

RTL_CLIMB_MIN: The vehicle will climb at least this many meters at the first stage of the RTL. By default 
this value is zero. (only Copter-3.3 and above)
