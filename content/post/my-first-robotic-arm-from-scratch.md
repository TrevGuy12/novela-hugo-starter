---
timeToRead: 0
authors: []
title: 'My first robotic arm from scratch '
excerpt: My first robotic arm from scratch need more text
date: 2022-08-01T06:00:00+00:00
hero: "/images/1656695893263.jpg"

---
explain the process and each step in fusion for each part

7 parts and images for each (measurements with the caliper etc)

![](/images/img_7579.JPG)
![](/images/botbase.PNG)
![](/images/img_7578.JPG)
![](/images/botelbow.PNG)
![](/images/img_7580.JPG)
![](/images/botarm.PNG)
![](/images/bottopper.PNG)
![](/images/botall.PNG)

***

now show the final design working before it is printed in fusion environments

![](/images/fusion.gif)

***

now you can show the printing process and the parts all laid out

![](/images/3dprint.gif)

![](/images/1656695893361.jpg)

***

now talk about the servos and their connections (the top bracket and how it fits ) and the servos assembled

![](/images/image1.jpeg)

***

now talk thru servos and the pi hat and what it does ...

![](/images/1657125534297.jpg)![](/images/1657125534571.jpg)![](/images/solderin2g-1.gif)

***

![](/images/img_7576.JPG)

now walk thru what packages you needed to write the python code

and examples of the python code

images and code blocks

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

***

now show the final product and future scope and what could be built

![](/images/img_7577.JPG)

![](/images/obs.gif)