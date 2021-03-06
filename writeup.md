# **Finding Lane Lines on the Road** 

**Finding Lane Lines on the Road**

The goals of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on the work done


[//]: # (Image References)

[image1]: ./examples/hslsolidWhiteRight.jpg "HSV space"
[image2]: ./examples/graysolidWhiteRight.jpg "Grayscale"
[image3]: ./examples/blursolidWhiteRight.jpg "Gaussian blur"
[image4]: ./examples/cannysolidWhiteRight.jpg "Canny"
[image5]: ./examples/houghsolidWhiteRight.jpg "Hough"
[image6]: ./examples/roisolidWhiteRight.jpg "Roi"
[image7]: ./examples/finalsolidWhiteRight.jpg "Final"


---

### Pipeline description

My pipeline consisted of 5 steps. First, I converted the images to HSV color space to reduce the influence if luninosity change then converted the image to grayscale, then I used Gaussian blur to loose thin small edges then I apply canny edge detection then I use high transform to determine the line segments in the image. 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by removing the line segments that are outside the region of interest then I separate the line segments into two arrays based on the slope of the lines - left_lines are the ones with a negative slope and right_lines the ones with a positive slope. At first I thought that a slope can go up to infinite but considering that the cartesian space of an image is formed of integer numbers - the biggesst/smallest value of the slope can not be bigger/smaller than the height of the image. Then I get the average slope from each array and use it together with the average intercept to draw the lane lines.  

![alt text][image1]
![alt text][image2]
![alt text][image3]
![alt text][image4]
![alt text][image5]
![alt text][image6]
![alt text][image7]


### 2. Shortcomings

One potential shortcoming would be what would happen when there are multiple lines in the area of interests, like cracks, road in repair, 
Another shortcoming could be that the turns are not usually describably by one line - ie the turns must be described by curbs.

### 3. Possible improvements 

A possible improvement would be to find a way to identify the area of interest - now it is hardcoded.

Another potential improvement could be to identify as well other lane lines so that the car has other drivable areas in the case of emergency maneouvers.

