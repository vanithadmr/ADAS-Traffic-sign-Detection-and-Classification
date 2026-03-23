# ADAS Traffic Sign Detection & Classification

# Overview:  
Real-world Advanced Driver Assistance Systems (ADAS) and autonomous vehicles, traffic sign recognition. In this project, you will build this complete two-stage ADAS pipeline. Using the GTSRB (German Traffic Sign Recognition Benchmark)dataset containing over 50,000 images across 43 traffic sign classes, you will first build a Sign Detection & Cropping module that locates and isolates traffic signs from full road scene images. 

# Project Deliverables:  
      EDA
      Object Detection
      Classification
      
# EDA(Exploratory data analysis) :  
      Loading the data 
      Understanding the data 
      Handling null values 
      Handling the duplicates data 
      Heatmap for correlation between features 
      Plot bar chart for class distribution.
      Identified Classes imbalance 
      Displayed sample images 
      Observed some images are blur and varying backgrounds 
      Differentiate traffic signs like some signs are red and blue. Etc
      Shapes are different like triangular, rectangle, circle 


# Data Preprocessing: 

      Images are different sizes so that we have to resize same sizes	
      We converted (30 ,30)	pixels 
      Using ImageDataGenerator scale the data, splitting the data 
      Like Training and validation data. 
      Classmode is categorical and generates one-hot encoded for    multiclass classification. 


# Data Augmentation : 

      Applied augmentation only training data.
      Rotation 15 degrees
      Zooming 0.1,shift 0.1 
      Never applied horizontal and vertical flips 

# Detection Approach: 
      Here detection approach  is two types 
      
# Manual 
# Yolo 

# First approach(Manual) : 

      Using OpenCV color thresholding detection mechanism detection sign and return cropped image
      limitations :
      Its captured red sign only 
      Blues and yellow signs are not captured that’s why 
      We moved another detection approach  
      
# Second approach (YOLO): 

YOLO ("You Only Look Once") is a popular, high-speed real-time object detection framework using convolutional neural networks, allowing computers to identify objects in images and videos within a single pass 
Here we load the pretrained yolo model yolov8n.pt and trained the model using our custom dataset. 
Then our model learns the trends and patterns in the dataset 
Our model can create bounding boxes on  images. 
Finally crop the traffic sign from the input image.


# CNN Model Building: 

Here  we build the CNNs model for multiclass classification.
Three different types of  models are building, and we picked one best model from that 
Finally, we saved one best model for classification 

1>  convolution layer 
2>  pooling layer 
3>  generalization layer 
4>  Dense layer 
5> Dropout
6> Activation layers(ReLU and SoftMax) 

# Pretrained models: 

mobilenetv2, loaded the pretrained model and and added the  dense layer and final output layer  
Model cannot capture trends in the data 
Model performance is very poor in this dataset 
Then again loaded another type of pretrained model resnet50 
Added dense and final layer for output 
This model is also not performing well 
Very poor performance for this problem.

# Data frame: 

'Models' : ['CNNs_model1', 'CNNs_model2','CNNs_model2', 'MobileNETV2',   'ResNet50'],
    'Layers' : [10, 10, 13, 4, 4],
     'neurons' : [565, 299, 565,565, 565],
     'Val_Accuracy' : [0.96, 0.95, 0.95, 0.21, 0.266],
     'Train_Accuracy' : [0.98, 0.98, 0.98, 0.37, 0.38],
     'Val_Loss' : [0.08, 0.06, 0.05, 2.61, 2.62],
     'Train_Loss' : [0.17, 0.26, 0.17, 2.08, 2.02],


  



# Model Building:

Streamlit application : 
Build a Streamlit application for this project. Get the input from the user model is detected the sign and return the crop sign for CNN model 
The CNN model is going to perform well for identifying the sign.

