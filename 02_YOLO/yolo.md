
<br>
<br>

# `# 1. Using YOLO from ultralytics `


<br>
<br>


```python

from ultralytics import YOLO

# Load YOLOv8 model
# You can choose different sizes: yolov8n.pt, yolov8s.pt, yolov8m.pt, etc.
model = YOLO('yolov8n.pt') 

results = model(frame) # frame from openCV 

  for detection in results[0].boxes:
        x1, y1, x2, y2 = detection.xyxy[0]  # Bounding box in (x1, y1, x2, y2) format
        confi = detection.conf[0]
        class_id = int(detection.cls[0])  # Convert class_id to an integer
        class_name = results[0].names[class_id]  # Now use class_id to get the class name
```

<br>
<br>

# `# 2. What we get from result : `


<br>
<br>

### Key Attributes and Methods of `results` in YOLO

1. **`results.boxes`**: Contains information about detected bounding boxes, including:
   - **`.xyxy`**: Coordinates of bounding boxes in `(x1, y1, x2, y2)` format.
   - **`.xywh`**: Coordinates of bounding boxes in `(center_x, center_y, width, height)` format.
   - **`.conf`**: Confidence scores for each detection.
   - **`.cls`**: Class IDs for each detection (maps to classes like person, car, etc.).




<br>
<br>

# `# 2. Train on Custom data: `


<br>
<br>



### Step 8: Training YOLO on Custom Data (Optional)
To train YOLO on a custom dataset:
1. **Prepare Dataset**: Organize images and labels in YOLO format. The directory structure is typically:
   ```
   ├── dataset
       ├── images
       ├── labels
   ```
   Each label file contains bounding box annotations with class IDs.

2. **Create a Data YAML File**: Define the path to images and classes in a YAML file.

3. **Train the Model**: Start training using the `train` method.

   ```python
   model.train(data='path/to/data.yaml', epochs=100, imgsz=640)
   ```

### Step 9: Save and Export the Model
After training or if you want to deploy your model, you can save and export it.

```python
model.export(format='onnx')  
```

