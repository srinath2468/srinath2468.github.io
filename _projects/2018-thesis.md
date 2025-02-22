---
title: "Accuracy comparison of 2d- 3d point correspondences"
collection: projects
type: "Master's Thesis"
permalink: /projects/2018-thesis
venue: "Nanyang Technological University"
date: 2018-06-09
location: "Singapore"

---


---

[Link to Code](https://github.com/srinath2468/Pose-estimation-comparison.git)

---

### Abstract

---

Pose estimation is one of the most basic steps when interfacing a camera with respect to the world. It has seen an increase in usage with the development of autonomy across various fields, mainly robotics. This thesis proposes to compare the various 2d-3d point correspondence methods for pose estimation available to us using three different conditions: distance from camera, resolution and pattern used. There is no documentation available today that describes which pattern, distance and algorithm configuration gives us the best results possible.

 After getting various correspondences, a hand-eye calibration will be performed and then later used for testing which correspondence environment produces the most accurate results. Accuracy would be the metric used to calculate the results produced from the correspondence algorithms.
### Methodology

---
10 waypoints were chosen for calibration such that they spanned toward the extreme points of the camera’s view.

![Waypoints](/images/RobotPoses.PNG)

**Position of Camera**

Two fixed positions of the camera were taken into consideration.

- 100cm from the base of the robot
- 150cm from the base of the robot
The minimum distance for the camera to produce a good and stable point cloud was calculated to be 1m, thus these distances were taken accordingly.
The camera was placed on a tripod with an angle of 30 deg.


![Experiment Setup](/images/experimentSetup.PNG )


**Method Workflow**

![Method](https://srinath2468.github.io/images/method.PNG)


### Results

In this dissertation, different Point correspondence methods were compared by testing them under various conditions and with different markers. It was noticed that for certain conditions, certain algorithms and markers worked well. The checkerboard marker works the best when the distance is comparable(50-120cm) from the robot. If the distance increases, we notice that the camera is not able to identify the checkerboard squares. The ellipses produce the least accuracy while calibrating. This might be due to the fact that the orientation of the ellipse was misaligned to the board. Therefore, it is essential that the orientation of the Ellipse marker always aligns with the board without any deviation. This might produce better results if tested in the future.

The Aruco marker was able to be detected at both the locations and produced considerable accuracy at both. For easy and fast implementation, Aruco marker can be prescribed while using the respective algorithm at the desired resolution. 

The resolution played a role in accuracy. With increase in resolution we could notice a decrease in accuracy of the calibration. This might be due to the fact that the algorithm had to search through more points when detecting the markers. The position of the camera has an inverse relation with the accuracy of calibration. As we moved the camera away, we could see a decrease in accuracy of both Aruco and Ellipse marker setups. There was no clear winner while using the algorithms as each algorithm produced good results under different conditions. It was henceforth proved that we need not only rely on the Iterative algorithmthat the solvepnp function uses by default and we can use the information given above to choose our algorithm and marker according to the needs of our objective.