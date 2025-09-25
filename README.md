# Shockflo40A EVSE Project
Re-imagining the firmware for a 40A Shockflo CG04 EV charger, as found for roughly $55 on eBay in September of 2025.

My specific goal with this, is to use this on an off-grid solar system where the charger dynamically throttles/switches to only gate extra power into a plug-in hybrid electric vehicle.  Basically plug the car in, and forget about it--if there's any extra power, it will be gated into the PHEV.  And if it's cloudy, you drive the PHEV on gas.

A lot of programming will be required to completely rewrite new firmware for the GD32 processor.  PlatformIO will be leveraged here, which easily supports programming GD32 MCUs with a cheap DAPLink / CMSIS-DAP programmer.  Note that due to the relatively small FLASH size in the GD32 (64KB), efficient programming techniques will be required.  We will not be able to casually "pull in" huge libraries, or this project will simply not be possible.

"Appending" an ESP32 to the little header on the top may not be viable, as both the 5v and 3.3v rails are run by series regulators from the 12v power supply.  The existing power system could handle an ESP32 if it was running off a switching regulator from the +12v rail...but probably not off the LDOs.

NOTE: I will NOT upload the original GD32 firmware binary here.  All firmware work will be done from the ground up.  I do not want to make Shockflo regret making something this easy to modify and repurpose!
