Object Navigation App for Blind Persons

An Android-based assistive navigation system for visually impaired users.
The app uses real-time object detection and depth estimation to guide the user safely through their environment using audio and vibration feedback.

Features

Real-time object detection using YOLOv8n (TFLite optimized for mobile).

Depth estimation using MiDaS (TFLite small model) for obstacle distance calculation.

Audio feedback via Text-to-Speech (TTS) announcing objects and their distance.

Haptic feedback using vibrations for nearby obstacles.

Accessible UI designed for visually impaired users.

Configurable settings:

Object categories to detect

Volume and speech speed

Sensitivity (distance thresholds)

Architecture
Camera → YOLOv8 Object Detection → MiDaS Depth Estimation → ViewModel → Audio + Vibration Feedback → User


Camera: Captures real-time frames.

YOLOv8: Detects objects in the environment.

MiDaS: Calculates depth to each detected object.

ViewModel: Combines object info + depth → generates feedback.

Audio/Vibration: Guides the user safely.


(Replace the URL with your diagram if needed)

Installation

Clone the repository:

git clone https://github.com/gobinda789/object_navigation_for_blind_person_app.git


Open the project in Android Studio.

Place TFLite models in app/src/main/assets/:

yolov8n.tflite

midas_small.tflite

Add required dependencies in build.gradle:

implementation 'org.tensorflow:tensorflow-lite:2.13.0'
implementation 'org.tensorflow:tensorflow-lite-gpu:2.13.0'
implementation 'androidx.camera:camera-core:1.2.3'
implementation 'androidx.camera:camera-camera2:1.2.3'
implementation 'androidx.camera:camera-lifecycle:1.2.3'
implementation 'androidx.camera:camera-view:1.2.3'


Connect an Android device or emulator and run the app.

Usage

Open the app → Tap Start Detection.

Move around your environment.

Listen to audio feedback:

Example: “Chair ahead 2 meters”

Feel vibration feedback for close obstacles.

Adjust settings in the Settings screen:

Volume, speech speed, object sensitivity, and categories.

Testing

Test in different lighting conditions.

Test with multiple objects in the environment.

Ensure TTS announces correct object and distance.

Ensure vibration intensity corresponds to distance.

Future Enhancements

Support offline multi-language TTS.

Integrate wearable haptic feedback devices.

Improve path guidance for indoor navigation.

Add analytics to log detection accuracy and distances.

License

This project is licensed under the MIT License. See LICENSE
 for details.
