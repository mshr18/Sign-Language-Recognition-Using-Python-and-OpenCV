# Sign-Language-Recognition-Using-Python-and-OpenCV
we create a sign detector, which detects numbers from 1 to 10 that can very easily be extended to cover a vast multitude of other signs and hand gestures including the alphabets.
2. Training CNN First, we load the data using ImageDataGenerator of keras through which we can use the flow_from_directory function to load the train and test set data, and each of the names of the number folders will be the class names for the imgs loaded.
3. In training callbacks of Reduce LR on plateau and earlystopping is used, and both of them are dependent on the validation dataset loss.
After every epoch, the accuracy and loss are calculated using the validation dataset and if the validation loss is not decreasing, the LR of the model is reduced using the Reduce LR to prevent the model from overshooting the minima of loss and also we are using the earlystopping algorithm so that if the validation accuracy keeps on decreasing for some epochs then the training is stopped.
The example contains the callbacks used, also it contains the two different optimization algorithms used – SGD (stochastic gradient descent, that means the weights are updated at every training instance) and Adam (combination of Adagrad and RMSProp) is used.
We found for the model SGD seemed to give higher accuracies. As we can see while training we found 100% training accuracy and validation accuracy of about 81%
After compiling the model we fit the model on the train batches for 10 epochs (may vary according to the choice of parameters of the user), using the callbacks discussed above.
The word_dict is the dictionary containing label names for the various labels predicted.
3. Predict the gesture
In this, we create a bounding box for detecting the ROI and calculate the accumulated_avg as we did in creating the dataset. This is done for identifying any foreground object.
Now we find the max contour and if contour is detected that means a hand is detected so the threshold of the ROI is treated as a test image.
We load the previously saved model using keras.models.load_model and feed the threshold image of the ROI consisting of the hand as an input to the model for prediction.
Getting the necessary imports for model_for_gesture.py
Now we load the model that we had created earlier and set some of the variables that we need, i.e, initializing the background variable, and setting the dimensions of the ROI. getting the max contours and the thresholded image of the hand detected.
Summary
We have successfully developed sign language detection project. This is an interesting machine learning python project to gain expertise. This can be further extended for detecting the English alphabets.
