# Sign-Language-Recognition-Using-Python-and-OpenCV
we create a sign detector, which detects numbers from 1 to 10 that can very easily be extended to cover a vast multitude of other signs and hand gestures including the alphabets.
1. Creating the dataset for sign language detection:
 In this project, we will be creating the dataset on our own.We will be having a live feed from the video cam and every frame that detects a hand in the ROI (region of interest) created will be saved in a directory (here gesture directory) that contains two folders train and test, each containing 10 folders containing images captured using the create_gesture_data.py
 Now for creating the dataset we get the live cam feed using OpenCV and create an ROI that is nothing but the part of the frame where we want to detect the hand in for the gestures.The red box is the ROI and this window is for getting the live cam feed from the webcam.
 For differentiating between the background we calculate the accumulated weighted avg for the background and then subtract this from the frames that contain some object in front of the background that can be distinguished as foreground.
This is done by calculating the accumulated_weight for some frames (here for 60 frames) we calculate the accumulated_avg for the background.
After we have the accumulated avg for the background, we subtract it from every frame that we read after 60 frames to find any object that covers the background.
Calculate threshold value
Now we calculate the threshold value for every frame and determine the contours using cv2.findContours and return the max contours (the most outermost contours for the object) using the function segment. Using the contours we are able to determine if there is any foreground object being detected in the ROI, in other words, if there is a hand in the ROI.
When contours are detected (or hand is present in the ROI), We start to save the image of the ROI in the train and test set respectively for the letter or number we are detecting it for.
