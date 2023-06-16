# ECE148 Group 15 Spring 2023
## Team Members

![](https://github.com/UCSD-ECEMAE-148/spring-2023-final-project-team-15/blob/main/148%20Pics/TeamPic148)


Max Gibson (E.E.), Artyom Muradyam (C.E.), Sukhraj Sekhon (M.E.), Gustav Blankenberg (M.E.)

![Our Car](https://github.com/UCSD-ECEMAE-148/spring-2023-final-project-team-15/blob/main/148%20Pics/IMG-4828.jpg)

## Team 15 Project Overview
### Goals
Main Objective: The main objective of this project was to have the autonomous car be able to track Aruco markers and be able to orient and navigate itself into a parking spot using the aruco markers.

Different Aruco markers were used to identify whether a marker was a waypoint or a parking spot.

Reach Objective: By expanding the library of detectable markers, the reach goal was to implement different aruco markers (ID numbers 2, 3, 4, etc.) to indicate to the vehicle to parallel park or reverse park. The end goal was to implement LiDAR and different aruco markers to create a fully autonomous parking robot that could park in any space with live collision detection.

### Implementation
Node Diagram:
![](https://github.com/UCSD-ECEMAE-148/spring-2023-final-project-team-15/blob/main/148%20Pics/workFlow148.png)

Aruco Tracking Code: OpenCV libraries for Aruco detection were used with the OAK-D camera to get the position and orientation of any marker with respect to the camera. Impressively, the camera (when well calibrated) could detect markers at a very shallow angle. 

Prioritization Code: After receiving a matrix with every recognized Aruco marker and their corresponding coordinates in an array (in the format (ID, X, Y, Z, ROT_X, ROT_Y, ROT_Z), the prioritization code parses the data to find a park or waypoint ID (prioritizing a park ID). The single aruco marker and its global coordinates are then sent out to govern vehicle motion.

PyVesc: Through the use of supplied PyVesc functionality, we were able to control our robot and feed it the Aruco Tracking / Prioritization Code which took us to our final goal of navigation and movement guided by supplied aruco markers. 

## Video Demonstrations:

[MAE 148 Team 15 Final Project Demo Video #1 - YouTube](https://www.youtube.com/watch?v=G50PBTAHEMw)

[MAE 148 Team 15 Final Project Demo Video #2 - YouTube](https://www.youtube.com/watch?v=zTW6V7eFzfQ)
 
[MAE 148 Team 15 Final Project Demo Video #3 - YouTube](https://www.youtube.com/watch?v=NJUQtnQEkZM)

## CAD Designs and Progressions
![Camer Mount 1](https://github.com/UCSD-ECEMAE-148/spring-2023-final-project-team-15/blob/main/148%20Pics/CamMount1.png)

![Camer Mount 2](https://github.com/UCSD-ECEMAE-148/spring-2023-final-project-team-15/blob/main/148%20Pics/CamMount2.png)

Our camera mount changed shape over the course of this project. We found that the rotating axis it was on was unstable and created inconsistencies within the data we were recording. On top of that the LIDAR was initially intended to be embedded below the camera as you see on the left, we learned that in order to use the LIDAR consistently we needed to put it as a high point which reduced noise.

## Github
This github contains a lot of different versions of files that both were and were not used in this project. We put in a lot of hours towards ideas or potential solutions that did not end up being things we finalized. This is expected with lengthy projects and bigger goals.
These files show the different iterations and versions we used to control our robot. Our initial goal was to use ROS2, with OAK-D Lite and LIDAR, but we decided to just use the Aruco detection and control the robot using PyVesc without ROS. The final file we used to get results is called Aruco_VESC_Final.pys

## Problems, Solutions, and Improvements

We originally intended to use movebase in order to generate a parking garage map and general navigation. We saw many difficulties with this throughout our work eventually causing us to not use ROS completely. Pyvesc ended up being the final solution we were satisfied with as it allowed a much easier use of the car.
Aruco tracking became unreliable as we attempted to use it in more and more realistic tests. The tracking was seen as stable when testing stationary or slightly moving objects, we found that the anomalies became too frequent as the car continued to move more. The Z-axis marker would randomly flip, some frames wouldn’t track at all. Due to the time constraints of this course we continued to use it, but if given more time we would probably have chosen to test other options.
Improvements made around the end of the course were very positive. We saw the car following the aruco markers well, and figuring out parking. In the end we did not reach our goals but believe with more time we could have.

## Project Proposal and Updates

[Project Proposal](https://docs.google.com/presentation/d/1SPdlXPeaII4OW4W1v2NUxgKgfb3k1HtfPm9ghgGeCbw/edit#slide=id.p)

[Week 9 Update](https://docs.google.com/presentation/d/1lvGwgzwrjG8htye6AT5abwq07Il-wbPSKSPVuAF7KgQ/edit#slide=id.p)

[Week 10 Update](https://docs.google.com/presentation/d/1FMcyuLqXJCHcQL7g1cQ_9VNxa2cS5Ztn7FdCI7k7CQ0/edit#slide=id.p)

[Final Presentation](https://docs.google.com/presentation/d/1nlVrjX4GuRy3t5_0HDabZ8MohPu2Y59aFtOgHU6wwj0/edit#slide=id.p)


