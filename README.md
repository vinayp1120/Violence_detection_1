# Violence_detection_1

The prosed model architecture is made up of VGG16+CNN+LSTM for detecting the violence behaviour in the video source or cams
Model Architecture Design
A. Frame-Level Feature Extraction with VGG16
VGG16 Backbone: Use the pre-trained VGG16 model as a feature extractor. For each frame of the video:
Load the VGG16 model with weights pre-trained on ImageNet.
Remove the fully connected layers (keeping only convolutional layers).
Extract feature maps from each frame.
Preprocessing for VGG16: Resize each frame to VGG16's input size (224x224) and normalize the pixel values.
B. CNN for Local Spatial Features
Use CNN layers after VGG16 to refine the extracted features further, capturing spatial dependencies across frames.
These CNN layers can help improve spatial pattern recognition (for example, detecting objects or violent actions in the frame).
C. LSTM for Temporal Dependencies
Use LSTM (Long Short-Term Memory) layers to process the sequence of frames. LSTMs are suited for temporal sequence data and can capture time-dependent changes (e.g., sudden movements that may indicate violent actions).
Feed the sequence of CNN-extracted features (from each frame) into the LSTM, which will learn temporal patterns and dependencies.
D. Fully Connected Layers and Classification
After the LSTM layer, use one or more fully connected layers.
Apply a final softmax layer for binary classification (violent or non-violent).
