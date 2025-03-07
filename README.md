# Skin-Oiliness-Level-Classification

## Overview
This project implements a deep learning model using ResNet-50 to classify skin oiliness levels into three categories: **dry, normal, and oily**. The model is trained on a dataset containing images of different skin types and provides treatment recommendations based on the classification results.

## Features
- **Image Classification**: Uses a pre-trained ResNet-50 model fine-tuned for skin oiliness classification.
- **Data Augmentation**: Includes transformations such as resizing, normalization, and flipping.
- **Training & Evaluation**: Implements training with cross-entropy loss and accuracy evaluation on validation and test datasets.
- **Live Image Prediction**: Allows users to take a photo via webcam and predict skin oiliness.
- **Treatment Suggestions**: Provides skincare recommendations based on the classified skin type.

## Dataset Structure
The dataset should be structured as follows:
```
skin-oiliness-level/
  ├── Oily-Dry-Skin-Types/
  │   ├── train/
  │   │   ├── dry/
  │   │   ├── normal/
  │   │   ├── oily/
  │   ├── valid/
  │   │   ├── dry/
  │   │   ├── normal/
  │   │   ├── oily/
  │   ├── test/
  │   │   ├── dry/
  │   │   ├── normal/
  │   │   ├── oily/
```

## Installation & Setup
1. Clone the repository:
   ```sh
   git clone https://github.com/yourusername/skin-oiliness-classification.git
   cd skin-oiliness-classification
   ```
2. Install dependencies:
   ```sh
   pip install -r requirements.txt
   ```
3. Ensure you have the dataset structured properly as described above.

## Training the Model
Run the following command to train the model:
```sh
python train.py
```

## Predicting Skin Oiliness
To predict the oiliness level of a new image:
```python
from predict import predict_user_input_image

image_path = "path/to/image.jpg"
predicted_label, treatment_options = predict_user_input_image(image_path)
print("Predicted skin type:", predicted_label)
print("Treatment options:")
for key, value in treatment_options.items():
    print(key + ":", value)
```

## Live Webcam Prediction (Google Colab Only)
If using Google Colab, you can capture an image from the webcam and classify it:
```python
from webcam import take_photo
image_path = take_photo()
predicted_label, treatment_options = predict_user_input_image(image_path)
```

## Model Performance
The model achieves an **accuracy of 86%** on the test set. Below is the confusion matrix:

![image](https://github.com/user-attachments/assets/a41c5bda-fc79-4f2a-812b-f0a01e16d106)


## License
This project is licensed under the MIT License. Feel free to use and modify it as needed.


