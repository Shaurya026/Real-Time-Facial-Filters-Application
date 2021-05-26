# Real-Time-Facial-Filters-Application  
This project builds a `Gesture based facial filter application` where you can use your hand gesture to select any filter over your face like in many social media applications. this implementation applies deep learning for building a custom model for 15 and 68 points face detection as shown in [this directory](https://github.com/Shaurya026/Real-Time-Facial-Filters-Application/tree/main/Facial%20Landmark%20Detection). Since, 68 points provide better accuracy in placement of filters we will use 68 key points model built in this project. The facial points predicted are shown below:   
<p align="center">  
<img src="https://github.com/Shaurya026/Real-Time-Facial-Filters-Application/blob/main/Demo%20Files/face.png" width=30% height=30% alt="pts">  
</p>  

### The model used for Facial Keypoint detection helps in giving results as shown below:   
<p align="center"> 
<img src="https://github.com/Shaurya026/Real-Time-Facial-Filters-Application/blob/main/Demo%20Files/human%20landmarks.png" width=30% height=30% alt="normal"> <img src="https://github.com/Shaurya026/Real-Time-Facial-Filters-Application/blob/main/Demo%20Files/human.png" width=30% height=30% alt="face points">
</p>

Some Requirements for this project are libraries shown below:   
1. Tensorflow
2. OpenCV
3. Pillow
4. numpy  

\>> For getting the face crops we use `Haarcascade Classifier` for face extraction and croping the photo for inference on our custom model. The Haarcascade for face detection is provided in this repo for anyone's use. Else you may find it in OpenCV library installed on your system.  
\>> For Hand gesture we track any object we wish to use for changing the filter using the CSRT_TRACKER present in OpenCV. Where using a Crosshair can be used to select our tracker.  

### Below is the Working Presentaiton of the `Project V1.ipynb` with the steps of usage provided after that:   
<p align="center">  
<img src="https://github.com/Shaurya026/Real-Time-Facial-Filters-Application/blob/main/Demo%20Files/Working.gif" width=60% height=60% alt="working">  
</p>    

1. From the above video the Haarcascade detects the face present in the frame as soon as the program is executed.  
2. The user selects the key `s` from the keyboard to pause the frame and allow user to select the area which we want to track, in this case the hand presented. Once the hand is selected user presses `space bar` for the tracker to start working and track the coordiantes of mid point from the tracker.  
3. We can than see a white circle for gesture reference, where the user moves his hand or any other object being tracked to get replace filter over the face.   
      >The `UP` gesture places the **sunglasses** over the eyes.  
      >The `DOWN` gesture simply shows the output of Haarcascade detection.  
      >The `LEFT` gesture leads to **moustache** below the nose.  
      >The `RIGHT` gesture leads to **Straw Hat** above the head.  
4. Finally if we want to exit we use the `q` key.  

The number below shows the Frame Rate per Second and the coordinates where the tracker is currently at.  
The FPS is low due to the fact a lot of inferencing i.e., Face Landmark detection, Face Detection, and Object tracking is being done all at once.  
