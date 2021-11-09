# Lab_5
Intro to Embedded Systems Lab 5
The purpose of this code is to generate a hardware PWM that controls the brightness of an LED. The goal was to write a code that generated a 250 ms delay with a 20% duty cycle.
This code is very similar to the software version, except that it uses a physical timer which uses interrupts to toggle the LED. 
We set P1.6 as the output pin and then figured out what values should be used for TACCR0 and TACCR1. 
To find TACCR0 you need to solve for ((frequency * period)/clock divider) - 1. 
We decided to use the SMCLK which has a frequency of 1MHz and a clock divider of 8 to get the TACCR0 value to be 31249. 
To find TACCR1 we take the value for TARRC0 and multiply it by 20, and then divide that by 100.
TACCR1 = (31249 * 20)/100 = 6249.8 
