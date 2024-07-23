# Emotion Classification Using RAVDESS Data

Welcome to the Emotion Classification project using the RAVDESS dataset! This project consists of four main steps, each documented in a separate notebook. Below is a detailed guide to navigate through these notebooks and understand their contents.

You can view the HTML versions of the notebooks with the links below to get a better picture of the steps involved.
- [Step 1: Loading Data](https://htmlpreview.github.io/?https://github.com/Chai-T29/Video_Audio_SentimentAnalysis/blob/364df9d09017d037ea1ed29a13040e9ab462ce81/RAVDESS_HTML_Notebooks/1_Video_Feature_Extraction_3DHOG.html)
- [Step 2: Video Feature Extraction](https://htmlpreview.github.io/?https://github.com/Chai-T29/Video_Audio_SentimentAnalysis/blob/364df9d09017d037ea1ed29a13040e9ab462ce81/RAVDESS_HTML_Notebooks/0_Loading_RAVDESS_Data.html)
- [Step 3: Audio Feature Extraction](https://htmlpreview.github.io/?https://github.com/Chai-T29/Video_Audio_SentimentAnalysis/blob/364df9d09017d037ea1ed29a13040e9ab462ce81/RAVDESS_HTML_Notebooks/2_Audio_Feature_Extraction.html)
- [Step 4: Building Classification Model](https://htmlpreview.github.io/?https://github.com/Chai-T29/Video_Audio_SentimentAnalysis/blob/364df9d09017d037ea1ed29a13040e9ab462ce81/RAVDESS_HTML_Notebooks/3_Emotion_Classification.html)

## Notebooks Overview

### 1. Loading Data

File: 0_Loading_RAVDESS_Data.ipynb

#### Description

This notebook is dedicated to downloading and preparing the RAVDESS dataset for our emotion classification project.

#### Contents

1. Importing Libraries and Data:
  - Essential libraries and setup.
  - Instructions for obtaining an API key to access the data from Zenodo.
2. Downloading Data:
  - Code to download and extract speech and song files from the RAVDESS dataset.
3. Creating Training and Testing Data:
  - Functions for resizing, interpolating, and converting video frames into arrays.
  - Splitting the data into training and testing sets.
4. Saving Data to Disk:
  - Saving processed video data to disk for later use.


### 2. Video Feature Extraction

File: 1_Video_Feature_Extraction_3DHOG.ipynb

#### Description

This notebook focuses on extracting features from the video data using a custom 3D Histogram of Oriented Gradients (HOG) algorithm.

#### Contents

1. Importing Libraries and Data:
  - Loading the training and testing video data.
2. 3D HOG Feature Extraction:
  - Detailed explanation and implementation of the 3D HOG algorithm for dimensionality reduction.
3. Visualizing HOG Features:
  - Visualization of gradient magnitudes and angles for a sample video.
4. Implementing Feature Extraction and Saving Data:
  - Code to compute HOG features for all videos and save them to disk.

### 3. Audio Feature Extraction

File: 2_Audio_Feature_Extraction.ipynb

#### Description

This notebook is dedicated to extracting relevant features from the audio data in the RAVDESS dataset.

#### Contents

1. Importing Libraries and Data:
  - Loading audio data and necessary libraries.
2. Custom Feature Engineering and Extraction Process:
  - Detailed steps for processing audio files, including adding noise, changing pitch, and speed.
  - Extracting various audio features such as MFCCs, Mel Spectrogram, ZCR, RMSE, Chroma, and Spectral Contrast using Librosa.
  - Projection of audio features onto a B-Spline basis for dimensionality reduction.
3. Visualizing Audio Features:
  - Visualizing the transformed audio and extracted features.
4. Implementing Feature Extraction and Saving Data:
  - Code to compute and save the extracted audio features.

### 4. Emotion Classification

File: 3_Emotion_Classification.ipynb

#### Description

This notebook covers the methods for classifying emotions using the extracted video and audio features.

#### Contents

1. Importing Libraries and Data:
  - Loading the extracted video and audio features.
2. Additional Dimensionality Reduction:
  - Applying Partial Tucker Decomposition to further reduce the dimensionality of the features.
3. Developing Classification Models:
  - Training and evaluating different classifiers including Random Forest, Support Vector Classifier (SVC), and Multilayer Perceptron (MLP).
  - Combining video and audio classifiers using an ensemble method to improve performance.
4. Visualizing Results:
  - Detailed visualizations of model performance, including confusion matrices and classification reports.

How to Navigate

1. Start with 0_Loading_RAVDESS_Data.ipynb:
	•	Follow the instructions to download and preprocess the data.
	•	Ensure all data is saved correctly for subsequent steps.
2. Proceed to 1_Video_Feature_Extraction_3DHOG.ipynb:
	•	Run the notebook to extract and save the video features using the custom 3D HOG algorithm.
3. Continue with 2_Audio_Feature_Extraction.ipynb:
	•	Extract and save audio features using the detailed feature engineering process outlined.
4. Finally, run 3_Emotion_Classification.ipynb:
	•	Train and evaluate the emotion classification models.
	•	Explore the performance metrics and visualizations to understand model efficacy.

By following these steps, you will gain insights into the process of building a robust emotion classification model using both video and audio features from the RAVDESS dataset. Happy learning and coding!
