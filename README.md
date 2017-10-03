# **Finding Lane Lines on the Road** 
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

<img src="examples/laneLines_thirdPass.jpg" width="480" alt="Combined Image" />

Overview
---

When we drive, we use our eyes to decide where to go.  The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle.  Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm.

In this project I detected lane lines in images using Python and OpenCV.  OpenCV means "Open-Source Computer Vision", which is a package that has many useful tools for analyzing images.  

The goals / steps of this project were the following:
* Make a pipeline that finds lane lines on the road
* Reflecting on my work in a written report

**1. The Pipeline:**
My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I used Canny Edge Detection method to trace out the edges by using pixels with higest gradient. I then implemeted Gaussian Smoothing followed by selecting my area of interest using a polygon. The next step was to trace out the segments of lines and interpolate them using Hough Transformation. Last part was the visulization part, in which I simply used a weighted function from OpenCV to combine the two images (lane lines and the original image)

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by calculating the average x and y coordinate values for all the lines with positive and negative slopes above a certain threshold (this threshold value was determined through trial and error!)

If you'd like to include images to show how the pipeline works, here is how to include an image: You can either use the command mpimg.imread(str) or cv2.imread(str) where str represents the image location and its name.


**2. Shortcomings:**
One potential shortcoming would be what would happen when the streets are very curvy and the videos are very fast (fps is too high, thereby causing problems in image capturing!). 


**3. Possible improvements:**
Through this project, I feel that a lot of algorithms that I wrote, might not be very good for very curvy roads and something additional needs to be included in my pipeline.



The Project - Set-up:
---

**If you have already installed the [CarND Term1 Starter Kit](https://github.com/udacity/CarND-Term1-Starter-Kit/blob/master/README.md) you should be good to go!   If not, you should install the starter kit to get started on this project.**

**Step 1:** Set up the [CarND Term1 Starter Kit](https://classroom.udacity.com/nanodegrees/nd013/parts/fbf77062-5703-404e-b60c-95b78b2f3f9e/modules/83ec35ee-1e02-48a5-bdb7-d244bd47c2dc/lessons/8c82408b-a217-4d09-b81d-1bda4c6380ef/concepts/4f1870e0-3849-43e4-b670-12e6f2d4b7a7) if you haven't already.

**Step 2:** Open the code in a Jupyter Notebook

You will complete the project code in a Jupyter notebook.  If you are unfamiliar with Jupyter Notebooks, check out <A HREF="https://www.packtpub.com/books/content/basics-jupyter-notebook-and-python" target="_blank">Cyrille Rossant's Basics of Jupyter Notebook and Python</A> to get started.

Jupyter is an Ipython notebook where we can run blocks of code and see results interactively.  All the code for this project is contained in a Jupyter notebook. To start Jupyter in your browser, use terminal to navigate to your project directory and then run the following command at the terminal prompt (be sure you've activated your Python 3 carnd-term1 environment as described in the [CarND Term1 Starter Kit](https://github.com/udacity/CarND-Term1-Starter-Kit/blob/master/README.md) installation instructions!):
```
jupyter notebook
```
A browser window will appear showing the contents of the current directory.  Click on the file called "P1.ipynb".  Another browser window will appear displaying the notebook.  Follow the instructions in the notebook to complete the project.
