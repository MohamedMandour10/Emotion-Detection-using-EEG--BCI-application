# BCI Emotions Detection Project

## Overview
Welcome to the BCI Emotions Detection Project! This project utilizes EEG data from the Muse headband to classify emotions and convey the detected emotions using a servo motor with an arrow pointing at a plate displaying the emotions. This README provides an overview of the project, including the data acquisition, feature extraction, machine learning models, and hardware implementation.

## Table of Contents
- [Introduction](#introduction)
- [Data Acquisition](#data-acquisition)
- [Feature Extraction](#feature-extraction)
- [Machine Learning Models](#machine-learning-models)
- [Hardware Implementation](#hardware-implementation)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Introduction
The Muse EEG headband is a wearable device designed to monitor brain activity using Electroencephalography (EEG). This project leverages the Muse headband to classify emotions such as positive, neutral, and negative states. Given the complexity of EEG data, we employ statistical feature extraction and machine learning models to achieve accurate emotion detection.

## Data Acquisition
Data was collected from two participants (one male and one female) for three minutes per emotional state (positive, neutral, and negative). The EEG signals were recorded from TP9, AF7, AF8, and TP10 locations using the Muse headband. Additionally, six minutes of resting neutral data were collected.

## Feature Extraction
Due to the temporal and auto-correlated nature of EEG waves, we used a sliding window approach to extract statistical features. Each 1-second window overlaps by 0.5 seconds with the adjacent window. The extracted features include:
- Sample mean and standard deviation
- Sample skewness and kurtosis
- Maximum and minimum values
- Sample variances and covariances
- Eigenvalues of the covariance matrix
- Frequency components using Fast Fourier Transform (FFT)

## Machine Learning Models
Two machine learning models were used for emotion classification:

### Multilayer Perceptron (MLP) Classifier
The MLP classifier is a neural network architecture suitable for capturing complex non-linear relationships in EEG data. It consists of interconnected layers of artificial neurons, making it well-suited for high-dimensional EEG data.

### Random Forest Classifier
The Random Forest classifier is an ensemble method combining multiple decision trees to improve robustness and accuracy. It handles noisy data effectively and can rank the importance of different EEG features, making it a reliable choice for real-world EEG applications.

## Hardware Implementation
A servo motor with an arrow is used to indicate the detected emotion on a plate. The plate is divided into sections representing different emotions. The servo motor moves the arrow to point at the detected emotion based on the classification results from the machine learning models.

## Installation
To install and run the project, follow these steps:

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/BCI-Emotions-Detection.git
    ```
2. Navigate to the project directory:
    ```bash
    cd BCI-Emotions-Detection
    ```
3. Install the required Python packages:
    ```bash
    pip install -r requirements.txt
    ```

## Usage
1. Connect the Muse EEG headband and start recording data.
2. Run the feature extraction script to preprocess the EEG data:
    ```bash
    python feature_extraction.py
    ```
3. Train the machine learning models using the preprocessed data:
    ```bash
    python train_models.py
    ```
4. Run the emotion detection script to classify emotions and control the servo motor:
    ```bash
    python detect_emotions.py
    ```

## Contributing
Contributions are welcome! Please fork the repository and submit a pull request for any enhancements or bug fixes.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

---

For more information or inquiries, please contact the EmotionsClassifier Team:
- Mohamed Elsayed Ali
- Mohamed Elsayed Eid
- Mariam Ahmed
- Mahmoud Magdy
- Mohamed Sayed
- Mosilhy
