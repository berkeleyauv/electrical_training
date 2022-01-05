# Reference Solution

One important thing to note is that the engineering process is not always a straightforward path. Often times, issues - some of which are out of our control - may pop up in later steps that cause us to go back to the drawing board to address them. For example, requirements may change, parts may become unavailable, or during layout it becomes impossible to meet a certain physical form factor.

Every section here is worth an entire discussion all on its own. In the interest of time and acknowledging that there are far better resources out there, we'll keep things brief. Electrical engineering is a huge field but don't be afraid to dive down the occasional rabbit hole.

## Block Diagram

With the project requirements set, we can start with a high-level block diagram that illustrates the major building blocks in our solution. The main thing to consider is how the blocks would work together to meet the requirements and how to turn them into circuit-level pieces in the next step.

<p align="center">
    <img height="200px" src="imgs/block.png"/>
</p>

The above block diagram implements a very typical architecture for solving problems which is to have a main CPU running some firmware that talks to peripheral sensors and actuate some effectors. In our case, the microcontroller (MCU) will run code that takes in readings from an accelerometer to measure the gravity vector, giving us the angle. The button allows the user to set a target angle and the LED provides an indicator for meeting the target. Power comes in through the USB port.

## Part Selection

Ultimately, choosing parts boils down to balancing various desirable traits to turn the block diagram into an actual design. I typically start by pulling ideas from other designs or past experience. Beyond that, I like to search using major electronics distributors like Digikey as well as going directly to a manufacturer's website. Parts manufacturers typically also provide customer service to further aid in the parts search.

For this solution, the focus was on a fast turnaround time and using already purchased parts. To achieve that, I compromised on things like cost, size, and power draw. We'll use the STM32F401CEU6 as the microcontroller, the LSM6DSM as the accelerometer, and the MIC5365 as the regulator. For passive parts like resistors and capacitors, I typically leave the exact part choice until the very end since there's usually many alternates.

## Schematic

For our team, we use KiCad since it's open-source and surprisingly powerful. Other software to be aware of particularly in industry are Autodesk EAGLE, Altium Designer, and Cadence Allegro. Every board design starts with a schematic symbolically detailing which components are to be used and how they are connected. For this solution, it really boils down to taking each part and looking at its datasheet or reference designs to figure out what components are needed to make the part work in the larger design. Manufacturers typically also provide engineering support.

Since this architecture is so common, let's take a look at the things one would consider when turning each block into a circuit.

### Power

Every time I start a project, I always like to ask how is the device powered? It's important to consider the voltage and current ranges as well as the noise coming in. Are there any safety concerns or desired behavior in extreme conditions? Based on what all of the other parts need, these things will determine how exactly all of the different components in your device are to be powered.

In our case, we're going to keep things simple. It'll be USB powered only. Looking at the rest of the parts, they'll all work on 3.3V which is pretty standard. None of the parts draw very much power or have special noise requirements. An LDO to drop the voltage from 5V to 3.3V will work just fine and has a really simple circuit.

<p align="center">
    <img height="200px" src="TODO"/>
</p>

### Microcontroller

For most microcontrollers and even microprocessors and FPGAs, getting them working boils down to completing the following sections.

- **Power** - what voltages and currents does it need? how about power sequencing?
- **Strapping** - a.k.a. boot or bootstrapping, are there any pins that need to be configured to get the desired behavior such as booting from flash?
- **Clocks** - are there any required input clocks or is the common internal oscillator adequate? is there a required accuracy?
- **Programming** - how will the device be programmed? via SWD/JTAG or a bootloader?
- **Peripherals** - is there anything special that needs to be added to communicate with the other devices such as voltage translation or transceivers?

<p align="center">
    <img height="200px" src="TODO"/>
</p>

### Accelerometer

Getting most peripheral chips working involves the exact same steps as getting a microcontroller working. In fact, most of the time the datasheet includes a complete circuit that you can just copy in to your design.

<p align="center">
    <img height="200px" src="TODO"/>
</p>

<p align="center">
    <img height="200px" src="TODO"/>
</p>

## Layout

footprint assignment, board stackup, noise, pours, thermals, trace width/space

## Manufacturing

gerbers and drill files, popular manufacturers

solder techniques

## Firmware

zephyr

## Test!

f401, lsm6dsm, usb powered, leds, button, interrupt pins

osbridge
    usb, boot button, rst button, swd/uart debug, spi/i2c/uart conn
