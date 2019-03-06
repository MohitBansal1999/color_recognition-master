# color_recognition-master

This project focuses on color classifying by K-Nearest Neighbors Machine Learning Classifier which is trained by R, G, B Color Histogram. It can classify Red, Green, Orange and Yellow. If you want to classify more color or improve the accuracy you should work on the training data or consider about other color features such as Color Moments or Color Correlogram.
You can use color_recognition_api to perform real-time color recognition in your projects. You can find a sample usage of color_recognition_api in this repo.

# Quick Demo
Run color_classification_webcam.py to perform real-time color recognition on a webcam stream.

# What does this program do?

Feature Extraction: Perform feature extraction for getting the R, G, B Color Histogram values of training images
Training K-Nearest Neighbors Classifier: Train KNN classifier by R, G, B Color Histogram values
Classifying by Trained KNN: Read Web Cam frame by frame, perform feature extraction on each frame and then classify the mean color of it by trained KNN classifier.

# Theory
In this study, colors are classified by using K-Neares Neşghbor Machine Learning classifier algorithm. This classifier is trained by image R, G, B Color Histogram values. The general work flow is given at the below.

You should know 2 main pheomena to understand basic Object Detection/Recognition Systems of Computer Vision and Machine Learning.

1.) Feature Extraction

How to represent the interesting points we found to compare them with other interesting points (features) in the image.

2.) Classification

An algorithm that implements classification, especially in a concrete implementation, is known as a classifier. The term "classifier" sometimes also refers to the mathematical function, implemented by a classification algorithm, that maps input data to a category.

# For this project;

1.) Feature Extraction = Color Histogram

Color Histogram is a representation of the distribution of colors in an image. For digital images, a color histogram represents the number of pixels that have colors in each of a fixed list of color ranges, that span the image's color space, the set of all possible colors.



2.) Classification = K-Nearest Neighbors Algorithm

K nearest neighbors is a simple algorithm that stores all available cases and classifies new cases based on a similarity measure (e.g., distance functions). KNN has been used in statistical estimation and pattern recognition already in the beginning of 1970’s as a non-parametric technique.



# Implementation
OpenCV was used for color histogram calculations and knn classifier. NumPy was used for matrix/n-dimensional array calculations. The program was developed on Python at Linux environment.


color_classification_webcam.py: test class to perform real-time color recognition form webcam stream.

In the “color_recognition_api” folder, there are 2 Python classes which are:

feature_extraction.py: feature extraction operation class

knn_classifier.py: knn classification class

1.) Explanation of “feature_extraction.py"

I can get the RGB color histogram of images by this Python class. For example, plot of RGB color histogram for one of the red images is given at the below.



I decided to use bin number of histogram which has the peak value of pixel count for R, G and B as feature so I can get the dominant R, G and B values to create feature vectors for training. For example, the dominant R, G and B values of the red image which is given at above is [254, 0, 2].

I get the dominant R, G, B values by using Color Histogram for each training image then I labelled them because KNN classifier is a supervised learner and I deploy these feature vectors in the csv file. Thus, I create my training feature vector dataset. It can be found in the file which name’s is training.data .

2.) Explanation of “knn_classifier.py”

This class provides these main calculations;

Fetching training data
Fetching test image features
Calculating euclidean distance
Getting k nearest neighbors
Prediction of color
Returning the prediction is true or false
“color_classification_webcam.py” is the main class of my program, it provides;

Calling feature_extraction.py to create training data by feature extraction
Calling knn_classifier.py for classification
You can find training data in here.

You can find features are got from training data in here.

# Conclusion
I think, the training data has a huge important in classification accuracy. I created my training data carefully but maybe the accuracy can be higher with more suitable training data.
