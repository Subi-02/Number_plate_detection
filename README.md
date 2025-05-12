
# Vehicle Number Plate Detection using EasyOCR

This project detects and highlights vehicle number plates from images using [EasyOCR](https://github.com/JaidedAI/EasyOCR) in Python, running on Google Colab. It uses a dataset of Indian vehicle number plates stored on Google Drive.

---

## 🚀 Features
- Detects text (number plate) from images using OCR.
- Draws bounding boxes and overlays the detected text on images.
- Works on a folder of multiple images.
- Displays and prints results in Google Colab.

---

## 📁 Folder Structure
```
Indian_Number_Plates/
└── Sample_Images/
    ├── car1.jpg
    ├── car2.jpg
    ├── ...
```

---

## 🧰 Dependencies
Install required libraries:

```bash
!pip install easyocr
```

Also make sure the following Python libraries are available:
- OpenCV (`cv2`)
- `matplotlib`
- `os`
- `google.colab`
- `easyocr`

These are generally pre-installed on Google Colab.

---

## 🔧 How to Use

### 1. Mount Google Drive

```python
from google.colab import drive
drive.mount('/content/drive')
```

### 2. Set Dataset Path

```python
dataset_path = '/content/drive/MyDrive/Indian_Number_Plates/Sample_Images'
```

Ensure this path correctly points to your image dataset in Google Drive.

### 3. Run the Program
The script:
- Initializes the EasyOCR reader.
- Iterates over all image files in the dataset folder.
- Detects and draws bounding boxes around the number plates.
- Displays the results using `cv2_imshow()` in Colab.

### 4. Main Functions

- **`detect_number_plate(image_path)`**
  - Detects number plate text from a single image.
  - Draws bounding boxes and labels the detected text.

- **`analyze_dataset(dataset_path)`**
  - Iterates over all images in a folder.
  - Applies detection and displays results for each image.

---

## 📌 Output Example
For each image:
```
Processing car1.jpg...
Detected Text for car1.jpg: ['MH12AB1234']
```

Image with highlighted number plate is displayed using `cv2_imshow`.

---

## 📤 Final Output
Prints a summary of all detected texts:
```
All Detected Texts:
car1.jpg: ['MH12AB1234']
car2.jpg: ['DL5CAF5031']
...
```

---

## 📌 Note
- OCR results may vary depending on image quality and clarity.
- This project is a prototype and may need post-processing or filtering for perfect results.

---

## 🧠 Future Enhancements
- Use YOLO or another object detection model to first locate number plates before running OCR.
- Save the results to a CSV or Excel file.
- Improve accuracy with image pre-processing (grayscale, thresholding, etc.).
