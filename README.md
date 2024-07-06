# EEG-Controlled Prosthetic Hand

![EEG-Controlled Prosthetic Hand](GIF/gif.gif)

In this project, we developed a system that utilizes EEG data to accurately classify motor actions as either grasp or release. The EEG signals are processed and fed into a Convolutional Neural Network (CNN) model designed to identify these specific motor events. Once the model predicts the action it is translated into physical movement of a prototype hand via an Arduino-controlled servo motor. This project demonstrates a low-cost, efficient approach to translating brain signals into physical movements, providing a potential pathway for developing advanced prosthetic devices that can respond to the user's neural commands with high precision.

## Table of Contents
- [Workflow](#workflow)
- [Components](#components)
- [Hardware Setup](#hardware-setup)
- [Software Setup](#software-setup)
- [Troubleshooting](#troubleshooting)
- [Visualization](#visualization)
- [Conclusion](#conclusion)

## Workflow

1. **EEG Data Processing**: EEG data is processed using wavelet denoising and band-pass filtration.
2. **Prediction with CNN**: The preprocessed EEG data is fed into the CNN model, which predicts whether the action is a grasp or release.
3. **Serial Communication**: The prediction is written to a CSV file, read by the Python script, and sent to the Arduino via serial communication.
4. **Servo Motor Control**: The Arduino receives the command and adjusts the servo motor accordingly. A '0' command rotates the servo to release the fingers, and a '1' command rotates it to grasp.
5. **Hand Movement**: The servo motor's movement pulls or releases the threads in the hand prototype, resulting in realistic finger movements.

## Components

- **Servo Motor**
- **Arduino Uno**
- **Jumper Wires, battery**
- **Cartoon Hand Prototype**: Constructed using straws to represent bones and threads connected to the fingertips.

## Hardware Setup

### Wiring Diagram
- **Servo Motor:**
  - Signal to Digital Pin 9
  - **VCC** and **Ground** of an external power source or battery.
### Power and Control

- **Arduino Power:**
  - Arduino Uno powered via USB.


## Software Setup

### Prerequisites

- **Python** 
- **Arduino IDE**

### Steps to Install and Run

1. Clone the Repository
2. Unzip the project folder
2. Download the Dependencies
3. Connect all components as per the wiring diagram provided.
4. Upload the Arduino code (`Grasp_Release.ino`) to the Arduino board using the Arduino IDE.
5. Run the Serial Communication Script (`to_arduino.py`)
## Troubleshooting

- **Issue:** The first few values of the CSV are sent, then an error occurs.
  - **Solution:** The long cables and the servo motor's rotation can cause a drop in voltage, leading to data corruption. Ensure you connect the servo motor to an external suitable powerful power source or battery based on the datasheet of the used servo motor.

## Visualization
To visualize the EEG data before and after filtering, run the `EEG_visual.py` file found in the Data_filtering_visualization folder. This helps in understanding the preprocessing steps and ensuring the data quality.

## Conclusion
This project demonstrates a low-cost, efficient approach to translating brain signals into physical movements, providing a potential pathway for developing advanced prosthetic devices. By leveraging EEG and machine learning techniques, we aim to enhance the quality of life for individuals with motor impairments, offering them greater autonomy and functionality in their daily activities.
