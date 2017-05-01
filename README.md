# Lane Lines Detection

My pipeline consisted of the following steps :-
* Read the images
* Convert the images to grayscale

![alt text](https://github.com/advaitha/CarND-LaneLines-P1/blob/master/grayscale.png)

* Apply Gaussian filter on the images
* Detect the edges by selecting the appropriate threshold levels

![alt text](https://github.com/advaitha/CarND-LaneLines-P1/blob/master/edge.png)

* Select the region on which line lanes need to be drawn by selecting vertices

![alt text](https://github.com/advaitha/CarND-LaneLines-P1/blob/master/region.png)

* Apply Hough transformation (by selecting and tuning the parameter values) on the selected region and utilize it for drawing lines on the masked image

![alt text](https://github.com/advaitha/CarND-LaneLines-P1/blob/master/red_lines.png)

* Hough lines drawn on the original images are as follows :-

![alt text](https://github.com/advaitha/CarND-LaneLines-P1/blob/master/hough_lines.png)

##### In order to draw a single line on the left and right lane respectively the draw_lines function is modified as follows :-

The slope of all the lines are calculated. Based on their slope value the lines are divided into two categories. The average of x1,x2,y1,y2 values are calculated for both the groups. A Single line is drawn for both the groups based on the average value. Precaution is taken for avoiding the dividing by zero error which is possible. Finally these two lines were utilized for annotating the continuous lines on the video stream.

##### Potential Shortcomings with the current pipeline:-

* This pipeline will work if the images are very similar to each other and the lane lines are approximately at the same position in the image. If the lane lines are at a significantly different position from one image to another image this pipeline will not work

* The parameter values selected for all the images are the same for example the threshold values for canny edge detector. If the images are not similar the common values choosed for the pipeline will not work

##### Suggestions for possible improvements:-

* The draw_lines function modified consists of many lines of code which can further be reduced.
* The function written for process_image can be further modified, so that it can be utilized universally.
* Applying regression for more robust output of the solid lines.




 



 

























