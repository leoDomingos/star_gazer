The goal of this project is to essentially copy one of those apps that lets you point your phone camera at the sky and then renders the stars, planets and constellations that you are seeing.

# Project Goals

The project must then have the following specifications:
1. It needs to let the user point at wherever, and then show the stars in the direction the device is pointing at.
2. Device must work anytime and anywhere, with no internet connection.
	1. This entails some sort of GPS and IMU sensor.
	2. Getting realtime coordinates of the astros will probably require some third party tool. Hope this doesn't require using an API.
		1. My thinking here is that since the bodies follow very predictable Newtonian Laws in the night sky, there might be some online resource or algorithm that lets me calculate where the bodies should be.
			1. Could get real hard real fast.
3. It must use the telemetry from the sensors to show the night sky on a display.
	1. The display needs to be updated real time. Probably only matters for the Sun and the Moon, but I still don't want to have any hardcoded positions here.
	2. Rendered images must be at least somewhat fluid when the user moves the pointing device (I'm thinking at least around 20 fps).
	3. The display itself can't be one of those super small Arduino displays - needs to be sufficiently big to show the objects coming in and out of view in a convincing manner. Being too small would break this illusion (the Moon would just pop in for instance, and it would be very finnicky)
		1. Could "lower the zoom", but can't imagine that looking good - imagine a small circle on an already small 1' display.
		2. This will probably force me to use a monitor, but I don't think STM32 can drive HDMI.
4. Because I'm broke af, all components must be somewhat cheap.
	1. Will probably only really matter for the display.

# Initial Breakdown


![](Excalidraw/Diagram%20V1.svg)