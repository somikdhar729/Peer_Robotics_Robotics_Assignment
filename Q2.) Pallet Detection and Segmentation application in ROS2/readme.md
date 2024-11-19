### Dataset Download link: https://drive.google.com/file/d/1cj_pwME7QhgB5QS8V9EINhvWO3mPj16O/view?usp=sharing


# Dataset annotation and augmentation
* Initial annotation done using grounding DINO + SAM
  Reference Link: https://github.com/roboflow/notebooks/blob/main/notebooks/automated-dataset-annotation-and-evaluation-with-grounding-dino-and-sam.ipynb
* Final check done manually using Roboflow
* Data Augmentation and preprocessing steps
   - Image Resize: 640
   - 90° rotation
   - Saturation(0.25)
   - Brightness(0.15)
   - Noise(0.2)
  * Total images
    - Train: 1092
    - Valid: 104
    - Test: 51
 
# Object Detection and Semantic Segmentation
* Object Detection Model: YOLOv11n
* Semantic Segmentation Model: YOLOv11n-seg

# ROS2 Node Development
mkdir -p ~/ros2_ws/src
cd ~/ros2_ws/src

ros2 pkg create --build-type ament_python pallet_detection
cd pallet_detection

mkdir -p pallet_detection/models pallet_detection/scripts
touch pallet_detection/pallet_detector_node.py
mkdir launch
touch launch/pallet_detection.launch.py

cd ~/ros2_ws
colcon build --symlink-install
source install/setup.bash

ros2 launch pallet_detection pallet_detection.launch.py
