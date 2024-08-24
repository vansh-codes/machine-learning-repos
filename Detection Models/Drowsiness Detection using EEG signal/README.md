
**DROWSINESS DETECTION USING DEEP LEARNING**

**Goal**
-This project aims to implement a drowsiness detection system using deep learning techniques, comparing the performance of a convolutional neural network (CNN) with a Random Forest classifier for binary classification tasks.

**Dataset**
-The dataset for this project can be accessed from the following link: EEG Driver Drowsiness Dataset.

**Setup and Installation**
-Python Environment: Ensure Python 3.x is installed on your system.

**Libraries**: Install the necessary libraries using pip:
  -pip install tensorflow scikit-learn matplotlib
  
**Libraries used**
1.Numpy
2.Pandas
3.sklearn
4.Keras
5.Tensorflow
6.matplotlib

***Model Implementation***
**Model 1**
**Architecture Description:**
-Input Layer: Receives sequences of length 12 with one feature dimension.
-Convolutional Blocks: Four blocks, each with two convolutional layers followed by element-wise addition (residual connection). Filters increase progressively (32, 64, 128, 256), ReLU activation.
-Global Average Pooling Layer: GlobalAveragePooling1D layer computes the average of each feature map across all spatial locations.
-Dense Layers: Four Dense layers (128, 90, 64, 32 neurons) with ReLU activation.
-Output Layer: Single neuron with sigmoid activation for binary classification.
**Training Description:**
-Optimizer: Stochastic Gradient Descent (SGD) with learning rate 0.001 and momentum 0.9.
-Loss Function: Binary Crossentropy.
-Regularization: No explicit regularization mentioned.
-Normalization: No explicit normalization mentioned.
***Model 2***
**Architecture Description:**
-Input Layer: Receives sequences of length 12 with one feature dimension.
-Convolutional Blocks: Four blocks, each with two convolutional layers followed by element-wise addition (residual connection). Filters increase progressively (32, 64, 128, 256), ReLU activation.
-Max Pooling Layer: After the final convolutional block, MaxPooling1D layer with pool size 2 and stride 1 reduces spatial dimensions.
-Flatten Layer: Reshapes output of the last convolutional layer into a 1D vector.
-Global Average Pooling Layer: GlobalAveragePooling1D layer computes the average of each feature map across all spatial locations.
-Dense Layers: Four Dense layers (128, 90, 64, 32 neurons) with ReLU activation.
-Output Layer: Single neuron with sigmoid activation for binary classification.

**Training Description:**
-Optimizer: Stochastic Gradient Descent (SGD) with learning rate 0.001 and momentum 0.9.
-Loss Function: Binary Crossentropy.
-Regularization: Dropout used to prevent overfitting.
-Normalization: Batch Normalization stabilizes and accelerates training.


**Training and Evaluation**
-Data Splitting: The dataset was split into training and testing sets using an 80:20 ratio.
-Training: The CNN model was trained for 150 epochs with a batch size of 4.
-Evaluation Metrics: Accuracy was used as the evaluation metric for both models.

****Results****
To provide a conclusion based on the three models provided:

**Model 1:** This model consists of four convolutional blocks with residual connections, followed by global average pooling and dense layers. It employs convolutional layers to capture local patterns in the input sequences, while residual connections facilitate gradient flow and help in mitigating the vanishing gradient problem. The model architecture seems suitable for sequential data processing tasks, especially with its residual connections and global pooling layer.

**Model 2:** Unlike the first model, Model 2 employs a simpler architecture with convolutional layers followed by pooling and dense layers. It lacks residual connections and global pooling, which may limit its ability to capture long-range dependencies in sequential data. However, it may still perform adequately for simpler tasks or datasets with less complex patterns.

**Conclusion:**

Model 1 is the most comprehensive and robust among the two, due to the use of residual connections and global pooling.
Model 2, while simpler, may struggle with capturing complex patterns in sequential data compared to Model 1.
The choice of the best model depends on factors such as the complexity of the dataset, computational resources, and the specific requirements of the task at hand.

