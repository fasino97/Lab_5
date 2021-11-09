# Lab_5
Intro to Embedded Systems Lab 5
Question 2

The purpose of this code is to generate a software PWM that controls the brightness of an LED. The goal was to write a code that generated a 500 ms delay with a 10% duty cycle. 
The first step was to set P1.6 as the output pin and then to figure out what values should be used for TACCR0 and TACCR1.
To find TACCR0 you need to solve for ((frequency * period)/clock divider) - 1. 
We decided to use the SMCLK which has a frequency of 1MHz and a clock divider of 8 to get the TACCR0 value to be 62499.
To find TACCR1 we take the value for TARRC0 and divide it by the desired clock divider. 
TACCR1 = 62499/10 = 6249.9
TACTL is then writen to show the chosen clock and clock divider and the bit is inverted with every pulse.
