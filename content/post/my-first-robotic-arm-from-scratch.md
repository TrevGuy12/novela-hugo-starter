---
timeToRead: 10
authors:
- Trevor Ortell
title: My First Robotic Arm from Scratch
excerpt: Building a robotic arm from the ground up.
date: 2023-06-01T06:00:00.000+00:00
hero: "/images/obs.gif"
---

# My First Robotic Arm from Scratch

*Estimated Reading Time: 10 minutes*

![Robotic Arm](/images/obs.gif)

## Abstract

In a world filled with robotic kits readily available online, I yearned for a more ambitious challenge: to design and build a robotic arm from scratch, using my own creativity and skills. To embark on this journey, I needed to learn a variety of skills, including using [Fusion 360](https://www.autodesk.com/products/fusion-360/overview?term=1-YEAR&tab=subscription) for CAD (computer-aided drafting), mastering electrical soldering, understanding basic kinetics, and gaining proficiency in Python programming.

## The Design and Modeling Phase

### Base

My journey began with the creation of a sturdy base for the robotic arm. This base would serve as the foundation for the arm's movement. To enable swiveling motion, I had to design a slot to accommodate a servo motor, which required precise measurements.

![Base Design](/images/img_7579.JPG)
![Base CAD Model](/images/botbase.PNG)

### Connector/Elbow

Next, I needed a connector piece to link the servos and other components together. I used the dimensions of a servo as a starting point for this critical component.

![Connector Design](/images/img_7578.JPG)
![Connector CAD Model](/images/botelbow.PNG)

### Arm and Key Slot

The arm's key piece, essential for maneuvering the other components, required careful measurement. I incorporated this key slot into every main part of the robot.

![Arm and Key Design](/images/img_7580.JPG)
![Arm and Key CAD Model](/images/botarm.PNG)

### Base Rotation and Key Slot

At the top of the base, I designed a crucial element with a tongue-and-groove notch and a key for the entire assembly's rotation.

![Base Rotation and Key Slot CAD Model](/images/bottopper.PNG)

### All Parts

These are all the final pieces of the robot, laid out together. This entire design process took several weeks after I had mastered Fusion 360.

![All Robot Parts](/images/botall.PNG)

## The Component Assembly Phase

Once I completed designing all the parts, I assembled them in the Fusion 360 environment to get a preview of the finished robotic arm.

![Assembled Robot in Fusion 360](/images/fusion.gif)

## The 3D Printing Phase

With a satisfying design in hand, I moved on to the 3D printing phase. I used the [Ender v3 3D printer](https://www.amazon.com/Official-Creality-3D-Printer-Source/dp/B07D218NX3) for this step, and the entire print job took approximately 13 hours.

![3D Printing Process](/images/3dprint.gif)

Here are the parts after they have been 3D printed.

![3D Printed Robot Parts](/images/1656695893361.jpg)

## The Servo Phase

Now that I had all the parts, it was time to make them move. I needed to connect the motors to all the joints.

![Servo Motors](/images/image1.jpeg)

### Soldering

Controlling one servo on a Raspberry Pi is relatively straightforward with Python, but it becomes challenging to control multiple servos simultaneously. Fortunately, using the Adafruit Motor/Stepper/Servo Shield, you can control up to 16 different servos concurrently.

![Soldering Equipment](/images/1657125534297.jpg)

Unfortunately, the pins for the servo hat do not come pre-soldered, so I had to learn how to solder, a process that, amusingly, left me with a scar from accidentally touching the hot soldering iron to my thigh.

![Soldering Process](/images/1657125534571.jpg)
![Soldering GIF](/images/solderin2g-1.gif)

### Connecting Wires and Pins

With the hat's pins soldered, I began attaching the servo wires to the hat pins. These wires included:

- Positive: Provides power to the servo
- Negative: Grounds the servo
- Data: Sends data to the servo

![Wiring Servos](/images/img_7576.JPG)

## The Coding Phase

### Setting up the Raspberry Pi

Once the wires were attached, I needed to enable [I2C](https://www.circuitbasics.com/basics-of-the-i2c-communication-protocol/) in the Raspberry Pi configuration file and then rebooted the system for the change to take effect.

![Configuring I2C](/images/i2c.PNG)

### Installing Packages

To make the hat compatible with Python, I had to install several packages.

```python
sudo apt-get install python-smbus
sudo apt-get install i2c-tools
sudo pip3 install adafruit-circuitpython-servokit
```

#### Writing python

The Python code below is relatively self-explanatory. It sets angle values for each pin, controlling the servos' movements.

ex: `(pin \[15\] angle = 180)`

###### Robot.py

```python
from time import *
from adafruit_servokit import ServoKit
kit = ServoKit(channels=16)

kit.servo[15].angle = 0
kit.servo[12].angle = 0
kit.servo[11].angle = 0
kit.servo[4].angle = 0
    
	while True:
        sleep(1)
        kit.servo[11].angle = 60
        sleep(1)
        kit.servo[15].angle = 60
        sleep(1)
        kit.servo[4].angle = 60
        sleep(1)
        kit.servo[12].angle = 60
        sleep(1)
        kit.servo[11].angle = 0
        kit.servo[15].angle = 0
        kit.servo[4].angle = 0
        kit.servo[12].angle = 0
```

![](/images/obs.gif)

## Reflecting phase

After two months of designing, printing, soldering, wiring, and coding, I finally had a working robotic arm. While all the parts, electronics, and code worked seamlessly, the journey was fraught with trial and error, numerous failed prints, constant redesigns, and hours of debugging. Murphy's law seemed ever-present during this robotic creation.

My next steps involve refining the design by increasing the base's size, machining aluminum parts, and upgrading to metal gear servos. I take great pride in the work I've accomplished, and this entire project has been an absolute blast.

![](/images/img_7577.JPG)