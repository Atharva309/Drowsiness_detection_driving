# Drowsiness Detection for Driving

This project is aimed at detecting driver drowsiness by analyzing eye states (open/closed) and yawns using deep learning techniques. The model is based on YOLOv5 and performs both image classification and object detection to recognize drowsiness signs in real time.

## Project Overview

Drowsy driving is a significant factor in road accidents worldwide. Early detection of drowsiness can save lives by alerting the driver and taking appropriate preventive measures. This system identifies drowsiness by monitoring:

1. **Eye State**: Whether the driver’s eyes are open or closed.
2. **Yawns**: Detecting when the driver is yawning, which is a strong indicator of tiredness.

## Dataset

This project utilizes two key datasets:

- **[Eye Detection Dataset](https://universe.roboflow.com/ai-project-t1xm8/eye-detector-01g2k)**: Used for detecting eyes in different states (open or closed) with YOLOv5.
- **[Eye and Yawn Classification Dataset](https://www.kaggle.com/datasets/dheerajperumandla/drowsiness-dataset)**: Used for classifying eye states and detecting yawns for drowsiness analysis.

## How the Project Works

1. **Eye State Classification**:
   - The model classifies images as either "eyes open" or "eyes closed" to determine drowsiness.
   - This classification is crucial as prolonged eye closure is a common sign of drowsiness.
   - Two approaches were used for detecting eyes:
     - **Eye Detection Dataset**: A bounding box is drawn around the eyes using a specialized eye detection dataset.
     - **Face Detection Dataset**: A bounding box is drawn around the entire face, and the eyes are detected within that region.
2. **Yawn Detection**:
   - The YOLOv5 model is used to detect yawns, which often occur when a person is drowsy.
   - The model continuously monitors the driver's face for signs of yawning.
3. **Drowsiness Decision Logic**:
   - The system integrates the results from both eye state classification and yawn detection to make a final drowsiness prediction.
   - If the eyes are closed for a specified period or if yawns are detected frequently, the system triggers an alert.


## YOLOv5 for Drowsiness Detection

YOLOv5 (You Only Look Once) is a real-time object detection system. In this project, YOLOv5 is used for:
- **Eye Detection**: Identifying the position and state of the eyes (open or closed).
- **Yawn Detection**: Detecting when the driver is yawning using bounding boxes around the mouth region.
The model is trained to be lightweight and efficient, making it suitable for real-time deployment in vehicle systems.

## Example Outputs

Here are some sample outputs showing the detection of drowsiness indicators:

### using eye detection
<p align="center">
<img src="images_outputs/Screenshot 2023-05-21 at 11.56.28 PM.png "Title="using eye detection"width="800" height="auto" />
</p>
<p align="center">
<img src="images_outputs/Screenshot 2023-05-21 at 11.56.59 PM.png"Title="using eye detection"width="800" height="auto" />
</p>

### using eye classification with face detection bounding box
<p align="center">
<img src="images_outputs/Screenshot 2023-05-21 at 11.56.40 PM.png "Title= "using eye detection"width="800" height="auto" />
</p>

## using eye classification with eye detection bounding box
<p align="center">
<img src="images_outputs/Screenshot 2023-05-21 at 11.56.49 PM.png" Title ="using eye detection" width="800" height="auto" />
</p>


## Conclusion

This project highlights the application of deep learning for enhancing road safety. By integrating eye state and yawn detection, the system provides a robust method for detecting driver drowsiness and issuing timely alerts. Future improvements could involve adding more features like head pose estimation and facial landmark detection for even greater accuracy.

## References

- YOLOv5: [Ultralytics YOLOv5](https://github.com/ultralytics/yolov5)
- Dataset 1: [Eye Detection](https://universe.roboflow.com/ai-project-t1xm8/eye-detector-01g2k)
- Dataset 2: [Eye and Yawn Classification](https://www.kaggle.com/datasets/dheerajperumandla/drowsiness-dataset)


