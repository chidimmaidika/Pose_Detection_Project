# Pose_Detection_Project

![image](https://github.com/ChidimmaIdika/Pose_Detection_Project/assets/137975543/bfae9941-6027-4615-86cd-fcf5f67d4c45)

## Table of Contents
- [Introduction](#introduction)
- [Getting Started](#getting-started)
- [Real-time Pose Detection](#real-time-pose-detection)
- [Sample Output](#sample-output)
- [Contributions and Feedback](#contributions-and-feedback)
- [License](#license)

## Introduction
In this project, I explored the exciting world of computer vision and real-time pose detection using the power of [MediaPipe](https://mediapipe.dev/). This project is designed to help you understand how to detect and track human body landmarks in real-time video streams from your webcam.

## Getting Started..

### Importing Essential Libraries
To dive into this project, you will need to import some essential libraries. I used OpenCV (cv2) for capturing and processing video streams and MediaPipe for pose detection.   
> *import cv2   
import mediapipe as mp*

### Identifying Your Webcam
You can choose between a local or external webcam by setting the cv2.VideoCapture parameter. In this project, 0 corresponds to a local webcam, and 1 to an external webcam.   
> *cap = cv2.VideoCapture(0)*

### Leveraging MediaPipe Pose Detection
I harnessed the power of MediaPipe's pose detection module to detect key landmarks in the human body. The mp.solutions.pose package provides a straightforward way to get pose landmarks in real-time.   
> *mpPose = mp.solutions.pose
pose = mpPose.Pose()*

### Drawing Landmarks
The mp.solutions.drawing_utils module allows you to draw and connect the detected landmarks, making it easy to visualize the pose estimation.

### Real-time Pose Detection
Once everything is set up, the project captures video frames from your webcam, converts them to RGB format, applies pose detection, and draws the landmarks. The results are shown in real-time.   
> *while True:   
    _, img = cap.read()   
    imgRGB = cv2.cvtColor img, cv2.COLOR_BGR2RGB   
    results = pose.process(imgRGB)   
    if results.pose_landmarks:   
        mpDraw.draw_landmarks(img, results.pose_landmarks, mpPose.POSE_CONNECTIONS)   
    cv2.putText(img, '10Alytics Pose Detection', (10, 50), cv2.FONT_HERSHEY_PLAIN, 2, (255, 255, 255), 2)   
    cv2.imshow('10Alytics Pose Detection', img)   
    if cv2.waitKey(1) & 0xff == ord('q'):   
        break*

## Sample Output
Here's an example of the project's output:




## Contributions and Feedback
This project is open-source and hosted on GitHub, welcoming contributions and feedback from the community.   
If you have ideas for improvements, bug fixes, or new features, please feel free to open issues or submit pull requests. Collaboration and learning are at the core of this project.

## License
This Pose Detection Project is released under the [MIT License](https://opensource.org/license/mit/), which means you have the freedom to use and adapt the code for your projects.

Let's explore the world of pose detection together and see what incredible applications we can build with this technology.
