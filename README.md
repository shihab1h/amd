# Leaf Image Classification with Automatic Model Selection using Keras Tuner
Project for the Algorithms for Massive Data course. Implements a Convolutional Neural Network to classify 11 types of plant leaves on Tensorflow / Keras. 

Caching and Prefetching with AUTOTUNE are applied on the Tensorflow datasets to speed up the training process. For further explanation, study this [link](https://www.tensorflow.org/guide/data_performance). 

Dataset: https://www.kaggle.com/datasets/csafrit2/plant-leaves-for-image-classification

**Automatic Model Selection:**
* Requires the Keras Tuner package (pip command is inside the nb)
* Identifies an optimal combination of hyperparameters
* The function ==make_model()== is passed to the tuner object and the optimal selection is based on the validation accuracy

**Technical Notes regarding Dataset Processing:**
* Requires connection to Google Drive in case of using the preprocessed dataset (setting DATASET_FROM_SCRATCH = False) or wanting to save trained model to Drive (seeting SAVE_TO_DRIVE = True)
* If opting to download the original data (~8 GB) and perform preprocessing (download, unzip, resize) from scratch, Kaggle credentials are to be uploaded by user as a JSON
* Processing images from scratch takes about 20 mins on a free Colab instance (June 2023)
* A preprocessed dataset ZIP file can be uploaded to Drive (in the root directory) to avoid the timely processing of the images everytime

**Details on Use:**
* The zipped model in this folder is the one obtained by running the Leaf_..._USE_ORIGINAL_DATASET.ipynb notebook on 11 June 2023
* If saving time is important to you, set DATASET_FROM_SCRATCH = False and download the preprocessed dataset from my drive at this [link](https://drive.google.com/file/d/1-4TO3iKRtXi7S08Q7Aghaq8Us004uxkW/view?usp=sharing). Then drag the zipped file into the ./content in the Colab workspace
* Each epoch of fitting takes less than 10 seconds with Colab's free T4 GPU
* The fitting function will train up to 100 epochs, but has an Early Stop callback allowing it to stop earlier if the val_loss does not improve for 5 consecutive epochs after the 50th epoch. The best weights are restored.