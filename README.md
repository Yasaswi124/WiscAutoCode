# WiscAutoCode (Wisconsin Autonomous Perception Coding Challenge)

## Submission Specification
This is my solution to the Wisconsin Autonomous Perception Coding Challenge. I used python and the following libraries to analyze the image:
- NumPy
- OpenCV
- Matplotlib
- sklearn (not yet implemented)




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
    - I detected the highest and lowest non zero pixel on both the left half and right half of the image.
    - I drew a line that connected the two detected pixels on each half of the image.
    
    
## In Progress/TO-DO:

- I used the object detection data to calculate the center location of each detected cone on the image, I can use this data to make a linear regression model that goes through the cones. This would make the lines more accurate, instead of only using data from the top and bottom cones.
- I can calculate the slope of the current line, or use the calculated slope of the linear regression model to extend the lines further.
    
