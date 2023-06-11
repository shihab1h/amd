# Leaf Image Classification with Automatic Model Selection using Keras Tuner
Project for the Algorithms for Massive Data course. Implements a Convolutional Neural Network to classify 11 types of plant leaves on Tensorflow / Keras. 

Caching and Prefetching with AUTOTUNE are applied on the Tensorflow datasets to speed up the training process. For further explanation, study this [link](https://www.tensorflow.org/guide/data_performance). 

Dataset: https://www.kaggle.com/datasets/csafrit2/plant-leaves-for-image-classification

**Automatic Model Selection:**
* Requires the Keras Tuner package
* Identifies an optimal combination of hyperparameters
* The function make_model() is passed to the tuner object and the optimal selection is based on the validation accuracy

**Technical Notes regarding Dataset Processing:**
* Requires connection to Google Drive
* If opting to download the original data (~8 GB) and perform preprocessing (download, unzip, resize) from scratch, Kaggle credentials are to be uploaded by user as a JSON
* Processing images from scratch takes about 20 mins on a free Colab instance (June 2023)
* A preprocessed dataset ZIP file can be uploaded to Drive (in the root directory) to avoid the timely processing of the images everytime
