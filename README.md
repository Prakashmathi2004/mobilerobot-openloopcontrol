# MobileRobot-Openloopcontrol
## Aim:

To develop a python control code to move the mobilerobot along the predefined path.

## Equipments Required:
1. RoboMaster EP core
2. Python 3.7

## Procedure

Step1:  

Use from robomaster import robot.
<br/>

Step2:

Choose the x,y,z - axis movement distance(meters).
<br/>

Step3:

Give ep_chassis.move to move straight.
<br/>

Step4: 

Give time.sleep() for a break.
<br/>

Step5:

Give ep_chassis.drive_speed to have a circular movement.
<br/>

## Program
~~~
'''
Developed by: PRAKASH M
Register number:212222100035
'''

rom robomaster import robot
import time
from robomaster import camera

if _name_ == '_main_':
    ep_robot = robot.Robot()
    ep_robot.initialize(conn_type="ap")

    ep_chassis = ep_robot.chassis

    '''
    x = x-axis movement distance,( meters) [-5,5]
    y = y-axis movement distance,( meters) [-5,5]
    z = rotation about z axis ( degree)[-180,180]
    xy_speed = xy axis movement speed,( unit meter/second) [0.5,2]
    # '''

    ep_camera = ep_robot.camera
    ep_led = ep_robot.led

    print("Camera streaming started...")
    ep_camera.start_video_stream(display=True, resolution=camera.STREAM_360P)  

    ep_led.set_led(comp="all",r=255,g=0,b=0,effect="on")   
    time.sleep(2)
    


    ep_chassis.move(x=1.5, y=0, z=0, xy_speed=0.75).wait_for_completed()

    ep_chassis.move(x=0, y=0, z=-135, xy_speed=1).wait_for_completed()

    ep_chassis.move(x=1.7, y=0, z=0, xy_speed=0.75).wait_for_completed()

    ep_chassis.move(x=0, y=0, z=135, xy_speed=1).wait_for_completed()

    ep_led.set_led(comp="all",r=0,g=0,b=255,effect="on")
    time.sleep(2) 
   
    ep_chassis.move(x=1.5, y=0, z=0, xy_speed=0.75).wait_for_completed()
   
    ep_chassis.move(x=0, y=0, z=90, xy_speed=1).wait_for_completed()

    ep_chassis.move(x=1.5, y=0, z=0, xy_speed=0.75).wait_for_completed()

    ep_chassis.move(x=0, y=0, z=-50, xy_speed=0.75).wait_for_completed()

    ep_led.set_led(comp="all",r=0,g=255,b=0,effect="on")
    time.sleep(2)
    ep_chassis.drive_speed(x=0.3,y=0,z=20)
    time.sleep(12)
    ep_chassis.drive_speed(x=0,y=0,z=0)

    ep_camera.stop_video_stream()
    print("Stopped video streaming...")

    ep_robot.close()

~~~

## MobileRobot Movement Image:

![mo](https://github.com/Prakashmathi2004/mobilerobot-openloopcontrol/assets/118350045/bb4202cb-6370-4683-b861-4446775cd532)

<br/>
<br/>
<br/>
<br/>

## MobileRobot Movement Video:

https://youtu.be/KuAtuhShlDw
<br/>
<br/>
<br/>
<br/>

## Result:
Thus the python program code is developed to move the mobilerobot in the predefined path.


<br/>
<br/>

```
Mobile Robotics Laboratory
Department of Artificial Intelligence and Data Science/ Machine Learning
Saveetha Engineering College
```
