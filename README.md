#PARTICLE CLOUD FUNCTION TRAFFIC LIGHT CONTROL - README

This project utilises the Particle.function() call to remotely control LED's from a webpage. It will mimick the scenario that you are required to create a program that allows you to manually control a set of traffic lights in a remote area. To complete this, you will need a Particle Argon device, knowledge of how to use Particle.function() (you can learn about this here: https://docs.particle.io/reference/device-os/firmware/photon/ ), you will need to download and read about the Particle CLI (https://docs.particle.io/reference/developer-tools/cli/) and have knowledge of how to create a basic HTML webpage. There is documentation on how to build a basic version of this project on the Particle website that you can find by searching for Particle Argon Hardware Examples, or via https://docs.particle.io/tutorials/hardware-projects/hardware-examples/argon/

###HARDWARE SETUP:

The breadboard will be almost identical to the blink program on the Particle Hardware Examples webpage, except also contain a yellow and green LED, each paired with their own 220 ohm resistor. They should be set up in the same way as the original red, but the data wires need to be connected like this:

Red to pin D2
Yellow to pin D4
Green to pin D6

You can test each of these by creating a small blink program that sets each LED pin to output, turns the LED's on for a second and then turns them off for a second. Once this is complete, you can use the .cpp file in your IDE and flash it to your Argon device.

###GENERATING AN ACCESS TOKEN

There are two edits you will need to make in order to utilise this code for your own Particle Argon. Under the action call inside each "form" tag, you will first need to replace the alphanumeric device id after /devices/ in the url. This will be the same across all form tags. The next step will be unique for each form tag. In the same URL, after it says access_token= you will need to replace the current alphanumeric access token with a newly generated one. To do this, you need to access the Particle CLI via your command prompt. Once in, run the command "particle setup" to initialise the Particle CLI. You won't need to make this call again, you will only need to type "particle" to enter. To create an access token, type the command "particle token create". Type in your Particle account password and you will be given an access token to use. This access token will be unique to each particle function. The basic form of the form tag line will look like this:

	<form target="hiddenFrame" action="https://api.particle.io/v1/devices/Your_Device_ID_Goes_Here/Name_Of_Particle_Function_Goes_Here?access_token=Access_Token_Goes_Here" method="POST">
		Heading for action goes here!<br>
		
Now all you need to do is open the .html page and you can toggle each of your lights.
