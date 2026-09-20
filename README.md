# Facial Emotion Recognition using CNN

A deep learning-based facial emotion recognition system that detects faces from a webcam and classifies the detected facial expression into one of seven emotion categories using a Convolutional Neural Network (CNN).

## Project Overview

This project uses a CNN trained on the **Face Expression Recognition Dataset** to recognize facial emotions from grayscale facial images.

The trained model is integrated with **OpenCV** for real-time webcam-based emotion detection. A Haar Cascade classifier is used to detect faces, and the CNN model predicts the emotion of each detected face.

### Emotions Recognized

* Angry
* Disgust
* Fear
* Happy
* Neutral
* Sad
* Surprise

## Technologies Used

* Python
* TensorFlow / Keras
* OpenCV
* NumPy
* Matplotlib
* Jupyter Notebook
* Haar Cascade Classifier

## Project Structure

```text
Facial-Emotion-Recognition/
│
├── dataset/
│   ├── README.md
│   ├── train/
│   │   ├── angry/
│   │   ├── disgust/
│   │   ├── fear/
│   │   ├── happy/
│   │   ├── neutral/
│   │   ├── sad/
│   │   └── surprise/
│   │
│   └── validation/
│       ├── angry/
│       ├── disgust/
│       ├── fear/
│       ├── happy/
│       ├── neutral/
│       ├── sad/
│       └── surprise/
│
├── models/
│   └── model.h5
│
├── haarcascade/
│   └── haarcascade_frontalface_default.xml
│
├── notebooks/
│   └── emotion-classification-cnn-using-keras.ipynb
│
├── src/
│   └── main.py
│
├── .gitignore
├── requirements.txt
└── README.md
```

> **Note:** The dataset images are not included in the repository because of their size. See `dataset/README.md` for the dataset source and setup instructions.

## Model

The project uses a CNN architecture consisting of:

* Convolutional layers
* Batch Normalization
* ReLU activation
* Max Pooling
* Dropout
* Fully Connected (Dense) layers
* Softmax output layer

### Input

```text
48 × 48 grayscale facial image
```

### Output

```text
7 emotion classes
```

The trained model is saved as:

```text
models/model.h5
```

## Workflow

```text
Face Expression Recognition Dataset
                ↓
       Image Preprocessing
                ↓
        CNN Model Training
                ↓
          Trained Model
          (model.h5)
                ↓
            Webcam
                ↓
       Face Detection using
          Haar Cascade
                ↓
      48 × 48 Grayscale Face
                ↓
        CNN Emotion Prediction
                ↓
         Emotion Label
```

## Setup

### 1. Clone the repository

```bash
git clone https://github.com/Heenal-15/Facial-Emotion-Recognition.git
cd Facial-Emotion-Recognition
```

### 2. Create a virtual environment

```bash
python -m venv .venv
```

### 3. Activate the virtual environment

**Windows PowerShell:**

```powershell
.venv\Scripts\Activate.ps1
```

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

## Dataset Setup

The project uses the **Face Expression Recognition Dataset**.

The dataset should be arranged as:

```text
dataset/
├── train/
│   ├── angry/
│   ├── disgust/
│   ├── fear/
│   ├── happy/
│   ├── neutral/
│   ├── sad/
│   └── surprise/
│
└── validation/
    ├── angry/
    ├── disgust/
    ├── fear/
    ├── happy/
    ├── neutral/
    ├── sad/
    └── surprise/
```

The dataset itself is excluded from GitHub through `.gitignore`.

Refer to [`dataset/README.md`](dataset/README.md) for the dataset source and download instructions.

## Running the Application

After installing the dependencies and ensuring the trained model is present in `models/model.h5`, run:

```powershell
python src/main.py
```

This will:

1. Open the webcam.
2. Detect faces using the Haar Cascade classifier.
3. Extract and resize detected faces to `48 × 48`.
4. Convert the face image to grayscale.
5. Pass the processed image to the trained CNN.
6. Display the predicted emotion on the webcam feed.

### Exit

Press:

```text
q
```

to close the application.

## Training the Model

The training process is available in:

```text
notebooks/emotion-classification-cnn-using-keras.ipynb
```

The notebook handles:

* Dataset loading
* Image preprocessing
* Training and validation data generation
* CNN architecture
* Model training
* Validation
* Saving the trained model

The trained model is saved as:

```text
models/model.h5
```

The notebook only needs to be run when you want to retrain the model or experiment with the CNN architecture and training parameters.

For normal webcam prediction, you only need:

```text
models/model.h5
```

and:

```text
haarcascade/haarcascade_frontalface_default.xml
```

## Hardware

The application can run on a CPU. GPU acceleration is not required for webcam inference.

## Notes

* The webcam must be accessible to the application.
* The model expects grayscale `48 × 48` facial images.
* Prediction quality can vary depending on lighting, facial orientation, image quality, and the training data.
* The dataset is not included in this repository because of its size.

## License

This project is intended for educational and learning purposes.
