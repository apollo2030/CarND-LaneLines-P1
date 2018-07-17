# **Finding Lane Lines on the Road** 

**Finding Lane Lines on the Road**

The goals of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on the work done


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Pipeline description

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I used Gaussian blur to loose thin small edges then I apply canny edge detection then I use high transform to determine the line segments in the image. 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by removing the line segments that are outside the region of interest then I separate the line segments into two arrays based on the slope of the lines - left_lines and right_lines, then I get the average slope from each array and use it together with the average intercept to draw the lane line.  

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Shortcomings

One potential shortcoming would be what would happen when there are multiple lines in the area of interests, like cracks, road in repair, 
Another shortcoming could be that the turns are not usually describably by one line - ie the turns must be described by curbs.

### 3. Possible improvements 

A possible improvement would be to find a way to identify the area of interest - now it is hardcoded.

Another potential improvement could be to identify as well other lane lines so that the car has other drivable areas in the case of emergency maneouvers.

