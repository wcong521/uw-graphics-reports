# Final Report

## Results

I built a web-based application that allows users to perform and record HRI experiments in VR. Since this project is continued from the previous semester, I will only mention what is new (the previous report can be found here):
1. The code exposes a "task-condition" interface where the user can create conditions (as a list of configurable modules) and assign them to specific tasks. 
2. The VR environment is much improved due to the integration of a physics library called RAPIER. Objects will now collide with each other and can be manipulated realistically (grasped, dropped, thrown, etc.). Objects can now also be articulated.
4. Two new tasks have been created, which take advantage of the physics engine: the stacking task involves creating a stack of blocks that does not tip over while the pick and drop task involves placing blocks into a box and then closing the lid. 
5. A tutorial has been added for each type of interaction (drag contol, grasping, etc.).
5. A variety of new control methods have been added that take full advantage of the Oculus controller, including the haptic motors.

In addition, I designed and built a bridge between my system and Alex's that allows users to record an experiment in my application and then visualize/play it back in Alex's. This is done using two hosted Google Apps Scripts that act as endpoints for storing and extracting data. A more detailed explanation of how this works can be found [here]. 

## Work

The first six weeks of the semester I spent refactoring my existing code into the "task-condition" system mentioned above and integrating RAPIER into the application. The latter was easily the most challenging thing I did. Originally, the goal was to write code that could generate the correct physics components from a URDF file, including the joints and joint motors. Yeping and I spent around a month on this problem and since there were no examples or documentation of this process online we created simple physics models to find and account for every difference between RAPIER and URDF ourselves. This proved to be extremely time-consuming and difficult. After receiving some help from the developers, we eventually figured out how to generate the correct rigid-bodies and colliders from a URDF (and for all other objects in the scene) but could not find a solution for controlling the joint motors accurately. After receiving no response from the developers regarding this problem, we concluded that it was a problem with the RAPIER library itself and decided it was not worth pursuing any further. 

The rest of the semester was spent creating more tasks and modules for the application and building a bridge that could connect my application with Alex's. While it took some time to decide on a method of data transfer that could operate under the limitations of the Google Drive environment while still being able to support changes in the future (real-time), the process was relatively straightforward and we were able to get everything working as intended.

## Learning

I learned a lot from my struggles with RAPIER, not only about how physics engines work but also how to approach problem solving without any guidance or external help whatsoever--specifically how to break a complex problem down into simple toy problems, learn how each component works or doesn't work, and then build up to increasingly more complex scenarios.

I also learned that I need to communicate more than I think I do. A lot of the things I was doing earlier in the semester did not end up working and so I felt reluctant sharing those failures, though now I understand that it is important for others to hear about the things I tried that didn't work and specifically why they didn't work. 
