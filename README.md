# Real-Time Object Detection and Tracking with YOLOv5

This project implements real-time object detection using the YOLOv5 model, combined with object tracking to optimize performance. It detects humans, cars, and animals in video streams, switching between detection and tracking phases to improve efficiency and achieve real-time results.

## Features
- **Object Detection**: Detects objects using the YOLOv5n model, focusing on specific classes such as humans, cars, and animals.
- **Real-Time Object Tracking**: Utilizes OpenCV trackers (KCF or MOSSE) to track detected objects across frames, reducing the need for constant detection.
- **Stationary Object Handling**: Implements Intersection over Union (IoU) to skip tracking of stationary objects, improving processing speed.
- **Multi-threading**: Uses parallel processing to handle detection and tracking concurrently, enhancing performance.
- **FPS Calculation**: Displays the frames per second (FPS) on each processed frame for real-time monitoring.

## How It Works
1. **Input Video**: The system processes each frame of a video using OpenCV.
2. **YOLOv5 Detection**: Every few frames, the system runs object detection to identify the target objects.
3. **Object Tracking**: For the subsequent frames, the system tracks the detected objects using OpenCV trackers, reducing the computational cost of rerunning detection.
4. **Frame Rate Optimization**: The FPS is calculated and displayed on each frame to ensure the system operates in real-time.
5. **Handling Stationary Objects**: Objects that remain stationary across frames are skipped to optimize processing.

## Customization Options
- **YOLOv5 Model**: You can swap the YOLOv5n model with other variants depending on the desired speed and accuracy balance.
- **Tracker Type**: The project uses KCF or MOSSE trackers for real-time performance. You can switch to more accurate trackers like CSRT for higher accuracy, though with a performance trade-off.
- **Target Object Classes**: The system is designed to detect humans, cars, and animals. This can be modified based on the use case.

## Libraries and Dependencies
- **PyTorch**: For loading and running the YOLOv5 model.
- **OpenCV**: For video processing and object tracking.
- **Concurrent Futures**: For parallelizing detection and tracking tasks.

## Performance Considerations
- **Detection and Tracking Phases**: By alternating between detection and tracking, the system reduces computational load, ensuring real-time processing.
- **Skipping Stationary Objects**: Using IoU to determine if objects are stationary helps minimize unnecessary tracking, further optimizing performance.

## Use Cases
This system can be applied in various scenarios where real-time object detection and tracking are required, such as:
- Security and surveillance systems
- Wildlife monitoring
- Traffic management and vehicle detection
