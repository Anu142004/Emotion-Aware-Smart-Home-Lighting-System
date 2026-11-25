Emotion-Aware Smart Home Lighting System
An AI- and IoT-based smart lighting project that detects a user's facial
expressions through a webcam and automatically changes an RGB LED's
color to correspond with the detected emotion.
Introduction
The Emotion-Aware Smart Home Lighting System combines computer vision,
machine learning, and embedded systems to create a personalized lighting
experience. A webcam captures the user's facial expressions, and a
Python-based emotion detection module analyzes the video stream to
identify emotions such as happiness, sadness, anger, surprise,
neutrality, fear, and disgust.

After an emotion is detected, the Python application sends the emotion
label to an Arduino microcontroller through serial communication. The
Arduino maps the received emotion to a predefined RGB color and controls
the LED using Pulse Width Modulation (PWM).

The project demonstrates how AI-driven emotion recognition can interact
with physical devices to create a more adaptive smart-home environment.
Problem Statement
Traditional lighting systems generally use fixed settings and require
users to adjust them manually. They do not respond to a user's facial
expressions or emotional state, which limits the ability to create a
personalized environment.

This project proposes an emotion-responsive lighting system that
combines facial emotion detection with Arduino-controlled RGB lighting.
The aim is to make lighting more interactive and adaptable to the user's
detected expression.
Objectives
- Capture the user's facial expressions in real time using a webcam.
- Detect and classify facial emotions using computer vision and a
  machine-learning-based emotion recognition model.
- Transmit the detected emotion from the Python application to Arduino
  through serial communication.
- Change the RGB LED color according to the detected emotion.
- Demonstrate an interactive smart-home application integrating AI and
  IoT.
Proposed System
The system consists of two main modules that work together.
1. Emotion Detection Module (Python)
- Captures live video frames from a webcam.
- Uses OpenCV to read and process video frames.
- Uses the FER-based emotion recognition component to identify facial
  expressions.
- Determines the detected emotion and prepares an emotion label or
  code.
- Sends the emotion information to Arduino through serial
  communication using the configured COM port.
2. Lighting Control Module (Arduino)
- Receives the emotion information sent by the Python application.
- Matches the received emotion with a predefined color.
- Controls the red, green, and blue LED channels using PWM output.
- Changes the RGB LED color to represent the detected emotion.
System Architecture
             Webcam
                |
                v
       Live Video Capture
                |
                v
       Python + OpenCV
                |
                v
     Facial Emotion Detection
          (FER Model)
                |
                v
       Detected Emotion
                |
                v
      Serial Communication
                |
                v
         Arduino Uno
                |
                v
        PWM RGB Control
                |
                v
          RGB LED Output
Emotion-to-Color Mapping
The system maps detected emotions to the following LED colors:

  Detected emotion   RGB LED color
  Happy              Yellow
Sad                Blue
Angry              Red
Neutral            White
Surprise           Purple
Fear               Cyan
Disgust            Green
Hardware Requirements
- Arduino Uno or Arduino Nano
- RGB LED (common cathode)
- Three 220Ω resistors
- Jumper wires
- USB cable
- Computer with Python installed
- Webcam
Software Requirements
- Python 3.x
- OpenCV
- FER library
- TensorFlow (as required by the FER installation)
- pyserial
- Arduino IDE
Circuit Connections
For the common-cathode RGB LED described in the project:

  RGB LED connection     Arduino connection
  Red pin                PWM pin 9 through a 220Ω resistor
Green pin              PWM pin 10 through a 220Ω resistor
Blue pin               PWM pin 11 through a 220Ω resistor
Common cathode (GND)   Arduino GND

Check the pin layout of the specific RGB LED before wiring. Use a
resistor in series with each color channel.
Working Principle
1. The user sits or stands in front of the webcam.
2. The Python application captures video frames from the webcam.
3. OpenCV processes the frames, and the emotion recognition component
   predicts the facial expression.
4. The detected emotion is sent from Python to Arduino through serial
   communication (the project configuration uses COM6).
5. Arduino receives the emotion string and identifies the corresponding
   color mapping.
6. Arduino uses PWM signals on the RGB channels to display the selected
   color.
Serial port note: COM6 is the port specified in the project
description. It may differ on another computer. Update the Python
serial-port configuration to match the port assigned to your Arduino.

Applications
- Smart-home and mood-responsive room lighting
- Personalized lighting environments
- Mood-based therapy or relaxation rooms
- Child-care environments
- Assistive and human-computer interaction prototypes
Future Enhancements
- Add configurable emotion-to-color mappings.
- Improve recognition performance in different lighting conditions and
  face orientations.
- Add wireless communication for more flexible device placement.
- Extend the system to coordinate other smart-home devices, where
  appropriate.
