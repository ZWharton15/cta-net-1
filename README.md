# CTA-Net
A repository for the code used to create and train the model defined in 'Coarse Temporal Attention Network (CTA-Net)' from WACV 2021 (See the ___Paper___ section). As this paper used datasets that were provided as individual .jpg frames or full length videos rather than short video sequences, the code to prepare the datasets used are also provided.
<kbd>![CTA-Net model diagram](https://github.com/ZWharton15/CTA-Net/blob/main/doc/Figure_1.JPG?raw=true)</kbd>

## Published Results
<kbd>![Drive&Act validation results](https://github.com/ZWharton15/CTA-Net/blob/main/doc/Table_1.JPG?raw=true)</kbd>
<kbd>![Distracted Driver validation results](https://github.com/ZWharton15/CTA-Net/blob/main/doc/Table_2.JPG?raw=true)</kbd>

## Data Visualisation
<kbd>![AFLW validation results](https://github.com/ZWharton15/CTA-Net/blob/main/doc/Figure_6.JPG?raw=true)</kbd>

## Paper
### Abstract
There is significant progress in recognizing traditional human activities from videos focusing on highly distinctive actions involving discriminative body movements, bodyobject and/or human-human interactions. Driver’s activities are different since they are executed by the same subject with similar body parts movements, resulting in subtle changes. To address this, we propose a novel framework by exploiting the spatiotemporal attention to model the subtle changes. Our model is named Coarse Temporal Attention Network (CTA-Net), in which coarse temporal branches are introduced in a trainable glimpse network. The goal is to allow the glimpse to capture high-level temporal relationships, such as ‘during’, ‘before’ and ‘after’ by focusing on a specific part of a video. These branches also respect the topology of the temporal dynamics in the video, ensuring that different branches learn meaningful spatial and temporal changes. The model then uses an innovative attention mechanism to generate high-level action specific contextual information for activity recognition by exploring the hidden states of an LSTM. The attention mechanism helps in learning to decide the importance of each hidden state for the recognition task by weighing them when constructing the representation of the video. Our approach is evaluated on four publicly accessible datasets and significantly outperforms the state-of-the-art by a considerable margin with only RGB video as input

## Implementation
### Python Modules
All required imports can be install by running:
```
pip install -r requirements.txt
```
This will install:
* Numpy
* OpenCV
* Tensorflow 1.13.1
* Keras 2.2.4

### Datasets
3 datasets were used. Drive & Act contains mutliple 30 minute vidoes which we split into 30 frame sequences for the purpose of feeding to the model. Both Distracted Driver datasets were provided in image file format. We manually reconstructed these frames into 30 (V1) and 20 (V2) frame sequences per participant activity.
1. Distracted Driver V1
2. Distracted Driver V2
3. Drive & Act

### Data Structure
The input data is a directory tree with the following structure:
```
- Dataset
 - Class Name 1
  - sequence1.mp4
  - sequence2.mp4
  - sequence3.mp4
  - ...
 - Class Name 2
  - sequence1.mp4
  - sequence2.mp4
  - sequence3.mp4
  - ...
```
### Running the Model
To compile and train the model, simply run the following command:
```
python train_cta-net.py
```

## Citation
```
Wharton, Z., Behera, A., Liu, Y. and Bessis, N., 2021. Coarse Temporal Attention Network (CTA-Net) for Driver's Activity Recognition. In: Proceedings of the IEEE/CVF Winter Conference on Applications of Computer Vision. 5-9 Jan 2021.
```
