# Analog Digital Converters

In general, sensor outputs start as an analog signal. An ADC takes the analog signal and converts it to a digital signal. Another way to think about this is the concept of converting floating-point numbers to an integer. For example, take the floating numbers {0, 2.2, 4.1, 5.6}. Converting these to integers, we would get {0, 2, 4, 6}.

An ADC follows this concept, but it does not mean that it can only represent integer values. The resolution, or the smallest change in value that can be described, is dependent on the number of bits the ADC has. This is similar to the number of places after a decimal, but not the same.

Let's consider an example:

We have an ADC with 4 bits. Each bit can be either high (1) or low (0). A general rule to remember with ADCs is that the number of possible values the ADC can represent is equal to 2^m, where m is the number of bits.

This means our 4-bit ADC can represent $$2^4$$ or 16 possible values.

Now, let's say that a sensor outputs a signal from 0 to 5 Volts. If we want to find the resolution of  our ADC in Volts we can take the range of the sensor and divide it by the number of steps taken by the ADC:

$$(5V-0V)/(2^4 - 1) = 5V/15 = 0.333V.$$

* Notice that we are using the number of bits minus 1 (15). Although we have 16 values that can be represented by the ADC, the number of steps it takes from 0 to 5V (the range of our sensor) is 15. For example, if we start at a value of 0 and go to 1, two values need to be represented, but only one step is taken.

------

## Successive Approximation Method

This is the most popular method for converting analog signals to digital signals.

Here is a Block Diagram taken from the STM microelectronics website.  [ADC/images/SAR Block Diagram.png]
