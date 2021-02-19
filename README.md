This python package contains modules to help with finding in an image.

Given an image that contains a table… the code is able to identify the tables correctly.

Steps:

Creating Dataset:
1. Tensorflow Object Detection API uses the TFRecord file format, so at the end we need to convert our dataset to this file format.
2. We need to write our own script to generate the TFRecords.
3. To prepare the input file for the API you need to consider two things. Firstly, we need an RGB image which is encoded as jpeg or png and secondly we need a list of bounding boxes (xmin, ymin, xmax, ymax) for the image and the class of the object in the bounding box. 
4. A script that converted the XML files to a csv and then to create the TFRecords.
5. For image processing on the command line like converting multiple images to different file formats, ImageMagick is used.

Training the model:
1. We used ssd_mobilenet_v1_pets.config as basis. Adjusted the num_classes to one, batch side to 8 and also set the path (PATH_TO_BE_CONFIGURED) for the model checkpoint, the train and test data files as well as the label map. In terms of other configurations like the learning rate, we used their default settings.
2. It is also recommended during the training to start the evaluation job. We can then monitor the process of the training and evaluation jobs by running Tensorboard.

All the files are in repository.


Note:
1. Due to lack of resources model hasen't been trained for more than 1800 steps (out of expected 8000). From the various resources we conclude that model has to trained
for at least 4000 steps
2. Other zip file contains code for OCR, but that code isn't connected to the bounding box identification code
