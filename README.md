# Clothing Classification CNN using Fashion MNIST

## Project Description
This project builds and evaluates a Convolutional Neural Network (CNN) to automatically classify images of clothing. Using the Fashion MNIST dataset, the model categorizes apparel into 10 distinct classes, including T-shirts, trousers, pullovers, dresses, coats, sandals, shirts, sneakers, bags, and ankle boots. Developed with TensorFlow and Keras, the project covers the entire machine learning pipeline from data preprocessing to model training and visual evaluation.

## Key Features & Achievements
* **Data Preprocessing:** Successfully loaded the Fashion MNIST dataset, reshaped the images to a 28x28x1 format for convolutional processing, normalized pixel values to a [0, 1] scale, and applied one-hot encoding to the labels.
* **CNN Architecture:** Designed a Sequential deep learning model featuring two Conv2D and MaxPooling2D blocks, followed by a Flatten layer and Dense layers configured for 10-class softmax output.
* **Model Training & Accuracy:** Compiled the model using the Adam optimizer and categorical crossentropy loss, training it over 10 epochs with a batch size of 32 to achieve an impressive test accuracy of ~90.91%.
* **Prediction Visualization:** Integrated Matplotlib to visually evaluate the model on a test subset, displaying original images alongside their true and predicted labels using dynamic green/red color coding for accuracy verification.
