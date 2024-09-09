# Sign Language Detection using Mediapipe and Custom LSTM Model

This project aims to detect and recognize sign language gestures in real-time using a custom-trained LSTM model and the Mediapipe library for extracting keypoints. The model predicts three sign language gestures from a live webcam feed.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Model Architecture](#model-architecture)
- [Dataset](#dataset)
- [Live Detection](#live-detection)
- [Contributing](#contributing)
- [License](#license)



## Installation

To set up the environment for this project, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/sign-language-detection.git
   cd sign-language-detection

2. Install the required dependencies listed in `requirements.txt`:
   ```bash
   pip install -r requirements.txt
   
## Usage

1. Open the `Sign_Language_Detection.ipynb` notebook file in Jupyter Notebook.
2. Follow the cells to load the Mediapipe model, process the webcam input, and start gesture detection.
3. The notebook is designed to capture live feed from your webcam, so ensure that the camera is enabled.

### Running the Live Detection:
- The system will start detecting gestures from the webcam feed and use the custom-trained LSTM model to recognize the sign language gestures.
- You can press `'q'` to exit the live detection at any time.



## Model Architecture

The model used for sign language detection is a custom-trained LSTM (Long Short-Term Memory) network. The input to the model is the keypoints extracted using Mediapipe, which include hand landmarks, pose, and face landmarks.

### Key steps include:
- **Data Preprocessing**: Extract keypoints using the Mediapipe library.
- **Training**: The LSTM model was trained on a custom dataset collected for different sign language gestures.
- **Prediction**: The model predicts the most likely gesture based on the recent sequence of keypoints from the webcam feed.



## Dataset

The dataset used in this project consists of recorded gestures that were labeled and used to train the LSTM model. You can find the training data and keypoint extraction logic in the notebook. The dataset is expected to be stored in the `MP_data` directory.

### Keypoints:
- **Hands**: 21 keypoints per hand.
- **Pose**: 33 keypoints.
- **Face**: Optional facial keypoints can also be used if needed.

You can collect more data by recording additional gestures via the webcam and retrain the model if you want to extend the vocabulary of detected gestures.



## Live Detection

The live detection uses the following workflow:

1. **Capture**: The webcam captures live video.
2. **Keypoint Extraction**: Using Mediapipe, keypoints of hands, pose, and face are extracted in real-time.
3. **Prediction**: A sequence of keypoints (30 frames) is fed into the LSTM model for gesture prediction.
4. **Visualization**: The detected gesture is displayed in real-time on the video feed.

You can modify the list of actions and retrain the model if necessary to include more gestures.



## Contributing

Contributions to this project are welcome! You can extend the model by adding new gestures or improving the detection accuracy. Feel free to open issues or create pull requests.



## License

This project is licensed under the terms of the [LICENSE](LICENSE) file in this repository.


