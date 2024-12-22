# Mars Rocks Detection Project

This repository contains the resources for detecting Mars rocks using YOLOv8 integrated with ROS2 nodes. It includes trained models, Python scripts for different ROS2 nodes, evaluation metrics, and visualizations.


## Repository Structure

mars-rocks-detection/
├── models/
│   ├── yolov8n.pt              # YOLOv8 nano model checkpoint
│   ├── best.pt                 # Best-performing model checkpoint
│   ├── last.pt                 # Last saved model checkpoint
├── nodes/
│   ├── input_node.py           # ROS2 node for publishing images
│   ├── detection_node.py       # ROS2 node for detecting objects using YOLOv8
│   ├── turtlesim_node.py       # ROS2 node for controlling Turtlesim based on detections
├── configs/
│   ├── args.yaml               # YOLOv8 training configuration file
├── metrics/
│   ├── confusion_matrix_normalized.png # Normalized confusion matrix
│   ├── confusion_matrix.png            # Confusion matrix
│   ├── F1_curve.png                    # F1-Confidence curve
│   ├── P_curve.png                     # Precision-Confidence curve
│   ├── PR_curve.png                    # Precision-Recall curve
│   ├── R_curve.png                     # Recall-Confidence curve
│   ├── results.png                     # Training and validation loss/metrics trends
│   ├── results.csv                     # CSV file with detailed results
├── visualizations/
│   ├── labels_correlogram.jpg          # Correlogram of labels
│   ├── labels.jpg                      # Labels overview
│   ├── train_batch0.jpeg               # Training batch visualization
│   ├── train_batch1.jpeg
│   ├── train_batch2.jpeg
│   ├── train_batch1125.jpeg
│   ├── train_batch1126.jpeg
│   ├── train_batch1127.jpeg
│   ├── val_batch0_labels.jpeg          # Validation batch with ground truth labels
│   ├── val_batch0_pred.jpeg            # Validation batch with predictions
├── README.md


	2.	Set Up Environment:
	•	Install ROS2: [ROS2 Installation Guide](https://docs.ros.org/en/rolling/Installation.html)
	•	Install Python dependencies:
      pip install -r requirements.txt
  •	Install YOLOv8:
      pip install ultralytics

  3.	Run the ROS2 Nodes:
	•	Start the input node:
      ros2 run nodes input_node
	•	Start the detection node:
      ros2 run nodes detection_node
	•	Start the turtlesim node:
      ros2 run nodes turtlesim_node


Usage Instructions
	1.	Training the Model:
	•	Modify args.yaml for your dataset and training configuration.
	•	Train the model:
     yolo task=detect mode=train data=<data.yaml> model=yolov8n.pt epochs=85
