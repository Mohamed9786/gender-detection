# Object Detection and Gender Classification using YOLOv3 and TensorFlow

This project integrates YOLOv3 and TensorFlow for real-time object detection and gender classification using OpenCV and a webcam. The application can identify objects (like people, cars, etc.) and classify the gender (male or female) of any person detected. An optional Flask web interface is also provided for running the system via a web browser.

## Project Structure

```
object-detection-gender-classification/
├── yolov3/
│   ├── yolov3.cfg
│   ├── yolov3.weights
│   ├── coco.names
├── model/
│   ├── gender_model.h5
│   ├── train_gender_model.py
├── README.md
├── requirements.txt
├── main.py
```

## Features

- Real-time object detection using YOLOv3
- Gender classification using a pre-trained TensorFlow model
- Live webcam feed for detection

## Prerequisites

- Python 3.6 or later
- TensorFlow 2.x
- OpenCV

## Setup and Installation

1. **Clone the repository:**

    ```bash
    git clone https://github.com/your-username/object-detection-gender-classification.git
    cd object-detection-gender-classification
    ```

2. **Download the YOLOv3 weights:**

    Download the `yolov3.weights` file from the following link and place it in the `yolov3/` directory:

    ```
    https://pjreddie.com/media/files/yolov3.weights
    ```

3. **Install dependencies:**

    Install the required Python packages using `pip`:

    ```bash
    pip install -r requirements.txt
    ```

4. **Download or create the gender classification model:**

    Place the pre-trained `gender_model.h5` in the `model/` directory. You can optionally train your own model using the `train_gender_model.py` script.

## Running the Application

### Option 1: Run in the Terminal

Run the main script to perform object detection and gender classification directly in the terminal:

```bash
python main.py
```

This will open your webcam and display the live video feed with detections.

## Project Explanation

1. **YOLOv3 for Object Detection:**
   - YOLO (You Only Look Once) is a state-of-the-art object detection algorithm that is fast and accurate.
   - The model is configured using `yolov3.cfg` and weights are loaded from `yolov3.weights`. Object class names (like person, car, etc.) are loaded from `coco.names`.

2. **Gender Classification with TensorFlow:**
   - A custom-trained TensorFlow model is used to classify the gender (male or female) of detected persons.
   - The model takes detected faces, resizes them, and performs classification based on pre-trained weights.

3. **Real-Time Detection and Classification:**
   - The `main.py` script captures frames from the webcam, applies YOLOv3 to detect objects, and uses the gender model to classify detected persons.

## Files and Directories

- **`yolov3/`:** Contains YOLOv3 configuration files and weights.
- **`model/`:** Holds the gender classification model and optional training script.
- **`main.py`:** The main script to run object detection and classification.
- **`requirements.txt`:** List of required Python packages.
