# Hand Gesture Media Controller

A Python application that allows you to control media playback using hand gestures captured through your webcam. This project uses computer vision and machine learning to recognize hand gestures and translate them into media control commands.

## Features

- **Play/Pause**: Pinch your thumb and index finger together
- **Fast Forward**: Swipe your open hand to the right
- **Rewind**: Swipe your open hand to the left
- **Volume Up**: Swipe your open hand upward
- **Volume Down**: Swipe your open hand downward

## Requirements

- Python 3.x
- OpenCV (cv2)
- MediaPipe
- PyAutoGUI

## Installation

1. Clone this repository:
```bash
git clone https://github.com/yourusername/hand_gesture_media_controller.git
cd hand_gesture_media_controller
```

2. Create and activate a virtual environment (recommended):
```bash
python -m venv .venv
source .venv/bin/activate  # On Windows, use: .venv\Scripts\activate
```

3. Install the required packages:
```bash
pip install opencv-python mediapipe pyautogui
```

## Usage

1. Make sure your webcam is connected and accessible
2. Run the main script:
```bash
python hand_gesture_recognition.py
```
3. Position yourself in front of the webcam
4. Use the following gestures to control your media:
   - Pinch thumb and index finger to play/pause
   - Swipe right with open hand to fast forward
   - Swipe left with open hand to rewind
   - Swipe up with open hand to increase volume
   - Swipe down with open hand to decrease volume
5. Press 'q' in the OpenCV window to quit the application

## Configuration

The following parameters can be adjusted in the code to fine-tune gesture recognition:

- `PINCH_DIST`: Distance threshold for pinch gesture (default: 35 pixels)
- `SWIPE_THRESH_X`: Horizontal swipe sensitivity (default: 120 pixels)
- `SWIPE_THRESH_Y`: Vertical swipe sensitivity (default: 120 pixels)
- `HISTORY_FRAMES`: Number of frames to evaluate a swipe (default: 5)
- `ACTION_DELAY`: Debounce time between actions (default: 0.60 seconds)

## How It Works

The application uses MediaPipe's hand tracking solution to detect and track hand landmarks in real-time. It then processes these landmarks to recognize specific gestures:

1. For play/pause: Measures the distance between thumb and index finger
2. For swipes: Tracks the movement of the wrist over multiple frames to determine direction and magnitude

The recognized gestures are then translated into keyboard commands using PyAutoGUI to control media playback.

