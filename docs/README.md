# PedalPi
Pedal Pi Thawney is based off of Pedal-Pi by electrosmash; a lo-fi programmable guitar pedal that works with the Raspberry Pi ZERO Board. My repository contains all of the information needed to create your own board from scratch unlike Pedal Pi who only share effect code.

[_There is a video demo here_](https://www.youtube.com/watch?v=90KZU-akCmM&ab_channel=Thawney)

![Picture of the Pedal Pi PCB Design](https://github.com/thawney/PedalPi/blob/main/PCB_Files/PCB_Images/PedalPiThawney_PCB_Wip.jpg?raw=true)

## How Is this Repository different to the original Pedal Pi?

The difference is that my version also has open source PCB files, Protective Case Design files, and anything else needed to make the project yourself (as well as example code of various pugins), unlike electrosmash who claims to be open source but will not share or does not produce certain files (such as PCB files and Protective case designs).

# How Does the Circuit Work?

This  [_hat_](https://www.hifiberry.com/blog/what-is-a-raspberry-pi-hat/) has three parts:

-   The Input Stage:  Amplifies and filters the guitar signal making it ready for the ADC (Analog to Digital Converter). The ADC sends the signal to the PI ZERO using  [SPI communication](https://en.wikipedia.org/wiki/Serial_Peripheral_Interface_Bus). In the forum, the topic "[Using MCP3202 ADC with Raspberry Pi Zero](https://www.electrosmash.com/forum/pedal-pi/212-using-mcp3202-adc-with-raspberry-pi-zero)" gives more details about the ADC-Pi ZERO connection.  
    
-   Pi ZERO:  It takes the digitalized audio waveform from the ADC and does all the Digital Signal Processing (DSP) creating effects (distortion, fuzz, delay, echo, tremolo...). In the forum, the topic "[Basics of Audio DSP in C for Raspberry Pi Zero](https://www.electrosmash.com/forum/pedal-pi/207-basics-of-audio-dsp-in-c-for-rapsberry-pi-zero)" can assist you to learn the basics.
-   The Output Stage:  Once the new digital waveform is created, the Pi Zero creates an analog signal with two PWMs combined, the signal is filtered and prepared to be sent to the next pedal or the guitar amp.  For more info check the topic "[PWM Audio on Raspberry Pi Zero](https://www.electrosmash.com/forum/pedal-pi/210-pwm-audio-on-raspberry-pi-zero)".

![Pedal Pi Schematic](http://www.electrosmash.com/images/tech/pedal-pi/pedal_pi_block_diagram.jpg)

- Here is a more detailed photo of just the RaspberryPi Stage.

![Raspi explanation schematic](http://www.electrosmash.com/images/tech/pedal-pi/pedal-pi-dsp1.png)
# How to Program it?

The idea is to make it as easy as possible, the examples are programmed in C using the standard  [BCM2835 Libraries](http://www.airspayce.com/mikem/bcm2835/). The Operating System used is  [Raspbian.](https://www.raspberrypi.org/downloads/raspbian/)  All tools and programs are free/open source. In the OFFICIAL forum, there is a topic called  ["How to Start Programming Pedal-Pi"](https://www.electrosmash.com/forum/pedal-pi/202-how-to-start-programming-pedal-pi) with more details (note: this forum is not run or maintained by thawney and is for the original design, all code should still work).

Basic knowledge of Arduino, Linux and C are needed. You can find many Example effects in this repository's Effects folder, the PedalPi legacy effect are the most basic ones currently.

## Need More Support?

Contact Thawney:

- Find all of their social media and othe contact info [here](https://www.thawney.com) or join their [discord](https://discord.com/invite/Eh7VRgu).

ElectroSmash PedalPi Website:

- Whilst some may be very outdated, information on how the project works, old schematics and Learning materials can be found [here](https://www.electrosmash.com/pedal-pi).
