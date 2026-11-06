CNN Binary Image Classification – Cat and Dog Recognition

Project Overview

This project is a Convolutional Neural Network (CNN) based binary image classification system developed to identify whether an uploaded image contains a cat or a dog.

The project uses deep learning techniques to train a CNN model using a dataset of cat and dog images. The trained model is integrated into a Flask web application, allowing users to upload images through a web interface and receive classification results.

The application displays the uploaded image, the predicted class and the model's prediction confidence.

Project Objectives

1. Develop a CNN model for binary image classification.
2. Train the model using cat and dog image datasets.
3. Evaluate model performance using a separate test dataset.
4. Save the trained model for future use.
5. Develop a web application using Flask.
6. Allow users to upload images and receive predictions.
7. Display classification results and confidence scores.
8. Make the application accessible through a public URL using ngrok.

Technologies Used

Python 3.12
TensorFlow
Keras
NumPy
Flask
Pillow
Jupyter Notebook
Anaconda
Ngrok
HTML
CSS
Convolutional Neural Networks (CNN)

Project Structure

Pro2_CNN_binary_image_classification/

    app.py
    classifier.pkl
    templates/
        index.html
    static/
        style.css
    data/
        CATDOG/
    notebooks/
        cnn_binary_image.ipynb
    user/

Project Components

1. Dataset

The project uses a dataset containing images of cats and dogs.

The dataset is divided into training, validation and testing datasets to develop and evaluate the CNN model.

Images are resized to 100 × 100 pixels and processed before being passed into the neural network.

2. CNN Model Development

A Convolutional Neural Network is developed using TensorFlow and Keras.

The model learns visual features from the training images, including edges, shapes, textures and patterns that help distinguish between cats and dogs.

The final output layer uses a sigmoid activation function to perform binary classification.

The two output classes are:

Class 0: Cat
Class 1: Dog

3. Model Training

The model is trained using a training dataset and evaluated using a validation dataset.

The training process uses multiple epochs and includes an EarlyStopping callback to help prevent unnecessary training and reduce overfitting.

The model learns to recognise distinguishing visual features through the CNN architecture and adjusts its weights during training.

4. Model Evaluation and Performance

The trained CNN model was evaluated using a test dataset containing 2,000 images, with 1,000 images belonging to each class.

The classification report produced the following results:

                    Precision    Recall    F1-score    Support

Class 0 (Cat)          0.71       0.84       0.77       1000

Class 1 (Dog)          0.80       0.66       0.72       1000

Accuracy                          0.75                  2000

Macro Average          0.76       0.75       0.74       2000

Weighted Average       0.76       0.75       0.74       2000

Overall Test Accuracy: 75%

Performance Analysis

The CNN model achieved an overall accuracy of 75% on the test dataset.

For cat classification, the model achieved 71% precision and 84% recall, indicating that it correctly identified a high proportion of actual cat images.

For dog classification, the model achieved 80% precision and 66% recall. This indicates that dog predictions were relatively reliable, although the model missed some actual dog images.

The macro-average F1-score was 0.74, demonstrating a reasonably balanced classification performance across both categories.

These results show that the CNN successfully learned visual features for distinguishing cats from dogs, while also providing opportunities for further optimisation.

5. Model Saving

After training, the model is saved as classifier.pkl using Python Pickle.

This allows the trained model to be loaded into the Flask application without retraining the CNN every time the application starts.

6. Flask Web Application

A Flask application is developed to provide a user-friendly interface for interacting with the trained CNN model.

Users can upload JPG, JPEG or PNG images through the website.

The application processes uploaded images by:

- Resizing images to 100 × 100 pixels.
- Converting images into RGB format.
- Converting images into numerical arrays.
- Normalising pixel values.
- Passing the processed images to the trained CNN model.
- Generating a prediction and confidence score.

The application displays:

- The uploaded image.
- The predicted class (CAT or DOG).
- The prediction confidence.
- A NOT RECOGNISED message when the prediction confidence falls below the configured threshold.

7. Frontend Development

The frontend is developed using HTML and CSS.

The HTML template provides the image upload form and displays prediction results.

The CSS stylesheet provides the visual layout, colours, typography and styling of the web application.

8. Public Access Using Ngrok

Ngrok is used to expose the locally running Flask application to the internet.

This allows users to access the application through a public URL without deploying it to a dedicated cloud server.

The public URL is generated when the ngrok tunnel starts.

How to Run the Project

1. Clone the repository

git clone YOUR_GITHUB_REPOSITORY_URL

2. Navigate to the project directory

cd Pro2_CNN_binary_image_classification

3. Create and activate the Conda environment

conda create -n cnn-env python=3.12

conda activate cnn-env

4. Install the required libraries

pip install tensorflow numpy flask pillow pyngrok jupyter

5. Open Jupyter Notebook

jupyter notebook

Open the notebook located at:

notebooks/cnn_binary_image.ipynb

The notebook contains the CNN model development, training and evaluation process.

6. Run the Flask application

python app.py

7. Access the application

Once Flask and ngrok are running, open the public URL displayed in the terminal or notebook.

Upload a cat or dog image to test the classifier.

Model Information

Model Type: Convolutional Neural Network (CNN)

Task: Binary Image Classification

Input Image Size: 100 × 100 pixels

Input Channels: 3 (RGB)

Output Layer: Sigmoid Activation

Output Classes: Cat and Dog

Model File: classifier.pkl

Test Dataset Size: 2,000 Images

Test Accuracy: 75%

Limitations

The model is trained specifically to distinguish between cats and dogs.

The current application uses a confidence threshold to display NOT RECOGNISED when prediction confidence is below a configured value.

However, a binary classification model can still confidently classify unrelated images as either cats or dogs. Therefore, the confidence threshold does not guarantee reliable detection of images outside the trained categories.

Future Improvements

1. Improve classification accuracy through additional training and hyperparameter optimisation.
2. Increase the size and diversity of the training dataset.
3. Experiment with deeper CNN architectures.
4. Implement data augmentation to improve model generalisation.
5. Improve the detection of images outside the trained categories.
6. Experiment with transfer learning using pretrained models such as MobileNetV2 or VGG16.
7. Improve the frontend design and user experience.
8. Deploy the application to a cloud hosting platform for continuous availability.

Author

Developed as a deep learning and web application project using Python, TensorFlow, Keras and Flask.

License

This project is available for educational and research purposes. Please check the original dataset licensing terms before redistributing the dataset or its images.