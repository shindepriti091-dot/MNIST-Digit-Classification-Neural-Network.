# MNIST Digit Classification using Neural Networks

## 1. Project Overview
This project implements a handwritten digit classification system using a Neural Network trained on the MNIST dataset. The notebook is designed to run in Google Colab and includes an image-prediction section for recognizing a user-supplied digit image.

**Project title:** MNIST Digit Classification using Neural Networks  
**Platform:** Google Colab / Jupyter Notebook  
**Language:** Python  
**Primary task:** Classify handwritten digits (0–9)

## 2. Objectives
- Load and prepare the MNIST handwritten digit dataset.
- Preprocess image data for neural-network training.
- Train a neural-network classifier.
- Evaluate the trained model.
- Accept an external digit image for prediction.
- Display the predicted digit.

## 3. Technologies Used
- Python 3
- TensorFlow / Keras
- NumPy
- OpenCV
- Matplotlib
- Seaborn
- Pillow
- Scikit-learn (optional, depending on notebook evaluation cells)
- Google Colab

## 4. Project Workflow
1. Import Python libraries.
2. Load the MNIST dataset.
3. Preprocess/normalize image data.
4. Prepare training and test data.
5. Build the neural-network model.
6. Train the model.
7. Evaluate the model.
8. Load an external image such as `3-digit.PNG`.
9. Convert the image to grayscale and resize it to 28×28.
10. Normalize and reshape the image.
11. Run `model.predict()`.
12. Use `argmax()` to obtain the predicted digit.

## 5. Image Prediction
The notebook contains a predictive system using OpenCV. The expected input is a handwritten digit image.

Example:
```python
input_image_path = input('Path of the image to be predicted: ')
input_image = cv2.imread(input_image_path)
```

The image is then:
- converted to grayscale,
- resized to 28×28,
- normalized to the 0–1 range,
- reshaped to the model's expected input,
- passed to the trained model.

The project test image `3-digit.PNG` was successfully recognized as digit **3** in Google Colab.

## 6. Google Colab Setup
1. Open Google Colab.
2. Upload the `.ipynb` notebook.
3. Open the **Files** panel.
4. Upload `3-digit.PNG`.
5. Run the notebook cells from top to bottom.
6. Run the prediction cell.
7. When prompted for the image path, enter:
```text
/content/3-digit.PNG
```
8. Check the output for the predicted digit.

### Important
If the notebook asks for Google Drive access through:
```python
from google.colab import drive
drive.mount('/content/drive')
```
this is only required if the project is actually reading files from Google Drive. For a directly uploaded `3-digit.PNG`, Drive mounting is not required.

## 7. Recommended Folder Structure
```text
MNIST-Digit-Classification/
│
├── MNIST_Digit_classification_using_Neural_Networks.ipynb
├── 3-digit.PNG
├── README.md
├── requirements.txt
└── PROJECT_REQUIREMENTS.md
```

## 8. Troubleshooting
### Error: `AttributeError: 'NoneType' object has no attribute 'clip'`
This usually means `cv2.imread()` did not load the image. Check the file path and make sure the image is uploaded to the Colab session.

Use:
```python
import os
print(os.path.exists('/content/3-digit.PNG'))
```
If it prints `True`, the file exists.

Then:
```python
input_image = cv2.imread('/content/3-digit.PNG')
print(input_image is None)
```
It should print `False`.

### Error while using `cv2_imshow`
Make sure the image variable is not `None` before displaying it:
```python
if input_image is not None:
    cv2_imshow(input_image)
else:
    print("Image could not be loaded.")
```

## 9. Reproducibility
Run the notebook cells in order. If the runtime is restarted, all variables and the trained model in memory are cleared, so the training/model-loading cells must be run again.

## 10. Future Enhancements
- Add a confusion matrix and classification report.
- Add training/validation accuracy and loss graphs.
- Add a CNN model for higher image-classification performance.
- Build a simple web interface using Streamlit or Flask.
- Allow users to draw a digit directly on a canvas.
- Add batch image prediction.

## 11. Author
**Student Project – MNIST Handwritten Digit Classification**

---
This README is prepared for academic/project submission and GitHub documentation.
