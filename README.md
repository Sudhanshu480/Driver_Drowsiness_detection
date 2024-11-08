# Driver Drowsiness Detection Model

Welcome to the Driver Drowsiness Detection Model project which I have developed in collaboration with [Aayushii](https://github.com/aayushii31). This project is focused on detecting driver drowsiness in real-time using computer vision and deep learning. By tracking facial cues such as eye closure and yawning, the model provides timely alerts to help prevent drowsy driving incidents.

We are actively working on this project, continuously improving its accuracy and responsiveness, and exploring additional features for enhanced usability.

---

## Features

- **Real-Time Drowsiness Detection**: Monitors driver’s face and detects drowsiness signs in real-time using live video feed.
- **Eye and Mouth State Classification**: Uses CNN-based model to classify eye closure and yawning as key indicators of drowsiness.
- **Automated Alerts**: Sends visual and audio alerts to warn the driver if drowsiness is detected.
- **Efficient Performance**: Optimized for quick response to ensure the driver is alerted with minimal delay.

---

## Dataset

The dataset used to train this model was sourced from Kaggle:
[Drowsiness Dataset](https://www.kaggle.com/datasets/dheerajperumandla/drowsiness-dataset). It contains annotated images for both eye and mouth states, which helped in training the CNN model for accurately detecting drowsy behavior.

---

## Model Export and Deployment

After training, the CNN model was exported as a `.h5` file using TensorFlow. This model file allows us to load the trained model directly into our detection script, where it classifies eye and mouth states in real time, optimizing for rapid inferences.

---

## How it Works

The Driver Drowsiness Detection Model primarily revolves around detecting eye closure and yawning from a live video feed. Here’s an in-depth look at the process:

1. **Real-Time Video Capture**: Captures live video of the driver’s face using OpenCV.
2. **Preprocessing**: Each frame is processed to focus on the driver’s eyes and mouth regions, with resizing and normalization to prepare it for model input.
3. **Model Initialization**: A CNN model, built and trained using TensorFlow, is used for classifying eye and mouth states, identifying potential signs of drowsiness.
4. **State Classification**:
   - **Eye Closure**: The model classifies frames as 'open' or 'closed' based on eye state.
   - **Yawning**: The model classifies whether the mouth is open wide, indicating a yawn.
5. **Drowsiness Alert**: If both eye closure and yawning are detected over multiple frames, a drowsiness alert is triggered.

---

## Maintaining the Model

We are using version control and a structured session state to maintain consistent model performance, while regularly testing for real-time responsiveness. Currently, we are focused on:

- **Improving Model Accuracy**: Continuously refining the CNN model and testing it with augmented data to better generalize across different lighting conditions.
- **Real-Time Optimization**: Working to reduce latency in the detection and alert process, aiming for the fastest possible response.

---

## Prerequisites

To set up and run the project, you’ll need:

- **Python 3.9 or higher**
- **TensorFlow**
- **OpenCV**
- **NumPy**

Install all required packages by running:

```bash
pip install -r requirements.txt
```

---

## Usage

To run and interact with the Driver Drowsiness Detection Model:

1. **Run the Application**:
   ```bash
   python drowsiness_detection.py
   ```

2. **Interact with the App**:
   - **Start Video Feed**: The application will start capturing live video and monitoring facial cues for drowsiness.
   - **Receive Alerts**: The model will display visual and audio alerts in real-time when drowsiness signs are detected.

3. **Example**:
   - **Eye State**: Detected as "Open" or "Closed"
   - **Mouth State**: Detected as "Yawning" or "Not Yawning"
   - **Drowsiness Alert**: Triggered when eyes are closed and yawning is detected over consecutive frames.

---

## File Structure

The project structure is organized as follows:

```
drowsiness-detection/
│
├── drowsiness_detection.py  # Main application script
├── requirements.txt         # Required Python packages
├── model/                   # Directory containing pre-trained model files
├── utils.py                 # Utility functions for preprocessing
├── README.md                # Project documentation
└── LICENSE                  # Project license
```

---

## Application Code

### Eye and Mouth State Detection

The `detect_drowsiness` function is the core of the detection algorithm. Key components include:

- **Eye Detection**:
   - Analyzes each video frame, focusing on eye regions.
   - Uses the CNN model to classify whether eyes are open or closed.
   - Repeated "closed" detections trigger a drowsiness alert.

- **Yawning Detection**:
   - Analyzes mouth regions to detect wide openings, indicating yawning.
   - If yawning is detected across multiple frames, it contributes to the drowsiness alert.

### Alert Mechanism

Visual and audio alerts are generated when drowsiness signs are consistently detected, helping notify the driver in real time.

---

## Contributing

We welcome contributions! Please feel free to fork this repository and submit pull requests to propose improvements or add new features. This project is ongoing, and we are open to ideas on enhancing the detection capabilities and user experience.

