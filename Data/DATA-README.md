# Data Sources Info

Flickr Dataset: https://www.kaggle.com/datasets/hsankesara/flickr-image-dataset/

We used only a subset of this data where we filtered out images containing "dog", "cat", "horse", and "cow". The filtering step was performed in "preprocessing.py". The filtered data includes an "Images" folder containing all the images and an Excel file, "captions.xlsx", which holds all the associated captions.

Unfortunately, the "Images" folder is too large for submission to GitHub. This folder contains all the images referenced in the "image_name" column of the "captions.xlsx" file.

- "train_df.csv", "val_df.csv", and "test_df.csv" are the training, validation, and testing datasets after performing train_test_split. Around 53.3% of the data are for training, 26.7% of the data are for validation, and 20% of the data are for testing.

- "train_image_embeddings.npy", "val_image_embeddings.npy", and "test_image_embeddings.npy" are the numpy arrays created after extracting image features using the VGG-16 model. Unfortunately, "train_image_embeddings.npy" is too large for submission to GitHub.
