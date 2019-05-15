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

## Model Training at Levels
- MobileNet and MobileNetV2 for quick models
- Models stored to Google Cloud Platform
- Iteration on models with Data Augmentation, Dropouts and Maxpooling
- Building new CNN based models from scratch
- 

## Evaluation Metric
- Using a confusion matrix to, in order of priority:
    - Maximize True Positives
    - Minimize False Negatives 
    - Minimize False Positives 

## Making Predictions
  - Making predictions at 3 levels: 3, 5, 7:
    1) For each 400 x 400 window and level 3, get a prediction
    2) Retrive the same region at higher 5 and 7 zoom levels with 800x800 and 50x50 windows respectively 
    3) Get predictions for each of those images 
  - Once all the predictions are in, choose majority prediction weighted equally. 
  - Get coordinates of all 400 x 400 window slides that were voted a tumors at level 3 resolutions and generate heat map. 
  
  
  
  
