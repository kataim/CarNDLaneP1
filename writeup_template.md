# **Finding Lane Lines on the Road** 

## Introduction
The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"
[image2]: ./test_image_outputs/solidWhiteCurve.jpg
[image3]: ./test_image_outputs/solidWhiteRight.jpg
[image4]: ./test_image_outputs/solidYellowCurve.jpg
[image5]: ./test_image_outputs/solidYellowCurve2.jpg
[image6]: ./test_image_outputs/solidYellowLeft.jpg
[image7]: ./test_image_outputs/whiteCarLaneSwitch.jpg

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of the following steps. 
* Read the image/video from the folder
* Convert the image to grayscale using the open CV function cvtColor
* Apply a gaussian blur to filter out noise on the image (this is also handled by the canny transform)
* Apply the canny transform for edge detection on the image
* Create a four sided polygon that will contain our area of interest
* Finally apply a hough transform to identify the lane lines. This is done by setting a threshold on the parameters to decide what
  constitutes a line.
  
The result of these steps are shown below:
## Solid White Curve
![alt text][image2]

## Solid White Right
![alt text][image3]

## Solid Yellow Curve
![alt text][image4]

## Solid Yellow Curve2
![alt text][image5]

## Solid Yellow Left
![alt text][image6]

## Solid White Car Lane Switch
![alt text][image7]


In order to draw a single line on the left and right lanes, I modified the draw_lines() function by:
* First identify the gradient of the line to know the left and right lanes
* Remove the horizontal lines
* Get the average gradient of the lines
* Get the average of the lines and use them to find the top and bottom lines for extrapolation
* Call open CV line() function to draw the line.



### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when another vehicle enters the region of interest the pipeline might detect this as a line. Another potential shortcomming is if we enter a box junction our pipeline would probably fall over and not accurately detect the lanes and discard the box junction.

The extrapolation of the lane lines to make a continuous also proved to not be optimal. The lines were jittery escpecially when approaching a curve.



### 3. Suggest possible improvements to your pipeline

An improvement to the current pipeline would be to introduce curves and not just straight lines. 

Another potential improvement could be to be able to follow lane lines without markers. Some roads might not have any lane markings but our algorithm should be able to follow the road
