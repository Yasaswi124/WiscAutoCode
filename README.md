# WiscAutoCode (Wisconsin Autonomous Perception Coding Challenge)

## Submission Specification
This is my solution to the Wisconsin Autonomous Perception Coding Challenge. I used python and the following libraries to analyze the image:
- NumPy
- OpenCV
- Matplotlib
- sklearn




Original Image            |   answer.png produced
:-------------------------:|:-------------------------:
<img src = "https://github.com/WisconsinAutonomous/CodingChallenges/blob/master/perception/red.png" width = "460" height = "560">   |  <img src = "https://github.com/Yasaswi124/WiscAutoCode/blob/main/images/answer.png" width = "460" height = "560"> 


## Methodolgy

I broke down my approach into 3 main steps: 

1) Filter the image to detect the cones:
    - I did this by selecting a specific range of rgb values that matched the color of the cones, and applied a filter to look for any pixels that matched the color.
    - I then converted this image to grayscale in order to make computation more efficient later.
    
2) To use object detection to select the cones and get rid of background noise:
    - I used the built in object detection algorithm in OpenCV to detect only the cones in the image.
    - I created a new image and selected only the objects that had a relatively large area. (gets rid of random objects detected in the background)
    
3) Drew a line that went through each column of cones:
    - I used the object detection data to calculate the center location of each detected cone on the image. 
    - I used this data to make a linear regression model that goes through the cones. 
    - I calculated the top and bottom coordinates of the lines and used OpenCV to plot the lines on the image.
    
 
    
