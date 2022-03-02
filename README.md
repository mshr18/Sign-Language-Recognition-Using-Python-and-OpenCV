# Sign-Language-Recognition-Using-Python-and-OpenCV
we create a sign detector, which detects numbers from 1 to 10 that can very easily be extended to cover a vast multitude of other signs and hand gestures including the alphabets.
2. Training CNN First, we load the data using ImageDataGenerator of keras through which we can use the flow_from_directory function to load the train and test set data, and each of the names of the number folders will be the class names for the imgs loaded.
3. In training callbacks of Reduce LR on plateau and earlystopping is used, and both of them are dependent on the validation dataset loss.
After every epoch, the accuracy and loss are calculated using the validation dataset and if the validation loss is not decreasing, the LR of the model is reduced using the Reduce LR to prevent the model from overshooting the minima of loss and also we are using the earlystopping algorithm so that if the validation accuracy keeps on decreasing for some epochs then the training is stopped.
The example contains the callbacks used, also it contains the two different optimization algorithms used – SGD (stochastic gradient descent, that means the weights are updated at every training instance) and Adam (combination of Adagrad and RMSProp) is used.
We found for the model SGD seemed to give higher accuracies. As we can see while training we found 100% training accuracy and validation accuracy of about 81%
After compiling the model we fit the model on the train batches for 10 epochs (may vary according to the choice of parameters of the user), using the callbacks discussed above.
The word_dict is the dictionary containing label names for the various labels predicted.
