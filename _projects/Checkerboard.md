---
title: "Checkerboard detector (CUDA)"
collection: projects
# type: ""
permalink: /projects/Checkerboard
# venue: "Iko"
# date: 2020-06-09
# location: "Singapore"

---


---

[Link to Code](https://github.com/srinath2468/CUDA-checkerboard-detector.git)

---

### Abstract

---

This checkerboard detector was created to work on the jetson TX2 that utilises CUDA. 


### Methodology

---

mxn = dimensions of checkerboard

a. We first run a corner detector using a hessian matrix which gives us our points of interest

b. These corners are then filtered to remove multiple corners detected around each pixel. This is because we are using a 3x3 kernel. Increasing this will remove the need for filtering

c. For each corner, we compare it to every other corner detected by constructing a line between them. For each comparison, we launch a thread on the gpu. 

d. We consolidate valid lines. These are lines that pass through more than (m-1) or (n-1) points

e. We extend these lines till they reach the end of the image

f. Duplicate lines are removed

g. The remaining lines are grouped by angle.

h. The pair is chosen that have mxn points and are ordered accordingly.



### Results

9x7 checkerboard

![Waypoints](/images/result_1.jpg)

9x6 checkerboard

![Waypoints](/images/result_2.jpg)

7x9 checkerboard

![Waypoints](/images/result_3.jpg)