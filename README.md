# OCR
Optical character recognition in ROS 

This is a code to detect digits from a video using ROS and OpenCV in python. The algorithm is split into two segments, training and creating a dataset, using the trained data set to obtain best match through K Nearest Neighbor algorithm (supervised learning).

K Nearest Neighbor:

The algorithm fundamentally works by computing the euclidean distance between the sampled data and the dataset. The lesser the euclidean distance, the closest is their match. Inorder to classify the data, an additional parameter called K is used. It is based on this value of K, the density of datapoints and the dominating family is identified to provide classification. <a href="https://en.wikipedia.org/wiki/K-nearest_neighbors_algorithm">In detail</a>. To achieve better results, use Support Vector Machine.

Training Method: 

I used to this <a href="http://stackoverflow.com/questions/9413216/simple-digit-recognition-ocr-in-opencv-python">link</a>
as a reference to my code. Also, remember to build huge dataset to help the KNN model to clasify without any ambiguity and to improve the results.

Step-1: Import the training image and identify its contours and regions.
<br/>Step-2: Convert the BGR image into grayscale and threshold. Use this image to find contours. Draw a rectangular bounding box for every contours.
<br/>Step-3: For every contours resize the region and get the input from the user. Record the region and the user response in ASCII format.
<br/>Step-4: Store the trained data in two txt files. This completes the training part. 

Implementation:

Step-1: Import the dataset and train the model.
<br/>Step-2: Stream Video and collect frames. 
<br/>Step-3: Convert the BGR image into grayscale and threshold. Find contours and for every contour extract x,y,w,h. 
<br/>Step-4: Separate every single region and feed it to the KNN model to find the closest possible match. Vary the value of K, to incorporate proper classification of data.
<br/>Step-5: Once classified the corresponding response is pulled from the saved txt file. The value is converted into string. 
<br/>Step-6: Show the image towards the camera and check whether the data that it is showing is right. Then press enter from the numpad. This stops the node and it starts to publish data to another node, by stitching the regions in nearby pixel. 

P.S: I'm new to machine learning, hence forgive me if you find any noob mistake. Feel free to criticise. This project is developed with support from Fulton Undergraduate Research Initiatives grant. Thanks to them !

