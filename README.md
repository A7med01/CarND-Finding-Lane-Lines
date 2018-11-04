# **Finding Lane Lines on the Road** 
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

<img src="test_images _output/solidYellowCurve.jpg" width="480" alt="Combined Image" />

Overview
---

When we drive, we use our eyes to decide where to go.  The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle.  Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm.

In this project I will detect lane lines in images using Python and OpenCV. 


### 1. pipeline

My pipeline consisted of 6 steps:

* Convert image to grayscale.
* Blur it with the chosen kernel to make the edges smoother. 
* Apply Canny edge detection to obtain edges.
* Set vertices of the region of interest and apply a selection mask to select the region of lane lines
* Applying Hough transform to the masked image to get a lines image
* Combine lines image with original image



In order to draw a single line on the left and right lanes, I modified the draw_lines() function as following :

All obtained hough lines is separated into two groups  left and right lanes according to their slope then we sum  all lines slopes and centers and  average them then using the average slope and average center we will draw the left and right lanes by calculating the top and bottom points of each line. 

Here's a [link to my video 1 result](./test_videos_output/solidWhiteRight.mp4)
Here's a [link to my video 1 result](./test_videos_output/solidYellowLeft.mp4)

### 2.  potential shortcomings 


One potential shortcoming is my pipeline don't work well with the Challenge video.


### 3.  possible improvements

A possible improvement is to modify the function so that it can do well with Challenge video.
