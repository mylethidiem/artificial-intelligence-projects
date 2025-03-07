# IoT Project Light Controlling Using Hand Guestures


## Step 1: Preparing data and environment
Using [Google MediaPipe technology](https://ai.google.dev/edge/mediapipe/solutions/guide) for [hand gesture recognition](https://github.com/google-ai-edge/mediapipe/blob/master/docs/solutions/hands.md).
1. Set up the work environment \
1.1 Using Conda with Python 3.10
- Create new environment with Python 3.10:
```bash
conda create -n gesture_env python=3.10.0
```
- Activate environment:
```bash
conda activate gesture_env
```
1.2 Install libraries from requirements.txt
```bash
pip install -r requirements.txt
```
2. Configure Gesture Class in hand_gesture.yaml
3. [Optional] Generate landmark data \
Run this script to collect data:
```bash
python generate_landmark_data.py
```

## Step 2: Building and training a hand gesture classification model
Training process
1. Load data
2. Build MLP model
3. Training model
4. Model evaluation

Run file: `hand_gesture_recgonition.ipynb`

## Step 3: Implement model and control lights with hand gestures
1. Goal:
   1. Real-time hand gesture recognition: use webcam to capture images and apply trained model to recognize gestures.
   2. Gesture-based light control: Perform on/off light operation in simulation or control real light devices via relay module and Modbus RTU RS485.
   3. Provide options for users: Allow running in simulation mode (no hardware) or real mode (with hardware).
2. Operating mode options: Set `device = True` if running real mode, `device = False` if running simulation.
3. [Optional] Hardware (in case you want to run real mode)
   1. Hardware:4 Modbus RTU RS485 communication relays, USB to RS485 communication converter circuit, 3 bulbs and lamp holders
   2. Run:
	`python detect_simulation.py`

