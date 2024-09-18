### VGG16-Based Binary Classification Model

This repository contains a binary classification model built using the VGG16 architecture pre-trained on ImageNet as the feature extractor. The model is implemented using TensorFlow's Functional API.

#### Model Architecture:
- **VGG16 Base**: We utilize the convolutional layers of VGG16 pre-trained on ImageNet, with the fully connected layers removed.
- **Frozen Layers**: All VGG16 layers are frozen to retain the pre-trained knowledge.
- **Custom Head**: The feature map from VGG16 is passed through:
  - A Flatten layer
  - Dense layer with 64 units and ReLU activation
  - Dropout layer for regularization
  - A final Dense layer with softmax activation for binary classification (2 output classes).

#### Key Features:
- **Pre-trained Weights**: Efficient feature extraction using VGG16 pre-trained on ImageNet.
- **Functional API**: Flexible model creation with TensorFlow/Keras Functional API.
- **Binary Classification**: Designed for tasks requiring two output classes.

#### Training Details:
- The model was trained for 10 epochs.
- Initial performance showed an accuracy of **78.92%** and a loss of **0.5467** in the first epoch.
- The final epoch achieved a training accuracy of **90.62%**, validation accuracy of **96.15%**, and validation loss of **0.0865**.
- Training encountered a warning regarding input data running out. This might require revisiting the dataset preparation process, possibly by applying the `.repeat()` function for sufficient data batches per epoch.

