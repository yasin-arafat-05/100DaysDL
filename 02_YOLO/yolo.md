
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
   - **`.confidence`**: Confidence scores for each detection.
   - **`.class_id`**: Class IDs for each detection (maps to classes like person, car, etc.).
   - **`.data`**: Raw tensor data for boxes, including coordinates, confidence, and class IDs.

2. **`results.names`**: A dictionary mapping class IDs to class names (e.g., `{0: 'person', 1: 'bicycle', ...}`).

3. **`results.orig_img`**: The original input image as a NumPy array, which can be useful for custom visualization or processing.

4. **`results.plot()`**: Renders the detections on the image, returning an annotated image with bounding boxes and labels drawn.

5. **`results.masks`** (if applicable): If segmentation is enabled, this attribute contains the masks for each object, allowing pixel-level segmentation.

6. **`results.keypoints`** (if applicable): For keypoint detection models (e.g., human pose estimation), this contains coordinates for keypoints (like joints on a human body).

### Example Usage of Each Attribute

Here's how to access these attributes in practice:

```python
# Run inference on an image
results = model('path/to/image.jpg')

# 1. Access Bounding Boxes
for detection in results[0].boxes:  
    x1, y1, x2, y2 = detection.xyxy[0]  t
    conf = detection.confidence[0]       
    class_id = int(detection.class_id[0])  
    class_name = results.names[class_id]  


# 2. Access Class Names
print("Class Names:", results.names)  # Dictionary of class names

# 3. Plot and Display Image with Detections
annotated_image = results[0].plot()
cv2.imshow("YOLO Detections", annotated_image)
cv2.waitKey(0)

# 4. Masks (if segmentation model is used)
if results[0].masks:
    for mask in results[0].masks:
        print(mask)

# 5. Keypoints (if keypoint model is used)
if results[0].keypoints:
    for keypoint in results[0].keypoints:
        print(keypoint)  
```

### Summary of Common Attributes:
| Attribute          | Description                                                                                  |
|--------------------|----------------------------------------------------------------------------------------------|
| `results.boxes`    | Bounding boxes with coordinates, class IDs, and confidence scores.                           |
| `results.names`    | Dictionary mapping class IDs to class names.                                                 |
| `results.orig_img` | Original input image in NumPy array format.                                                  |
| `results.plot()`   | Returns annotated image with bounding boxes and labels.                                      |
| `results.masks`    | Masks for each object (only for segmentation models).                                        |
| `results.keypoints`| Coordinates for detected keypoints (only for keypoint detection models).                     |



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

