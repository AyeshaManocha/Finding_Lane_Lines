# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I applied gaussian blur on that image taking kernel_size=11. Further, I applied canny edge on the output returned after applying gaussian blur taking low_threshold=50 and high_threshold=150. Later, I defined vertices for my region of interest and passed edges and vertices to region_of_interest() to apply an image mask. I defined rho=2, threshold = 20,min_line_length = 40, max_line_gap = 20 and did Hough transform on edge detected image. Finally, I applied weighted_img() to draw the lines on the image.

While working on test videos, lane lines were not detected properly, so I modified kernel_size=5, min_line_length = 200, max_line_gap = 100 to form long lines.


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when there are curvy lines on the road. 

Another shortcoming could be intersecting lines in the end might cause problem.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to modify draw_line to find accurate slope.

Another potential improvement could be to fill in colour while detecting lane lines
