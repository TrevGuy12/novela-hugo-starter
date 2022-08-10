---
timeToRead: 0
authors: []
title: 'My first robotic arm from scratch '
excerpt: My first robotic arm from scratch need more text
date: 2022-08-01T06:00:00+00:00
hero: "/images/1656695893263.jpg"

---
There are thousands of robotic kits you can buy online that come with pre-cut parts for any type of robot. To me that wasn't enough I wanted to design a robot from scratch, using my own brain. In order for me to design the robot, I needed to learn a software called [Fusion 360](https://www.autodesk.com/products/fusion-360/overview?term=1-YEAR&tab=subscription), which is a CAD (computer-aided drafting) program.

## Design/modeling phase

#### Base

I started by creating a base for the robot arm to sit on and use to swivel around. In order to allow the swivel movement to work, I had to create a slot for a servo to sit in, so I got the dial calipers and measured the width and height of the servo.

![](/images/img_7579.JPG)
![](/images/botbase.PNG)

#### Connecter/Elbow

Next, I needed a piece that I could use as a connecter for the servos and the other parts, so I measured the top of a servo as a starting point for the connecter.

![](/images/img_7578.JPG)
![](/images/botelbow.PNG)

#### Arm and key slot

I also had to measure the key piece so I could actually move all the other parts, I put the cutout on every main piece of the robot.

![](/images/img_7580.JPG)
![](/images/botarm.PNG)

#### Base rotation and key slot

The top of the base was another very important part that was vital for the rotation of the entire assembly.

![](/images/bottopper.PNG)

#### All parts

These are all the final pieces of the robot laid out together, this whole process took about a month after I finished learning Fusion 360.

![](/images/botall.PNG)

## Component assembly phase

Once I finished all of the parts I put them together in Fusion 360, so I could get a preview of the finished robot.

![](/images/fusion.gif)

## 3D printing phase

After I was satisfied with the end result I 3D printed the parts with the [Ender v3 3D printer](https://www.amazon.com/Official-Creality-3D-Printer-Source/dp/B07D218NX3).

![](/images/3dprint.gif)

Here are the parts after they have been printed

![](/images/1656695893361.jpg)

## Servo phase

I now have all the parts but I have no way to make them move, so I need to connect the motors to all the joints.

![](/images/image1.jpeg)

#### Soldering

controlling one servo on a raspberry pi is relatively easy with python, but it's next to impossible to control multiple servos at the same time. luckily using the Adafruit Motor/Stepper/Servo Shield you can control up to 16 different servos at the same time.

![](/images/1657125534297.jpg)

Unfortunately, the pins for the servo hat do not come pre-soldered, so I had to learn how to solder in order to continue with the project. funny enough I now have a scar because I dropped the hot soldering iron on my thigh.

![](/images/1657125534571.jpg)
![](/images/solderin2g-1.gif)

#### Connecting wires and pins

Now that the hat has all of its pins connected to the pi we can now start attaching the servo wires to the hat pins.

There are three different wires:

* Positive = brings power to the servo
* Negative = grounds the servo
* Data = sends data to the servo

![](/images/img_7576.JPG)

## Coding

#### Setting up the pi

after the wires have been attached I needed to enable [I2C](https://www.circuitbasics.com/basics-of-the-i2c-communication-protocol/) in the raspberry pi config file and then I rebooted the system for the change to be implemented.

![](/images/i2c.PNG)

#### Installing packages

In order for the hat to understand python, I needed to install the following packages.

```js
sudo apt-get install python-smbus
sudo apt-get install i2c-tools
sudo pip3 install adafruit-circuitpython-servokit
```

#### Writing python

The code below is relatively self-explanatory, in essence, we are setting an angle value for each pin.

eg: (pin \[15\] angle = 180)

###### Robot.py

```js
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

## Reflecting phase

After 2 months of designing, printing, and connecting, I finally had a working robot arm, I am truly proud of the work that I have done.

![](/images/img_7577.JPG)

My next steps are going to be refining the design, and making it more stable, I also want to swap the 3D printed parts for machined aluminum parts.

![](/images/obs.gif)