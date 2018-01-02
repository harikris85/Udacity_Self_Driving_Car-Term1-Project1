# **Finding Lane Lines on the Road** 

## Writeup

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I .... 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 

My Pipeline consists of the following steps.
1. Read in an image.
2. Convert to grayscale.
3. Do gaussian blur. This should help with noise reduction.
4. Do Canny edge detection on the blurred image.
5. Perform Hough_Lines on the canny edge detected image to find line segments.
6. Extrapolate the lines segments to full lanes.

For draw_lines function, I made the following changes.
1. Find out the slope and intercept of the line segments.
2. We can seperate out the 2 lanes based on the slope values, all positive for 1 lane and all negative for other.
3. Find the average of the slope and intercept.
4. Using the average slope, we can find out the top and botton point of both lanes.
   Since the y values are known for top and bottom points, x values will be (y - intercept)/slope


### 2. Identify potential shortcomings with your current pipeline

1. The above logic for draw_lines can still be improved, since at some video frames, my output was not very good.


### 3. Suggest possible improvements to your pipeline

1. As explained above draw_lines could still be further improveed. We could use some threshold for the slope and use only slope values which fall within this threshold. This should help improve the average value for slope.
2. I decided on the Hough parameters after lot of trial and error. There may be better values for these.
