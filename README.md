# Emotion Classification Using RAVDESS Data

Welcome to the Emotion Classification project using the RAVDESS dataset! Although a lot of the concepts from this project are based off of recent research, the methodology for this project is unique, simple enough to follow, and effective! The main focus of this project is to show that we can derive meaningful results without the use of complex models and architectures, that are often too time-consuming to process and train. A solid feature extraction pipeline is the foundation to any good model, and that is the focus of this project. I hope you enjoy!

This project consists of four main steps, each documented in a separate notebook. Below is a detailed guide to navigate through these notebooks and understand their contents.

You can view the HTML versions for the scripts below. The markdown may not render, but you can view an example video in step 2, and example audios in step 3. I would highly recommend checking them out because they look very cool! If the videos do not pop up, just refresh the page, and it should show!

To recreate the contents, or to view the code directly, continue reading the documentation below these links.
- [Step 1: Loading Data](https://htmlpreview.github.io/?https://github.com/Chai-T29/Video_Audio_SentimentAnalysis/blob/364df9d09017d037ea1ed29a13040e9ab462ce81/RAVDESS_HTML_Notebooks/0_Loading_RAVDESS_Data.html)
- [Step 2: Video Feature Extraction](https://htmlpreview.github.io/?https://github.com/Chai-T29/Video_Audio_SentimentAnalysis/blob/364df9d09017d037ea1ed29a13040e9ab462ce81/RAVDESS_HTML_Notebooks/1_Video_Feature_Extraction_3DHOG.html)
- [Step 3: Audio Feature Extraction](https://htmlpreview.github.io/?https://github.com/Chai-T29/Video_Audio_SentimentAnalysis/blob/364df9d09017d037ea1ed29a13040e9ab462ce81/RAVDESS_HTML_Notebooks/2_Audio_Feature_Extraction.html)
- [Step 4: Building Classification Model](https://htmlpreview.github.io/?https://github.com/Chai-T29/Video_Audio_SentimentAnalysis/blob/364df9d09017d037ea1ed29a13040e9ab462ce81/RAVDESS_HTML_Notebooks/3_Emotion_Classification.html)

## Requirements

```bash
pip install requests tqdm opencv-python-headless numpy matplotlib tensorly librosa seaborn scikit-fda pandas torch scikit-learn
```

## Notebooks Overview

### 1. Loading Data

File: 0_Loading_RAVDESS_Data.ipynb

#### Description

This notebook is dedicated to downloading and preparing the RAVDESS dataset for our emotion classification project.

#### Contents

1. Importing Libraries and Data:
  - Essential libraries and setup.
  - Information on obtaining a free api key from Zenodo.
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
2. 3D HOG Feature Extraction (my own custom implementation):
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

## How to Navigate

1. Start with 0_Loading_RAVDESS_Data.ipynb:
  - Follow the instructions to download and preprocess the data.
  - Ensure all data is saved correctly for subsequent steps.
2. Proceed to 1_Video_Feature_Extraction_3DHOG.ipynb:
  - Run the notebook to extract and save the video features using the custom 3D HOG algorithm.
3. Continue with 2_Audio_Feature_Extraction.ipynb:
  - Extract and save audio features using the detailed feature engineering process outlined.
4. Finally, run 3_Emotion_Classification.ipynb:
  - Train and evaluate the emotion classification models.
  - Explore the performance metrics and visualizations to understand model efficacy.

## Conclusion
This project showcases the potential of a custom approach to emotion classification using multimodal data. By combining a 3D Histograms of Oriented Gradients for video features and advanced audio feature extraction with B-Spline transformations, we were able to create a robust and efficient feature extraction pipeline. The integration of these features through Partial Tucker Decomposition significantly reduced the dimensionality, making our models more efficient without sacrificing performance. The impressive accuracy of our ensemble method underscores the power of combining video and audio data, paving the way for more sophisticated and accurate emotion detection systems in real-world applications. This custom approach not only enhances the accuracy of emotion classification but also demonstrates the potential for broader applications in any field requiring nuanced analysis of multimedia data.

By following these steps, you will gain insights into the process of building a robust emotion classification model using both video and audio features from the RAVDESS dataset. Happy learning and coding!
