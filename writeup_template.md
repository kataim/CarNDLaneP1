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






In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
