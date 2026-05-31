Crowd Density Image Classification with CNN

Project Description

A CNN-based model is used in this project for classifying crowd density images in low, medium, and high categories based on the provided data set. The CNN architecture is implemented with TensorFlow & Keras, and the model evaluation was performed using accuracy graphs and confusion matrices.



Data Set Organization

The folder structure of the dataset would look something like this:



dataset/

class_1/

img1.jpg

img2.jpg

class_2/

img3.jpg

img4.jpg

class_3/

img5.jpg



Example:



low/

medium/

high/



Technologies used

Python

TensorFlow/Keras

NumPy

Matplotlib

Pandas

Architecture of the Model

The CNN architecture consists of:



Input shape 64x64x3

Conv2D(32 filters) + MaxPooling

Conv2D(64 filters) + MaxPooling

Conv2D(128 filters) + MaxPooling

Flatten

Dense Layer with 128 neurons (ReLU activation)

Dropout with 0.3

Output with Softmax classification



Data Preprocessing

Images are resized to 64x64 pixels

Images are normalized (divided by 255.0)

Image data augmentation includes:

-rotation of the images,

- zoom-in and zoom-out, horizontal flipping,

- width and height shifting of the images.



Model Training

Adam optimization method is applied

Loss function: categorical cross-entropy

Batch size is 32

Number of epochs: 10-20

Validation split: 20%



Model Evaluation Measures

Accuracy

Loss

Confusion Matrix

Classification Report



Training Performance Visualization

Training accuracy vs validation accuracy graph

Training loss vs validation loss graph

Heat map of the confusion matrix



Outputs of the Trained Model

Trained model (.h5 file) - outputs/cnn_model.h5

training history - outputs/training_history.csv

class mapping - outputs/class_mapping.csv

model summary - outputs/model_summary.txt

figure 1 - outputs/figure_1.png

figure 2 - outputs/figure_2.png



Example prediction

With the following script, new images can be predicted with the trained model:



from tensorflow.keras.preprocessing import image

import numpy as np



img = image.load_img("test.jpg", target_size=(64,64))

img = image.img_to_array(img)/255.0

img = np.expand_dims(img, axis=0)



prediction = model.predict(img)

print("Predicted Class:", class_names[np.argmax(prediction)])



Features of the model

Deep learning model implemented with CNN.

Improved accuracy with data augmentation.

Using early stopping and saving the best models.

Evaluation using confusion matrix analysis.

Saving the trained model for future predictions.

Performance visualization during the training process.



Future Enhancements

Use Transfer learning with VGG16 and Resnet50 models

Increase the size of the data set

Integration with streamlit or flask server.

Improvement of accuracy using hyperparameter tuning.



Author

This is a machine learning assignment using CNN.



Conclusion

In this project, an image classification task of estimating crowd density is solved using CNN deep
