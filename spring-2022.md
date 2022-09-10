# Final Report

## Project Files

1. (VR Training Platform for Robot Teleoperation) https://github.com/wycongwisc/urdf-loader-test-vr

The application is hosted [here](https://wycongwisc.github.io/urdf-loader-test-vr/) and all data is sent to [this Google Drive folder](https://drive.google.com/drive/folders/1T90hAXaHdQIh-kv27N346yu3MOC9gFvM?usp=sharing).

## Bibliography

Papers relating to our research area (robot teleoperation in VR):

1. The Influence of Gaming Experience, Gender and Other Individual Factors on Robot Teleoperations in VR, Freder
1. Multi-View Merging for Robot Teleoperation With Virtual Reality, Wei.
1. Spatial Computing and Intuitive Interaction: Bringing Mixed Reality and Robotics Together, Delmerico.
1. Skill-based human–robot cooperation in tele-operated path tracking, Enayati.
1. Virtual Kinesthetic Teaching for Bimanual Telemanipulation, Jang.


## Results

I built a web-based application that allows users to teleoperate robots (Sawyer and UR5) in VR. The system is primarily oriented towards teleoperation *training* and features a VR interface that is used to provide instructions and navigation. However, it also serves as a "sandbox" platform where a number of features can be enabled and disabled, including different tasks (pose matching and pick and place), control modalities (drag control and remote control), motion recording, and other VR-related features (teleportation, monoscopic vision, no parallax, etc.).

All data is stored in a Google Sheets backend using Google Apps Scripts and the Google Sheets API. Though it may be somewhat unconventional, it is fully functional and allows data to be quickly accessed and viewed in the browser. Jupyter notebook scripts can then access this data and perform any necessary manipulations/analysis. Due to the system's flexibility and its data collection/analysis features, it can be used to run studies both in person and remotely (without supervision) using the VR UI. 

The documentation I wrote throughout the semester is outdated; since I will be continuing this project in the summer, it is not a huge deal though I will be sure to finalize everything when I do pass it to someone else.

## Process

Through the first few weeks of the semester, I cleaned up my code from the previous semester and added a finite state machine library to handle internal logic. I also spent some time looking into various data collection methods. We wanted to keep the application lightweight and use GitHub Pages for hosting, so we settled on using a deployed Google Apps Scripts that interacts with the Google Sheets API. (I know you aren't a big fan of how we did this, but it is at least working for our purposes right now and we can always switch to a more standard approach. Regardless of whether we keep using it in the future, I think we learned a lot about its benefits and limitations. I also wrote a [tutorial](https://github.com/wycongwisc/urdf-loader-test-vr/blob/master/google-sheets-api-tutorial.md) that people in the future can reference if necessary.)

I also spent a lot of time looking for a framework or library that could help with building user interfaces in VR. There was a surprisingly small amount to choose from and most of the popular ones required an overhaul of my code (see react-xr, react-three-fiber, react-three-flex), so we ended up settling on something [simple](https://github.com/felixmariotto/three-mesh-ui).

The rest of the semester was spent implementing the features that we wanted, including drag control, remote control, teleportation, pose matching, workspace visualization, task navigation, UI interaction (ray casting), and some other user experience features. In the last two weeks of the semester, I ran a "study" with a group of friends to test the system from end-to-end. Though the sample size was really small and the process wasn't very formal, the system held up, indicating that it was/is ready to be used for something more formal in the future (after some minor adjustments). An informal analysis of the data can be found [here](https://colab.research.google.com/drive/1psiZMpPRj4CqYt5aRHmWur2hjQKrv-7e?usp=sharing).

While the development process was a lot smoother than last semester (especially after I discovered how to run localhost on the Quest), maintaining the quality of my code and making the correct software design decisions so that new features didn't break old features was challenging. 

## Learning

I don't think there was anything I did this semester that I had already done in the past, so I won't bother listing the same things again (see previous sections). Some other interesting problems that I didn't mention:
1. How to implement a relatonal database using spreadsheets and how to ensure that joins are lossless
1. How to log data efficiently using a buffer
1. How to reverse portforward in order to run localhost on the Quest and debug using the Chrome debugger

As for non-technical things, I learned (and am still learning) not to assume what people know and to explain things as if they knew nothing (or at least very little). I think I have the tendency to overestimate how familier others are with my project or just assume they know more then they do in general.

## Self-Evaluation

I was really happy with how the project turned out, especially after doing the test study and seeing everything working as we had envisioned at the beginning of the semester. I was happy with the amount of time I was able to allocate to research and thought I was able to get a lot done. Like last semester, software development took up a majority of my research time (which I think is understandable given the goal of my project). I had originally hoped this wouldn't be the case but now that we have a system to work with, I think there will be much more opportunities to think about research ideas and run actual studies in the future.

I also did not do a good job with keeping up with status reports. I will make sure this is not the case over the summer.

As for advice, I would tell anyone who is building an application to think carefully about *how* something should be implemented as opposed to just getting it working. It is much more work to go back and fix lazy code then it is to implement it right the first time.
