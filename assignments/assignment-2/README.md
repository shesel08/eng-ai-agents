# Image-to-Video Semantic Retrieval via Object Detection

## Detector Selection

For this assignment, Ultralytics yolo26n is used as detector. This is the latest evolution in the YOLO series of real-time object detectors that removes unnecessary complexity while delivering faster, lighter and more accessible deployment. Chose this model specially as it provides faster cpu inference compared to other YOLO models.

## Input video and retrieval corpus

Roboflow is used to process the youtube video on Toyota RAV4 review offline and to build an index of detected semantic context. In https://app.roboflow.com/ after creating an account, created a new project and chose the video to create dataset. Tried sampling the video with output of 1 frame every 1, 2, 5 and 10 secs. 1 sec created 2794 images, 2 secs created 1397, 5 secs created 559 and 10 secs created 280 images as output. Chose not to increase the time as the number of images reduces further and may not be sufficient to train the model. Decided to stay with 10 secs as it provided image samples close to what is present in the hugging face query images in step 3.

The folder car-object-detection has all the training, validation and test images along with their labels. assignment_2.ipynb file has the code to train the yolo 26 model and run it on the data query images from hugging face to predict their class labels. 

## Output format
The yolo model does not output the video id or frame id as metadata. Hence created a dataframe with information from training dataset and kept it aside. Later while predicting, combined the data into the parquet file.
The created parquet file is uploaded to hugging face repository and displayed the first 5 of the entries of the file as a using pandas dataframe head. 