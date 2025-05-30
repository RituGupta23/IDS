# Intrusion Detection System using Deep Learning

This project implements an Intrusion Detection System (IDS) using deep learning models to detect network intrusions in the UNSW-NB15 dataset. The system employs three different neural network architectures to classify network traffic as either normal or malicious.

## Dataset

The system uses the UNSW-NB15 dataset, which contains modern normal and attack network traffic. The dataset includes:
- Training set: 175,341 samples
- Testing set: 82,332 samples
- 45 features per sample
- Binary classification (Normal vs Attack)

## Models

### 1. MLP Classifier
A simple Multi-Layer Perceptron with the following architecture:
- Input layer → 128 neurons → 64 neurons → Output layer (2 classes)
- ReLU activation functions
- Cross-entropy loss
- Adam optimizer

### 2. 1D ResNet Classifier
A Residual Neural Network adapted for 1D data:
- Basic blocks with convolutional layers
- Batch normalization
- Residual connections
- Adaptive average pooling
- Two main blocks (32 → 64 channels)

### 3. SA-ResNet Classifier
An advanced model combining ResNet with Spatial Attention:
- Three main blocks (32 → 64 → 128 channels)
- Spatial attention mechanism
- Dropout (0.3) for regularization
- Adaptive average pooling
- Final fully connected layer

## Implementation Details

### Data Preprocessing
1. Drop irrelevant columns (id, proto, service, state, attack_cat)
2. Extract labels and features
3. Normalize features using StandardScaler
4. Convert to PyTorch tensors
5. Create DataLoaders with batch size 128

### Training Process
- 50 epochs for each model
- Cross-entropy loss function
- Adam optimizer with learning rate 0.001
- Batch size: 128
- GPU acceleration when available

### Evaluation Metrics
- Confusion Matrix
- Classification Report (Precision, Recall, F1-score)
- ROC Curve
- Threshold Analysis (0.1 to 0.9)

## Requirements

- Python
- PyTorch
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn

## Usage

1. Install dependencies:
```bash
pip install torch pandas numpy scikit-learn matplotlib seaborn
```

2. Prepare the dataset:
   - Download UNSW-NB15 dataset
   - Place training and testing CSV files in the project directory

3. Run the notebook:
   - Open `Intrusion_Detection.ipynb`
   - Execute cells sequentially
   - View results and visualizations

## Future Improvements

1. **Model Enhancements**:
   - Experiment with different architectures
   - Implement ensemble methods
   - Add more attention mechanisms

2. **Feature Engineering**:
   - Explore feature importance
   - Add new relevant features
   - Implement feature selection

3. **Training Optimization**:
   - Implement learning rate scheduling
   - Add early stopping
   - Experiment with different optimizers

4. **Deployment**:
   - Create API for real-time detection
   - Implement model serving
   - Add monitoring and logging
   
## Acknowledgments

- UNSW-NB15 dataset creators
- PyTorch team
- Open source community
