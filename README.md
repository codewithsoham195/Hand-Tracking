🤏 ThumbsDown — Hand Gesture Controlled Door Unlocking System

A real-time hand gesture recognition system using OpenCV, MediaPipe, and Tkinter that unlocks a door (or toggles a relay) when a gentle pinch gesture is detected inside a specific region of interest (ROI).

🚀 Features
	•	🔒 Unlocks or locks door/relay using a specific hand gesture (pinch).
	•	🧠 Trained using the EgoHand dataset.
	•	📦 Real-time hand landmark detection with MediaPipe.
	•	📡 Sends HTTP requests to a relay module over IP.
	•	🎯 ROI detection using Shapely geometry.
	•	🖥️ Interactive IP prompt using Tkinter.
	•	🎥 Displays live camera feed with gesture overlays and FPS.

🛠️ Technologies Used
	•	Python
	•	OpenCV
	•	MediaPipe
	•	Tkinter
	•	Shapely
	•	urllib
	•	HTTP Relay Module (custom hardware)

🧠 How It Works
	1.	Prompts user to input the IP address of the relay module.
	2.	Starts the webcam and detects hands using MediaPipe.
	3.	Defines a rectangular ROI on the screen.
	4.	Detects specific fingertip landmarks (id: 4, 8, 12, 16, 20).
	5.	If all fingertips are within the ROI, the gesture is validated.
	6.	On pressing the Spacebar, a request is sent to:
	•	/OPEN_LED if the gesture is outside the ROI.
	•	/CLOSE_LED if the gesture is inside the ROI.

🧪 Requirements
	•	Python 3.x
	•	opencv-python
	•	mediapipe
	•	shapely

Install dependencies:

pip install opencv-python mediapipe shapely

💻 How to Run

python thumbsdown.py

On running, enter the IP address of the relay device when prompted.

📷 UI Preview
	•	Green box: ROI
	•	Red fingertips: Detected pinch inside ROI
	•	Status Text: WINDOW-OPEN or WINDOW-CLOSED
	•	FPS counter on top-left

⛓️ Endpoints Used
	•	http://<RELAY_IP>/OPEN_LED — to open the relay (unlock)
	•	http://<RELAY_IP>/CLOSE_LED — to close the relay (lock)

🧱 Project Structure

thumbsdown.py        # Main gesture detection script
README.md            # This file

🔐 Security Notice

Ensure that your relay module and the IP interface are secured and not exposed to public networks without authentication.
