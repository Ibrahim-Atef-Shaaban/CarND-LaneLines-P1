# **Finding Lane Lines on the Road** 


**Finding Lane Lines on the Road

**The goals / steps of this project are the following:

* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report



**My pipeline consists of the following X steps:

1.The Image is converted into grayscale.

2.Gaussian blur and canny edge detection are applied to the Gray 1 channel image

3.A region of interest is extracted from the computed gradient, this region of interest is an upside down "V" shaped region, with a line thickness, and it is showed as follows:
#A shappe of 6 edges, where sides are drawn as "*"
**--------------2------------------**
**--------------*------------------**
**------------*---*----------------**
**----------*---*---*--------------**
**--------*---*-5-*---*------------**
**------*---*------*----*----------**
**---1******6-------4******3-------**
    
4.A hough transformation is applied to the lane lines in the focus region, then the lines are specified and the lane lines are drawn using the draw_lines() function

5.Finally, the drawn redlines are drawn over the original image

**In order to draw a single line for each of the right and left lanes, the draw_lines() function was implemented as follows:

First the function iterates over all lines, lines with zero slope, almost horizontal or vertical lines are neglected, other lines with negative slope are stored for left lane lines, and lines with positive slope are stored for right lane lines.
The values stored of the lines are the **(x1, y1, x2, y2)** coordinates of the line, along side with its slope.

Second, checks if the coordinate list has data, and if so a mean intercept and slope are calculated for the side lines, then using the average slope and intercept, an average line equation is generated and used to draw one lane line in the set boundries mentioned earlier.

Finally the lines of the left and right lanes are set and returned to be drawn over the main image.


**Shortcomings:**

The shortcoming of my pipe line is that with the optional challenge, there are some flickers on the left lane line, this is because the detection is a linear straight line and this might need to change a curved line

**Possible improvements to your pipeline

A possible improvement would be to color fill the whole space between the two lane lines for a better simulation and control later on.

