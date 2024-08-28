# Underwater Robotics @ Berkeley | Electrical Training

Hello there! Welcome to UR@B electrical team! UR@B Electrical training will introduce you to basic circuit concepts, and firmware. Additionally, the HOPE Decal content created by IEEE @ Berkeley will introduce you to printed circuit board CAD tools. 

> "*Note: Feel free too ask/wait for a electrical team member to help you when working on this training to prevent frustration.*"

> "*Note: If you already feel comfortable with all the concepts below, feel free to skip this whole training all together.*"

### Pre-requsites:
- None

At the end of the training, you will know: 

1. Basic Circuit (Electronic) Concepts
2. Basic Firmware
3. Basic Printed Circuit Board Design (PCB) CAD Tools 

### High Level View:
<p align="center">
    <img src="./imgs//urclub_highlevel_overview.png"/>
</p>
In the electrical team, you will be creating the electronics and the associated software to make it work. 

<br>

**Technologies Used:** C, RP2040, Raspberry Pi Pico, pico-sdk, VMWare Workstation Pro, Linux (Ubuntu), etc...

> "*Note: For each part, click on the dropdown to show the content.*"


# Prelab: Electronics (Hardware) - Part 1

You will learn about the concept of ground, voltage, current and various machine tools used in electrical engineering. 

<details>
<summary>Electronics Dropdown</summary>

## Current
Current is the rate at which electrons (particles) flow. Remember that particles are physical in nature. 

## Voltage 
Particles will stay still unless there is enough pressure to get them moving. Voltage is the difference in electric potential energy between two points. 
It is the **"Push"** that gives pressure to push electrons (particles) through a circuit. 

## Reference Voltage (Ground) 
<p align="center">
    <img height="200px" src="./imgs/reference_mountain.png"/>
</p>
Reference voltage commonly referred to as **ground** is a value that can be used with respect to everything else. 
One example is that "Earth ground" can be used as the reference voltage but most times the reference voltage is relative to the application. 

</br>

**"Common" ground** is the reference voltage that is shared across
the whole application. 

> **V_GND = 0 V**

Most times, zero volts are used as the reference voltage to make calculations easier.  

Note that the reference voltage may not necessarily be 0 volts, It can be any value as long as the circuit designer is consistent. 

## Resistance
Resistance is the opposition to the flow of current. Everything has resistance including wires itself. 

## Ohm Law
<p align="center">
    <img height="200px" src="./imgs//Ohms-law.jpg"/>
</p>
Image Credits: Build-electronics-circuit / Oyvind Nydal Dahl

</br>

Bringing it all together with Ohm's Law.  

> Voltage = Current * Resistance
 
> Current = Voltage / Resistance

> Resistance = Voltage / Current 

## Hardware Equipment
> Note: Please ask if you are interested in getting hands on experience with these machines.

### Power Supply Unit
Power supply unit provide a voltage source. 

### Multimeter
Measures Voltage, Current, and Resistance.

### Oscilloscope
Mainly used for tracking "signals". Oscilloscope is a multimeter but able to provide a graph of voltage over time. 

## Lab: An Application-LED (Optional)
> Note: Please ask if you are interested in doing the LED application. It is a simple lab that walks you through how to get a LED to work.

</details>

> Checkpoint: No Checkpoint for Part 1

## Firmware (Software) - Part 2
> "*Note: Feel free too ask/wait for a electrical team member to help you when working on this to prevent frustration.*"

With the **RP2040** microcontroller which is part of the Raspberry Pi brand. 

<details>
<summary>Firmware (Software) Dropdown</summary>

### Development Environment Setup
Setting up Ubuntu with VMWare Workstation Virtual Desktop 

- Download VMWare Workstation Pro from broadcom.com
- Download Ubuntu24.04 LTS ISO
- Add the Ubuntu to VMWare
- In the Ubuntu Create 2 folders:
    - “development”, “program_files”
        - Do this by opening command line and going to the root directory. ~/
        - run “mkdir development”
            - It will be used to do any development
        - run “mkdir program_files”
            - Stores program files that you will see below such as picotool and pico-sdk
- Recommendation: Use one Package Manager. Ubuntu has “Snap” and “APT” . I recommend using “APT” and staying consistent.
- Some Notes: Adding Environment Variables
    - Used when Building and compiling projects so programs know where files are
        - vim ~/.basrhc
        - Add by using EXPORT VAR_NAME=”/path”
- Download VSCode by Googling “VScode Ubuntu” and downloading the .deb file
    - Open a terminal and goto the “Downloads folder” then run “sudo apt install ./<filename>.deb”
    - You can now run “code .” in directories in the SHELL to open VSCode for a directory.
    - Other method of installing: sudo snap install code --classic
- Download “Github CLI”. “gh” in APT package manager
    - run “gh auth login” and login to github.
- Packages Needed: sudo apt install gh git curl screen

Some Command Line

- ls -la
- ls
- cd …

**Setting up Raspberry Pi Development:**

#### Creating your first RP2040 Project

#### Debugging: Monitor


1. SETUP: goto program_files and clone [raspberrypi/pico-sdk (github.com)](https://github.com/raspberrypi/pico-sdk)

</details>

> Checkpoint: Blinking LED

## PCB ECAD Tools - KICAD - Part 3

Instead of using prototyping boards like stripboards and breadboards, you will now create a "PCB" which makes your electronics much more versatile. Instead of wires failing off, the wires can't fall off printed circuit boards. Like how 3D Printing design uses CAD tools like Solidworks, electrical engineers use electronic computer aided design (ECAD) like KiCad. 

<details>
<summary>PCB ECAD Tools Dropdown</summary>

Too get used to the KiCad ECAD software, please follow the HOPE course. 
#### Hands on PCB Engineering (HOPE) | IEEE @ Berkeley
IEEE @ Berkeley has created a awesome decal (course) on printed circuit board design. All content and credits goes to staff at the Hope Decal
##### See HOPE Decal- https://ieee.berkeley.edu/hope/
If the link does not work, please search for: IEEE Berkeley HOPE Decal
<br>
**For underwater robotics, Please do the following content and associated labs:**
1. Install Kicad
2. Light Sensor Schematic
3. Light Sensor Components
4. Light Sensor Layout
5. USB Charger Components (Optional)
6. USB Charger Schematic (Optional)
7. USB Charger Layout (Optional)
<p align="center">
    <img src="./imgs/hope_decal_schedule.png"/>
</p>

</details>

> Checkpoint: The DRC for both schematic/layout should show no errors. DRC - Design Rule Checker.

# Design
We did not at all cover the "Design" aspect of electrical engineering, searching for answers through your coursework, using search engines, and asking questions are the best way to learn "Design". 

Here are some keywords that outlines the steps to make a design work:
1. Planning
2. Tapeout
3. Bringup
4. Implementation

# Bringing it all together... (OPTIONAL - NOT MANDATORY)
To see an example, see: [Example](./example_design/README.md)
<p align="center">
    <img src="./imgs/example_design/block.png"/>
</p>

# Notes

### Software:

#### Git/Github
If you need help setting up Git/Github, use a search engine and search for "CS 61B Lab01: Setup" Lab. 