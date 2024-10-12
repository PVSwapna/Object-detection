
# YOLO Object Detection with OpenCV

This project demonstrates how to perform object detection using YOLOv3 and OpenCV in real-time with a connected camera.

## Requirements

- Python 3.x
- OpenCV
- NumPy
- Pre-trained YOLOv3 model files (`yolov3.cfg`, `yolov3.weights`, and `yolov3.txt`)

### Installation

Install the required Python libraries:
```bash
pip install opencv-python numpy
```

## YOLO Model Files

Make sure to download the following YOLOv3 files:
1. `yolov3.cfg` - YOLOv3 configuration file.
2. `yolov3.weights` - Pre-trained YOLOv3 weights.
3. `yolov3.txt` - List of class names YOLOv3 can detect.

You can download these from the official YOLO website or GitHub repositories.

## Usage

### Running the Script

Once you have the required files, you can run the script as follows:

```bash
python realtime.py
```

### Functionality

- The script opens the default camera (0). If you have multiple cameras, you can change the camera index.
- It reads the pre-trained YOLO model and class labels.
- Captures frames from the camera in real time.
- For each frame, it:
  1. Prepares the image as a blob for YOLO.
  2. Passes the blob through the network.
  3. Processes the output to detect objects.
  4. Draws bounding boxes around detected objects.
  5. Displays the frame with detected objects.

### Key Functions

#### `get_output_layers(net)`
Retrieves the output layers for YOLO from the network.

#### `draw_prediction(img, class_id, confidence, x, y, x_plus_w, y_plus_h)`
Draws the bounding box and label on the image for the detected object.

## Parameters

- `config_path` - Path to the YOLO configuration file.
- `weights_path` - Path to the YOLO weights file.
- `classes_path` - Path to the file containing class names.

## Example Output

For each frame captured by the camera, the script will output the frame with detected objects highlighted by bounding boxes and their corresponding labels.

## Adjustments

- **Confidence Threshold**: You can change the confidence threshold for object detection by modifying the `conf_threshold` variable (default is 0.5).
- **NMS Threshold**: Adjust the non-max suppression threshold (`nms_threshold`, default is 0.4) to refine detection.

### Closing the Application

Press `q` to stop the object detection and close the camera feed.

## License

This project is open-source and can be freely used or modified.
