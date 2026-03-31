# Project Report  
## Pre-trained Image Classifier to Identify Dog Breeds  
**Udacity AI Programming with Python Nanodegree Project**  

**Repository:** Pre-trained-Image-Classifier-to-Identify-Dog-Breeds-Udacity-Nanodegree  
**Author:** Yuktha2708  
**Project Type:** Image Classification using Transfer Learning (Pre-trained CNN Models)  

---

## 1. Introduction

This project implements an **image classification pipeline** using **pre-trained Convolutional Neural Network (CNN) models** to identify whether an image contains a dog and if so, predict the **dog breed**.  

The project is developed as part of the **Udacity AI Programming with Python Nanodegree**, focusing on applying deep learning models without training from scratch.

Instead of building a custom CNN model, the project uses **transfer learning**, leveraging powerful models trained on large datasets like **ImageNet**.

---

## 2. Objectives

The major objectives of the project are:

- Create an image classifier using Python.
- Use a **pre-trained CNN model** for classification.
- Predict whether an image contains:
  - a **dog**
  - a **human**
  - neither
- Identify the **dog breed** if a dog is detected.
- Compare accuracy and runtime performance of multiple CNN architectures.
- Generate classification statistics and performance reports.

---

## 3. Tools and Technologies Used

### Programming Language
- Python 3

### Python Libraries
- `argparse` – for command-line argument handling  
- `os` – for file/directory processing  
- `time` – for runtime tracking  
- CNN model support libraries (provided via Udacity environment)

### Pre-trained CNN Architectures
The project supports multiple pre-trained models:

- **AlexNet**
- **VGG**
- **ResNet**

These models are used for image classification based on ImageNet-trained weights.

---

## 4. Methodology / Workflow

The project follows a stepwise pipeline to process images and evaluate classification accuracy.

---

### Step 1: Command Line Argument Handling

The project accepts input arguments such as:

- image directory path
- CNN model architecture
- output file name

This is handled using:

- `get_input_args.py`

---

### Step 2: Extracting True Pet Labels

The true label is extracted from the image filename.  
Example:

- `Boston_terrier_02259.jpg` → **boston terrier**

This process is performed by:

- `get_pet_labels.py`

---

### Step 3: Image Classification using Pre-trained CNN

Each image is passed through a pre-trained CNN classifier which predicts the object label.

This is implemented in:

- `classifier.py`
- `classify_images.py`

The output includes:
- predicted label
- whether predicted label matches the true label

---

### Step 4: Label Matching

The predicted output label is compared against the extracted pet label.  
If both match, it is counted as a correct classification.

---

### Step 5: Dog and Human Detection

The system checks whether the true label and predicted label correspond to a dog breed using the list provided in:

- `dognames.txt`

This helps classify images into:
- dog images
- human images
- non-dog images

---

### Step 6: Computing Statistics

The performance of the classifier is measured using metrics such as:

- percentage of correctly classified dog breeds
- percentage of correctly identified dogs
- percentage of correctly identified non-dogs
- percentage of correctly identified humans

This is handled by:

- `calculates_results_stats.py`

---

### Step 7: Printing Final Results

The final output report is printed in a structured format, including:

- model used
- number of images tested
- overall accuracy metrics

This is handled by:

- `print_results.py`

---

## 5. System Architecture

### Input
- Image dataset directory (containing dog, human, and non-dog images)

### Processing
- Label extraction from filenames
- Classification using CNN model
- Dog/human detection
- Statistical evaluation

### Output
- Classification results for each image
- Summary statistics report

---

## 6. Repository File Structure

The repository contains the following important files:

| File Name | Purpose |
|----------|---------|
| `check_images.py` | Main program to execute classification pipeline |
| `classifier.py` | Contains CNN classifier function |
| `classify_images.py` | Classifies all images in the dataset |
| `get_input_args.py` | Reads command line arguments |
| `get_pet_labels.py` | Extracts pet labels from image filenames |
| `calculates_results_stats.py` | Computes accuracy statistics |
| `print_results.py` | Prints final results and summary |
| `dognames.txt` | Contains valid dog breed names |
| `uploaded_images/` | Folder containing test images |

---

## 7. Performance Evaluation

The project evaluates classification accuracy across different CNN architectures.

---

### 7.1 AlexNet
- **Fast execution**
- Lower classification accuracy compared to deeper networks

---

### 7.2 VGG
- Better breed classification accuracy than AlexNet
- Moderate runtime performance

---

### 7.3 ResNet
- Generally produces the **best accuracy**
- Slower execution compared to AlexNet

---

## 8. Results and Observations

### Key Observations
- Deep models such as **ResNet** and **VGG** perform better for dog breed prediction.
- **AlexNet** runs faster but has lower breed classification performance.
- Most CNN models are effective in identifying whether an image is a dog or not.
- Dog breed classification is more challenging than simply detecting a dog.

---

## 9. Conclusion

This project successfully demonstrates the use of **transfer learning** and pre-trained CNN models to classify dog breeds.

The pipeline can:
- classify images using a selected CNN architecture
- detect dogs vs humans vs other objects
- predict dog breeds
- generate accuracy metrics and summary reports

The evaluation confirms that deeper models such as **ResNet** and **VGG** provide higher accuracy, while **AlexNet** offers faster performance.

---

## 10. Future Improvements

Possible enhancements include:

- Training a custom CNN model for dog breeds.
- Adding top-3 prediction support instead of top-1 only.
- Improving dataset quality using augmentation.
- Building a GUI or web application for real-time classification.
- Supporting multiple animals in a single image.

---

## 11. References

- Udacity AI Programming with Python Nanodegree Program  
- ImageNet Dataset (used indirectly through pre-trained models)  
- Transfer Learning and CNN Architecture Concepts  

---

# Final Summary

This repository provides a complete Python-based solution for classifying dog breeds using pre-trained CNN architectures. It highlights the effectiveness of transfer learning and provides a structured pipeline for classification, evaluation, and reporting.