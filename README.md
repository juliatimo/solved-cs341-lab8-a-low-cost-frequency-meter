Download Link: https://assignmentchef.com/product/solved-cs341-lab8-a-low-cost-frequency-meter
<br>
In this lab, you will learn about waves. In part 1 you will experiment with a function generator and an Oscilliscope to understand the relationship between frequency, and period. In part 2 you will create a frequency meter that calculates the frequency and period of an incoming signal. The starter code can be found on GitHub under Lab 8.<strong> </strong>

Background Information

This lab is based on an article “<em>A simple, low cost, precision frequency meter uses only two pins of a PC parallel port</em>” written by Radovan Stojanovic  published in the Design Ideas section of the EDN magazine. The setup is shown in figure 1:

The computer runs a program that reads the state of pin 10 of the line printer port (LPT1). By measuring the time when the pin is high and the time when pin is low as shown in figure 2,

the program computes the pulse width and the period. The frequency of the square wave generator f<sub>IN</sub> is calculated using:

frequency = 1 / Period




In this lab, we will program the computer to read the state of an I/O pin that is connected to a pulse generator. The pulse width is measured using a polling method (we keep checking in a while loop) to determine if the state of the I/O pin has changed using the following pseudo code:

get the current_time_1;

here:     if pin is high, loop here;

get the current_time_2;

width= current_time_2 – current_time_1;




The period is obtained by adding the pulse width (the length of time the pin was high) and also the duration when the I/O pin is low.

Part 1




In part 1 we are going to experiment with the function generator and oscilloscope. The function generator outputs a signal in a wave (you can imagine the graph y = sin x), and the oscilloscope displays it. You should drag them into your project and connect them like this:

On the oscilloscope, the only setting we can change is the scale of the x-axis. The settings on the function generator work as follows:

Frequency: how many times the wave will be repeated in 1 second

Amplitude: The difference in voltage between the top of the wave and the bottom of the wave

DC Offset: the voltage amount that the wave is centered at

Function: change between rectangular, smooth, or triangular wave




Setup the function generator with frequency 1Hz, amplitude 5V, offset 2.5V, and function set to square. Now try changing the oscilloscopes scale so that you can see a few waves (try 200ms if you are completely lost). You should see something like this.

Try changing the frequency and look at the resulting change in the period. Does the period grow longer or shorter?

Part 2

In part 2 we will be creating a program that reads a signal and calculates the frequency and period. Connect the function generator to pin 10 and GND as seen in the picture.

Using the method described in the background section as a guide, calculate the frequency and period of the incoming signal. Pay close attention to the pseudocode on page 2, and the comments in the starter code. Also, be aware that the micros() function returns a result in microseconds.