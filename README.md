# OctoPrint-Hardwarepwm

Uses PiGPIO to drive a hardware PWM pin. Super early stages!

## Setup

Install via the bundled [Plugin Manager](https://github.com/foosel/OctoPrint/wiki/Plugin:-Plugin-Manager)
or manually using this URL:

    https://github.com/pastapojken/OctoPrint-Hardwarepwm/archive/master.zip


## Configuration

Requires the pigpio deamon to be running (I recommend to install "pigpio" via apt-get and enable it with "sudo systemctl enable pigpiod" and then reboot your Raspberry Pi. 
Defaults to pin 19 (BCM pin naming). To change the pin, frequency or the dutycycle, simply edit the corresponding fields in the settings page.

## API sample

	curl -H "X-Api-Key:xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx" -X GET http://localhost:5000/api/plugin/hardwarepwm
	curl -H "Content-Type: application/json" -H "X-Api-Key:xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx" -X POST -d "{ \"command\" : \"setdutycycle\" , \"dutycycle\" : \"10\" }" http://localhost:5000/api/plugin/hardwarepwm
	curl -H "X-Api-Key:xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx" -X GET 'http://localhost:5000/api/plugin/hardwarepwm' 2> /dev/null | jq -r '.dutycycle'
	