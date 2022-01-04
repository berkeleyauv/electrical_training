# Reference Solution

One important thing to note is that the engineering process is not always a straightforward path. Often times, issues - some of which are out of our control - may pop up in later steps that cause us to go back to the drawing board to address them. For example, requirements may change, parts may become unavailable, or during layout it becomes impossible to meet a certain physical form factor.

Every section here is worth an entire discussion all on its own. In the interest of time and acknowledging that there are far better resources out there, we'll keep things brief. Electrical engineering is a huge field but don't be afraid to dive down the rabbit hole here and there.

## Block Diagram

With the project requirements set, we can start with a high-level block diagram that illustrates the major building blocks in our solution. The main thing to consider is how the blocks would work together to meet the requirements and how to turn them into circuit-level pieces in the next step.

<p align="center">
    <img height="200px" src="imgs/block.png"/>
</p>

The above block diagram implements a very typical architecture for solving problems which is to have a main CPU running some firmware that talks to peripheral sensors and actuate some effectors. In our case, the microcontroller (MCU) will run code that takes in readings from an accelerometer to measure the gravity vector, giving us the angle. The button allows the user to set a target angle and the LED provides an indicator for meeting the target. Power comes in through the USB port.

## Part Selection

Ultimately, choosing parts boils down to balancing various desirable traits to turn the block diagram into an actual design. I typically start by pulling ideas from other designs or past experience. Beyond that, I like to search using major electronics distributors like Digikey as well as going directly to a manufacturer's website. Parts manufacturers typically also provide customer service to further aid in the parts search.

For this solution, the focus was on a fast turnaround time and using already purchased parts. To achieve that, we compromised on things like cost, size, and power draw. We'll use the STM32F401CEU6 as the microcontroller, the LSM6DSM as the accelerometer, and the MIC5365 as the regulator. For passive parts like resistors and capacitors, I typically leave the exact part choice until the very end since there's usually many alternates.

## Schematic



## Layout

## Manufacturing

## Firmware

## Test!

lsm6dsm, usb powered, leds, button, interrupt pins

osbridge
    usb, boot button, rst button, swd/uart debug, spi/i2c/uart conn