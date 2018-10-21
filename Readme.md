# Task :- Boundary Detection on Unseen Data

### I use OpenCV for this task . But Why? I can also use something like object detection

### models like YOLO,SSD etc. for this task. The reason is :

- Dataset is not provided for this task. So there must be some reason for that. Reasons can be :
    - We have to find dataset for this task from somewhere.
    - We have to make our own dataset.
    - We have to approach to find the solution for this task from some other method that can be possible to be done in the given time-frame.


### 3rd Reason seems to be best for me to try this task. So I go for OpenCV for this task.



## I am using OpenCV Version : 3.4.3 


### I have borrowed the images of college IdCard from my friend as my phone camera is not working properly right now.



## There are 2 files :

- ExplainOneImage.ipynb -> This file contains all the detailed information how i have done the task with detailed description.

- BulkImages.py -> This python file contains the code for performing the task on all images inside the folder.


## To run the code :

### Make 2 folders inside the current directory -> 

1. images -> Put all your images inside this folder. 

2. images-result -> Resultant images will be stored inside this folder.

### To run the code use python2 
### packages that must be installed on python2 virtual enviornment :
- numpy
- PIL
- OpenCV Version: 3.4.3


# Steps that I have done in this tasks

### First Step Converting image into grayscale image 


### Second Step to Blurr the image . Why? Reasons:
- Simply to reduce the noise
#### We can also use medianfilter here infact median filter has advantages over gaussian filter:
- it removes noise while keeping edges relatively sharp.
#### But let it keep simple and I use gaussian blur filter here


### Third Step is to use Thresholding :
#### Adaptive Thresholding is used why??
 - It performs good in all the conditions where image has different lighting conditions in different areas.
 
 
### Fourth Step is to use Erode and Dilation
#### For more details on this read on docs :- https://docs.opencv.org/2.4/doc/tutorials/imgproc/erosion_dilatation/erosion_dilatation.html

#### In Simple Terms :
#### Erode - It makes the object in white smaller.
#### Dilate - It makes the object in white bigger.


### Fifth Step (Final Step) - It Contains series of Steps

#### 1. Find the Contours from the threshold image . Important thing to note here is :

- cv2.RETR_EXTERNAL => If we use this flag, it returns only extreme outer flags. All child contours are left behind. 
- cv2.CHAIN_APPROX_SIMPLE => It will only give us the endPoints.It will compresses horizontal, vertical, and diagonal segments and leaves only their end points.

#### 2. Getting the points of contour which is having the maximum contour area.
#### 3. We will draw the rectangle based on the contours we have find out on an image.


# ThankYou
