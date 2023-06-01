# R24MidiSync
**Project to get BMP from R24 to midi sync BPM**

This try to take BPM from tempo LED on Zoom R24<br />
and make tempo Midi sync with 24 ticks per quater note.<br/>

Because I'm not so adanced to analyse what's happended on USB port between two R24 when they are programmed as master/slave.<br />
I don't want to open my R24 to get electric signal from LED.
Bonus, normaly you can use it for all things with a LED for BMP visualisation.
***

## Hardwares

* [Zoom R24](https://zoomcorp.com/fr/ca/m%C3%A9langeurs-num%C3%A9riques--enregistreurs-multipistes/m%C3%A9langeurs-num%C3%A9riques--enregistreurs-multipistes/r24/)
* [Arduino MICRO 5Volts](https://store.arduino.cc/products/arduino-micro)

***

## Softwares
* [Arduino IDE](https://www.arduino.cc/en/software)
* this developpemnt
***

### Contributors
* Me !
***
### Description
1. Get the number of beat for the pre-count before sending start midi message (between 2 to 5).<br/>
2. From the red LED on a R24 from Zoom, catch the tempo with a photodiode.<br/>
3. Pass the pulse signal from the phtotdiode by a trigger for a proper square wave.<br/>
4. Input the pulse on a digital port on Arduino.<br/>
5. Calculate the bpm by measuring time between two beat.<br/>
6. Divide it by 24 to obtain the time between two ticks that we have to send by midi.<br/>
7. Make a timer pulse with 24 interrupts by beat using preceding calculs.<br/>
8. Send on each interrupt F8h to serial port as midi port.<br/>
