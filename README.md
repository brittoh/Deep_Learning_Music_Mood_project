# Deep_Learning_Music_Mood_project
Deep_Learning_Music_Mood_project



## Identifying the Deep Learning Problem

The primary objective of this project is to classify songs into various moods using their musical features. This represents a multiclass classification challenge, where the model must learn from labeled data—songs with known moods—and predict the mood of new, unseen songs.

#### Problem Context

The project draws inspiration from the article ["Predicting the Music Mood of a Song with Deep Learning"](https://towardsdatascience.com/predicting-the-music-mood-of-a-song-with-deep-learning-c3ac2b45229e), where the author uses Spotify data to predict the mood of music. The article emphasizes the importance of mood prediction in music streaming platforms, where understanding the emotional context of songs can enhance user experience by providing personalized recommendations.

#### Why Deep Learning?

Given the complexity and variety of features in the dataset, such as tempo, key, loudness, and spectral features, deep learning models are particularly well-suited for this problem. These models excel in capturing intricate patterns in large datasets, making them ideal for understanding the nuanced relationships between musical features and moods.

#### Models to be Implemented

To tackle this problem, we will implement and compare multiple deep learning models:

1. **Fully Connected Neural Network (FCNN)**: A baseline model that connects every neuron in one layer to every neuron in the next, capturing general patterns in the data.
   
2. **Convolutional Neural Network (CNN)**: A model that applies convolutional layers to extract local features from the input data, potentially capturing more detailed patterns in the musical features.

3. **Recurrent Neural Network (RNN) with LSTM layers**: A model designed to capture temporal dependencies in sequential data, which is crucial for understanding how the sequence of musical notes or features relates to the mood of a song.

#### Traditional Supervised Learning Model

In addition to deep learning models, we will evaluate the performance of traditional supervised learning model:

 **Random Forest**: An ensemble learning method that constructs multiple decision trees during training and outputs the mode of the classes for classification.

#### Goal

The goal is to determine the most effective approach for mood classification, comparing the performance of deep learning models against traditional supervised learning models. This comparative analysis will help identify the strengths and limitations of each model type in the context of music mood classification.


## Data, Data Collection Method, and Provenance

The data for this project comes from the [Million Song Dataset (MSD)](http://millionsongdataset.com/pages/getting-dataset/), a collaborative effort between The Echo Nest and the Music Information Retrieval community. The dataset was originally collected to aid researchers in developing new algorithms for music recommendation, analysis, and retrieval. The full MSD contains millions of records totaling over 300 GB. Due to the sheer size of the full dataset, we will use the `MillionSongSubset`, which is a more manageable version containing 10,000 songs (approximately 1% of the full dataset, totaling 1.8 GB). According to the MSD website, this subset was curated to include a diverse selection of songs with detailed feature annotations.

**Note:** The dataset does not include listenable audio files but provides extensive metadata, including information about the songs, artists, and other relevant features.

### Structure of the Dataset

The dataset is organized into several folders containing files in the HDF5 (`.h5`) format. These files are nested within a directory structure, which we'll need to parse and transform to extract useful features for our analysis. Below is an example of the folder structure:

```
millionsongsubset/
│
├── AdditionalFiles/
│   ├── MSD_allmusic_tags.txt
│   ├── MSD_lastfm_tags.txt
│   └── MSD_track_metadata.db
│
├── data/
│   ├── A/
│   │   ├── TRAAAAW128F429D538.h5
│   │   ├── TRAAABD128F429CF47.h5
│   │   └── ...
│   │
│   ├── B/
│   │   ├── TRABBJE12903CB55B7.h5
│   │   ├── TRABBOP128F931B50D.h5
│   │   └── ...
│   │
│   ├── C/
│   │   ├── TRACABD128F92CDBDF.h5
│   │   ├── TRACBBC128F9302667.h5
│   │   └── ...
│   │
│   └── ... (continues with more folders labeled D-Z)
│
├── LICENSE.txt
└── README.txt
```

### Creating Mood Labels

The `Million Song Subset` does not include a predefined mood label for each song. We will create these mood labels in the `Labeling Mood of the Music` section, where the methodology and calculations for assigning moods will be detailed. 

For convenience, I have prepared a version of the dataset with the `mood` field included and uploaded it as a CSV file on Kaggle. You can access this version here: [Million Song Subset](https://www.kaggle.com/datasets/brittoh/million-song-subset).

#### Data Dicitionary
| #  | Column     | Non-Null Count | Dtype   |
|----|------------|----------------|---------|
| 0  | artist     | 10,000 non-null | object  |
| 1  | title      | 10,000 non-null | object  |
| 2  | mood  | 10,000 non-null | object|
| 3  | intensity  | 10,000 non-null | float64|
| 4  | rhythm     | 10,000 non-null | float64|
| 5  | timbre     | 10,000 non-null | float64|
| 6  | pitch      | 10,000 non-null | float64|


The project includes two files: a Jupyter notebook and a requirements file. I used Python 3.11.9, and I recommend installing the packages listed in the requirements file to avoid version-related issues.
