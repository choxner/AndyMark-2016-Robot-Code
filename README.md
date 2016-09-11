# AndyMark Robot in 3 Days Code Documentation
![Image of the robot.](https://raw.githubusercontent.com/choxner/AndyMark-2016-Robot-Code/master/AndyMark-2016-Robot-Code/Reference/am_2016_robot.jpg)

This is the documentation for the LabVIEW code written for the 2016 *FIRST* Robotics Competition robot built by AndyMark. All code is written by *FIRST* Robotics Competition Team #2655, The Flying Platypi. The code is accessible on [GitHub](https://github.com/choxner/AndyMark-2016-Robot-Code). Additional code written by Team #2655 can be found [here](https://github.com/FRC-Team2655).


## Motors
|PMW|Motor ID|Purpose|
|:-:|:-:|:-:|
|0|Drive Motors|Controls the left side of the drive train|
|1|Drive Motors|Controls the right side of the drive train|
|2|Ball Intake|Intake or ejects boulders|
|3|Collector Arm|Raises and lowers the ball intake attatchment|
|4|Shooter|Shoots boulders into the high goal|
|5|Low Arm|Controls the lower half of the climbing mechanism|
|6|High Arm|Controls the upper half of the climbing mechanism|

## Teleop
![Teleop .vi](https://raw.githubusercontent.com/choxner/AndyMark-2016-Robot-Code/master/AndyMark-2016-Robot-Code/Reference/Teleop%20Screenshot.PNG)


## Drive Train
The six pneumatic wheels of the drive train are controlled using an arcade drive system on the two joysticks of the controller. Driving forward or backward uses the left joystick and turning uses ther right joystick. Each side of the drive train is controlled by a Victor motor controller. Each axis controlled by the arcade drive system is edited by the Joystick_Sensitivity.vi, which adds a deadband and a ramp rate to the input of the motors to simplify driving the robot.
![Joystick_Sensitivity.vi](https://raw.githubusercontent.com/choxner/AndyMark-2016-Robot-Code/master/AndyMark-2016-Robot-Code/Reference/Joystick_Sensitivity%20Screenshot.PNG?raw=true)


## Ball Intake
The ball intake mechanism is used to intake or eject boulders. It is controlled by the left trigger and the left bumper on the controller. If the left trigger is pressed a boulder can be sucked in, which will be a negative input for the motor controller. If the left bumper is pressed the boulder will be ejected, which will be a positive input for the motor controller. These values are added together so that in the case both the trigger and the bumper are pressed the ball intake will not move. This code can be found in the Teleop .vi above.


## Collector Arm
The collector arm is raised and lowered as to be able to use the ball intake. This mechanism can also be used to cross the Cheval de Frise. It is controlled with the right trigger and the right bumper. When the right trigger is pressed the collector arm will be raised and when the right bumper is pressed it will be lowered. Similar to the ball intake system these values will be added together as a safety measure. This code can be found in the Teleop .vi pictured above.


## Shooter
The shooter motor that launches boulders into the high goal is controlled using the back button and the start button on the controller. While the back button is pressed the shooter will spin backwards. The start button functions as a toggle using the Shoot_Toggle .vi as shown below. This toggle will set the output to true if the start button is pressed once and return to false when the start button is pressed a second time. This can be seen in the Teleop .vi.
![Shoot_Toggle .vi](https://github.com/choxner/AndyMark-2016-Robot-Code/blob/master/AndyMark-2016-Robot-Code/Reference/Shoot%20Toggle%20Screenshot.PNG?raw=true)


## Climbing Mechanism
The climbing mechanism is split into two parts, the low arm and the high arm. The low arm is controlled by the A button and the B button. The B button raises it and the A button lowers it. The high arm is conrolled by the X button and the Y button. The Y button raises it and the X button lowers it. This is shown in the Teleop .vi.
