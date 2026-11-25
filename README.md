# Emotion-Aware Smart Home Lighting System

## 1. Introduction

The Emotion-Aware Smart Home Lighting System is an intelligent IoT application that combines Computer Vision, Machine Learning, and Embedded Systems to create a personalized lighting experience based on the user's emotional state.

The system captures real-time facial expressions using a webcam and analyzes them using a Python-based emotion detection model. Using OpenCV and the FER (Facial Emotion Recognition) library, the system identifies emotions such as happiness, sadness, anger, surprise, neutrality, fear, and disgust.

Once an emotion is detected, the Python application communicates with an Arduino microcontroller through serial communication. The Arduino controls an RGB LED by adjusting its color according to the detected emotion.

## 2. Problem Statement

Traditional lighting systems operate with fixed settings and require manual adjustments. They cannot respond dynamically to an individual's emotional state, limiting their ability to create a personalized and comfortable environment.

This project addresses this limitation by integrating facial emotion recognition with smart lighting technology. It automatically adjusts RGB LED colors based on detected facial expressions, creating an interactive and emotion-responsive environment.

## 3. Objectives

- **Real-Time Emotion Detection:** Capture facial expressions through a webcam and identify emotions using computer vision and machine learning techniques.
- **Serial Communication:** Transmit detected emotions from the Python application to the Arduino microcontroller.
- **Dynamic RGB Lighting:** Automatically adjust LED colors based on the detected emotional state.
- **Smart Home Integration:** Develop an interactive lighting system that demonstrates the integration of AI, IoT, and embedded systems.

## 4. Proposed System

The proposed system consists of two major modules:

### A. Emotion Detection Module (Python)

- Captures live video frames using a webcam.
- Processes facial images using OpenCV.
- Uses the FER library and deep-learning-based emotion recognition to classify facial expressions.
- Identifies the dominant emotion.
- Sends the detected emotion to Arduino through serial communication.

### B. Lighting Control Module (Arduino)

- Receives emotion information from the Python application.
- Maps each detected emotion to a predefined RGB color.
- Controls RGB LED channels using Pulse Width Modulation (PWM).
- Changes the lighting color according to the detected emotion.

## 5. System Architecture

The system follows the workflow below:

1. Webcam captures the user's facial expressions.
2. Python processes video frames using OpenCV.
3. FER identifies the user's facial emotion.
4. The detected emotion is transmitted to Arduino through serial communication.
5. Arduino processes the received emotion.
6. RGB LED changes its color according to the predefined emotion mapping.

### Architecture Flow

```text
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
       RGB LED
```

## 6. Emotion-to-Color Mapping

| Detected Emotion | LED Color |
|---|---|
| Happy | Yellow |
| Sad | Blue |
| Angry | Red |
| Neutral | White |
| Surprise | Purple |
| Fear | Cyan |
| Disgust | Green |

## 7. Hardware Requirements

- Arduino Uno / Arduino Nano
- RGB LED (Common Cathode)
- 220Ω Resistors (3 units)
- Jumper Wires
- USB Cable
- Computer with Python installed
- Webcam

## 8. Software Requirements

- Python 3.x
- OpenCV
- FER Library
- TensorFlow
- Arduino IDE
- PySerial (Serial Communication Library)

## 9. Circuit Connections

| RGB LED Pin | Arduino Pin |
|---|---|
| Red | PWM Pin 9 (through 220Ω resistor) |
| Green | PWM Pin 10 (through 220Ω resistor) |
| Blue | PWM Pin 11 (through 220Ω resistor) |
| Common Cathode | GND |

## 10. Working Principle

1. The user stands in front of the webcam.
2. Python captures live video frames.
3. OpenCV processes the frames and detects the face.
4. The FER model predicts the user's facial emotion.
5. The detected emotion is transmitted to Arduino through the configured serial port (COM6).
6. Arduino receives and matches the emotion string.
7. The RGB LED glows with the corresponding color.

## 11. Applications

- Smart Home Automation
- Mood-Based Lighting Systems
- Personalized Lighting Environments
- Child Care Environments
- Assistive Technology
- Human-Computer Interaction

## 12. Future Enhancements

- Improve emotion recognition accuracy under different lighting conditions.
- Integrate wireless communication for remote lighting control.
- Extend the system to control additional smart home devices.
- Introduce customizable emotion-to-color mapping.
- Integrate additional IoT features for intelligent home automation.

## 13. Limitations

Emotion recognition may be affected by lighting conditions, camera quality, face orientation, and facial occlusion. Detected facial expressions are estimates and may not always represent a person's actual emotional state.

## 14. Conclusion

The Emotion-Aware Smart Home Lighting System demonstrates the practical integration of Artificial Intelligence, Computer Vision, Machine Learning, and IoT. By detecting facial expressions and controlling RGB lighting through Arduino, the system creates an interactive and personalized lighting environment.

This project highlights the potential of AI-driven smart home applications in improving human-computer interaction and developing adaptive living environments.

## 15. Technologies Used

- **Programming Language:** Python
- **Computer Vision:** OpenCV
- **Machine Learning:** Facial Emotion Recognition (FER)
- **Hardware:** Arduino Uno / Nano, RGB LED
- **Communication:** Serial Communication (PySerial)
- **Development Environment:** Arduino IDE, Python IDE
