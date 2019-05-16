# Deep Learning - CAMELYON 16 Challenge

### Collaborators:
**Cynthia Clement** - cfc2134   
**Vineet Aguiar** - vaa2114

## Overall Approach
- Understanding starter code
- Understanding features of the data:
- Understanding Sliding window technique

## Data Extraction
- Level selection
- Sliding widow technique and window size
- Separating tumor/non tumor images - num of tumor pixels & % tumor 
- Sampling of Non-tumor images
- Image resolution - Context vs Detail
- Separting Training, Validation and Test Data
- Naming convention for stored images

#### Running data extractor by level
New image files store with the following naming convention:
```
level_<level_num>_<window_x_coord>_<window_y_coord>_<window_size>_<filename>
```

**Sliding Window Size Calculations**

| Level  |   Zoom Factor |  Window Size | 
|---|---|---|
|  7 |  1x |  50  |
|  6 |  2x |   |
|   5|  4x |  400 |
|   4|  8x |   |
|   3|  16x | 800 |
|   2| 32x |   |
|   1|  64x |   3200|
|   0|  128x |   |

## Model Training at Levels
- MobileNet and MobileNetV2 for quick models
- Models stored to Google Cloud Platform
- Iteration on models with Data Augmentation, Dropouts and Maxpooling
- Building new CNN based models from scratch
- Evaluted with our  metric

## Evaluation Metric
- Using a confusion matrix to, in order of priority:
    - Maximize True Positives (Tumor areas predicted correctly)
    - Minimize False Negatives (Tumor areas missed by our model)
    - Minimize False Positives (Non tumor areas predicted as tumors)

## Making Predictions
  - Making predictions at 3 levels: 3, 5, 7:
    1) For each 400 x 400 window and level 3, get a prediction
    2) Retrive the same region at higher 5 and 7 zoom levels with 800x800 and 50x50 windows respectively 
    3) Get predictions for each of those images 
  - Once all the predictions are in, choose majority prediction weighted equally. 
  - Get coordinates of all 400 x 400 window slides that were voted a tumors at level 3 resolutions and generate heat map. 
  
  
  
  
