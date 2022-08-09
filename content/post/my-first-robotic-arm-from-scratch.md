---
timeToRead: 0
authors: []
title: 'My first robotic arm from scratch '
excerpt: My first robotic arm from scratch need more text
date: 2022-08-01T06:00:00+00:00
hero: "/images/1656695893263.jpg"

---
There are thousands of robotic kits you can buy online that come with pre-cut parts for any type of robot. To me that wasn't enough I wanted to design a robot from scratch, using my own brain. In order for me to design the robot, I needed to learn a software called [Fusion 360](https://www.autodesk.com/products/fusion-360/overview?term=1-YEAR&tab=subscription), which is a CAD (computer-aided drafting) program.

## So here was my process

I started by creating a base for the robot arm to sit on and use to swivel around. In order to allow the swivel movement to work, I had to create a slot for a servo to sit in, so I got the dial calipers and measured the width and height of the servo.


![](/images/img_7579.JPG)
![](/images/botbase.PNG)
Next, I needed a piece that I could use as a connecter for the servos and the other parts, so I measured the top of a servo as a starting point for the connecter.


![](/images/img_7578.JPG)
![](/images/botelbow.PNG) 

I also had to measure the key piece so I could actually move all the other parts, I put the cutout on every main piece of the robot.


![](/images/img_7580.JPG)
![](/images/botarm.PNG)
![](/images/bottopper.PNG) 

These are all the final pieces of the robot laid out together, this whole process took about a month after I finished learning Fusion 360. 

![](/images/botall.PNG)

Once I finished all of the parts I put them together in Fusion 360, so I could get a preview of the finished robot.

![](/images/fusion.gif)

After I was satisfied with the end result I 3D printed the parts with the [Ender v3 3D printer](https://www.amazon.com/Official-Creality-3D-Printer-Source/dp/B07D218NX3).

![](/images/3dprint.gif)
Here are the parts after they have been printed


![](/images/1656695893361.jpg)

I now have all the parts but I have no way to make them move, so I need to connect the motors to all the joints.

![](/images/image1.jpeg)

controlling one servo on a raspberry pi is relatively easy with python, but it's next to impossible to control multiple servos at the same time. luckily using the Adafruit Motor/Stepper/Servo Shield you can control up to 16 different servos at the same time.

![](/images/1657125534297.jpg) 

Unfortunately, the pins for the servo hat do not come pre-soldered, so I had to learn how to solder in order to continue with the project. funny enough I now have a scar because I dropped the hot soldering iron on my thigh.

  
![](/images/1657125534571.jpg)
![](/images/solderin2g-1.gif)

![](/images/img_7576.JPG)

now walk thru what packages you needed to write the python code

and examples of the python code

images and code blocks

```js
sudo apt-get install python-smbus
sudo apt-get install i2c-tools
sudo pip3 install adafruit-circuitpython-servokit
```

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

now show the final product and future scope and what could be built

![](/images/img_7577.JPG)

![](/images/obs.gif)