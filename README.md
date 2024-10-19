How It Was Built:
Tools and Libraries:

OpenCV: Used for video capture and frame-by-frame image processing.
MediaPipe: This Google framework is used to detect human poses and key landmarks on the body.
NumPy: Likely used for numerical operations, though its role in the notebook wasn’t explicitly visible.
Pose Detection:

The MediaPipe library identifies key body landmarks from the video feed (i.e., the person performing bicep curls).
These landmarks include specific points such as wrists, elbows, and shoulders, which are crucial for determining when a full bicep curl is completed.
Bicep Curl Logic:

Landmark Detection: The positions of the elbow and wrist are tracked. By analyzing the relative movement between these two landmarks, the program determines whether the arm is fully extended or contracted.
Counting Logic:
The program tracks the stage of the bicep curl (either "up" or "down") based on the angle between the arm's joints.
A full curl is counted when the arm transitions from full extension (down) to contraction (up) and back to extension.
Real-Time Feedback:

The program gives real-time feedback by displaying the current count of curls and the stage ("up" or "down") on the video feed.
It uses OpenCV to draw rectangles, text, and the detected pose landmarks on the live camera feed.
Control Mechanism:

The cv2.imshow() function from OpenCV shows the processed video feed with all annotations.
The user can press 'q' to exit the video feed and terminate the program.
How It Works:
Setup:

The user runs the program, which accesses their camera via OpenCV to start capturing video in real-time.
Pose Detection and Counting:

MediaPipe's pose detection model analyzes each video frame and extracts key points (wrist, elbow, shoulder).
Using these landmarks, the program calculates angles to detect when a full bicep curl is completed.
Real-Time Updates:

The curl counter updates dynamically as the user completes each rep, displaying the count and stage on the screen.
It also visualizes the user's detected pose by drawing landmarks and pose connections on the frame.
Termination:

The process continues until the user presses 'q' to quit the program, at which point the video capture is stopped and all windows are closed.
