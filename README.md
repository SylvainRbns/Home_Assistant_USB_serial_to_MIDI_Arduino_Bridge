# Home_Assistant_USB_serial_to_MIDI_Arduino_Bridge
Home Assistant USB Serial to MIDI Arduino Bridge 

This solution allows to make a bridge from USB serial to MIDI communication.

The aim of this project was to be able to send MIDI notes from Home Assistant (running as OS on a Raspberry Pi4) to a Behringer X32 digital Audio Mixing Desk.

This command has to be launched in the Home assistant terminal in order to work:
cat -v /dev/ttyUSB0 

I currently need to re-launch this command in the terminal after each reboot.

"MEGA2560 CODE" is the code for the MEGA2560 Board. 
At first, I tried with an arduino UNO but this board have only 1 serial port, so I moved to a MEGA2560 in order to have multiple serial ports.

MEGA2560 is connected directly via USB to the Raspberry pi4 running Home Assistant.

Communication between Raspberry Pi4 and MEGA2560 is done on default serial port.

Serial Port 3 is used to send the MIDI informations.

"Home Assistant Code" is the part to add to the configuration.yaml of Home Assistant.

"Serial_To_MIDI.PNG" => Schematics 

"Home_Assistant_Final_view.PNG" => An exemple of the controls programmed in Home Assistant via a Picture Elements Card.

Commands are sent from Home Assistant using "Call a service" => example:   shell.command.x32_input5_mute

This can be used with scripts or automations. I did use some Boolean Inputs in order to set the MUTE/UNMUTE states.

Enjoy and please feel free to contact me if you have ideas to improve this project !
