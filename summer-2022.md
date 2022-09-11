# Final Report

## Results

I built a web-based application that allows users to perform and record HRI experiments in VR. Since this project is a continuation from last semester, I will only mention what is new (the previous report can be found here):
1. T
2. The VR environment is much improved due to the integration of a physics library called RAPIER. Objects will now collide with each other and can be manipulated realistically (grasped, dropped, thrown, etc.). Objects can now also be articulated.
4. Two new tasks have been created, which take advantage of the physics engine: the stacking task involves creating a stack of blocks that does not tip over while the pick and drop task involves placing blocks into a box and then closing the lid. 
5. A tutorial has been added for each type of interaction (drag contol, grasping, etc.).
5. A variety of new control methods have been added that take full advantage of the Oculus controller, most notably the haptic motors.

In addition, I designed and built a bridge between my system and Alex's that allows users to record an experiment in my application and then visualize/play it back in Alex's. This is done using two hosted Google Apps Scripts that act as endpoints for storing and extracting data. A more detailed explanation of how this works can be found [here]. 
