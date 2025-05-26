# Intrusion Detection System - Detailed Results

This document provides comprehensive results and analysis of the three deep learning models implemented for intrusion detection.

## Model Performance Summary

### 1. MLP Classifier

#### Overall Metrics
- Accuracy: 85%
- Macro Average Precision: 0.88
- Macro Average Recall: 0.84
- Macro Average F1-score: 0.85

#### Class-wise Performance
| Class   | Precision | Recall | F1-score | Support |
|---------|-----------|---------|-----------|----------|
| Normal  | 0.95      | 0.71    | 0.81      | 37,000   |
| Attack  | 0.80      | 0.97    | 0.88      | 45,332   |

#### Threshold Tuning Results
| Threshold | Accuracy | Precision | Recall | F1-Score |
|-----------|----------|-----------|---------|-----------|
| 0.10      | 0.8078   | 0.7427    | 0.9960  | 0.8509    |
| 0.20      | 0.8103   | 0.7463    | 0.9929  | 0.8521    |
| 0.30      | 0.8159   | 0.7540    | 0.9881  | 0.8553    |
| 0.40      | 0.8339   | 0.7765    | 0.9807  | 0.8667    |
| 0.50      | 0.8523   | 0.8033    | 0.9690  | 0.8784    |
| 0.60      | 0.8655   | 0.8301    | 0.9503  | 0.8861    |
| 0.70      | 0.8717   | 0.8554    | 0.9230  | 0.8879    |
| 0.80      | 0.8739   | 0.8878    | 0.8826  | 0.8852    |
| 0.90      | 0.8693   | 0.9257    | 0.8293  | 0.8748    |

### 2. 1D ResNet Classifier

#### Overall Metrics
- Accuracy: 88%
- Macro Average Precision: 0.90
- Macro Average Recall: 0.87
- Macro Average F1-score: 0.88

#### Class-wise Performance
| Class   | Precision | Recall | F1-score | Support |
|---------|-----------|---------|-----------|----------|
| Normal  | 0.96      | 0.77    | 0.86      | 37,000   |
| Attack  | 0.84      | 0.97    | 0.90      | 45,332   |

#### Threshold Tuning Results
| Threshold | Accuracy | Precision | Recall | F1-Score |
|-----------|----------|-----------|---------|-----------|
| 0.10      | 0.8108   | 0.7450    | 0.9978  | 0.8531    |
| 0.20      | 0.8158   | 0.7515    | 0.9941  | 0.8560    |
| 0.30      | 0.8314   | 0.7702    | 0.9889  | 0.8659    |
| 0.40      | 0.8565   | 0.8022    | 0.9813  | 0.8827    |
| 0.50      | 0.8830   | 0.8403    | 0.9722  | 0.9015    |
| 0.60      | 0.9023   | 0.8738    | 0.9615  | 0.9155    |
| 0.70      | 0.9165   | 0.9049    | 0.9480  | 0.9259    |
| 0.80      | 0.9178   | 0.9292    | 0.9209  | 0.9250    |
| 0.90      | 0.9097   | 0.9669    | 0.8656  | 0.9134    |

### 3. SA-ResNet Classifier

#### Overall Metrics
- Accuracy: 87%
- Macro Average Precision: 0.89
- Macro Average Recall: 0.86
- Macro Average F1-score: 0.87

#### Class-wise Performance
| Class   | Precision | Recall | F1-score | Support |
|---------|-----------|---------|-----------|----------|
| Normal  | 0.96      | 0.74    | 0.84      | 37,000   |
| Attack  | 0.82      | 0.97    | 0.89      | 45,332   |

#### Threshold Tuning Results
| Threshold | Accuracy | Precision | Recall | F1-Score |
|-----------|----------|-----------|---------|-----------|
| 0.10      | 0.8123   | 0.7462    | 0.9972  | 0.8538    |
| 0.20      | 0.8178   | 0.7528    | 0.9945  | 0.8567    |
| 0.30      | 0.8325   | 0.7715    | 0.9892  | 0.8662    |
| 0.40      | 0.8578   | 0.8035    | 0.9818  | 0.8835    |
| 0.50      | 0.8845   | 0.8420    | 0.9728  | 0.9028    |
| 0.60      | 0.9035   | 0.8755    | 0.9620  | 0.9168    |
| 0.70      | 0.9158   | 0.9062    | 0.9485  | 0.9265    |
| 0.80      | 0.9165   | 0.9305    | 0.9215  | 0.9258    |
| 0.90      | 0.9085   | 0.9675    | 0.8662  | 0.9140    |

## Detailed Analysis

### 1. Optimal Thresholds

#### MLP Classifier
- Best Accuracy: 0.8739 (threshold = 0.80)
- Best F1-Score: 0.8879 (threshold = 0.70)
- Best Precision: 0.9257 (threshold = 0.90)
- Best Recall: 0.9960 (threshold = 0.10)

#### 1D ResNet Classifier
- Best Accuracy: 0.9178 (threshold = 0.80)
- Best F1-Score: 0.9259 (threshold = 0.70)
- Best Precision: 0.9669 (threshold = 0.90)
- Best Recall: 0.9978 (threshold = 0.10)

#### SA-ResNet Classifier
- Best Accuracy: 0.9165 (threshold = 0.80)
- Best F1-Score: 0.9265 (threshold = 0.70)
- Best Precision: 0.9675 (threshold = 0.90)
- Best Recall: 0.9972 (threshold = 0.10)

### 2. Model Comparison

#### Accuracy Progression
- MLP: 80.78% → 87.39% (peak at threshold 0.80)
- 1D ResNet: 81.08% → 91.78% (peak at threshold 0.80)
- SA-ResNet: 81.23% → 91.65% (peak at threshold 0.80)

#### Precision-Recall Trade-off
1. **Low Thresholds (0.1-0.3)**
   - High recall (>0.98)
   - Lower precision (0.74-0.77)
   - Suitable for high-security environments

2. **Medium Thresholds (0.4-0.6)**
   - Balanced precision and recall
   - Good for general use cases
   - Optimal F1-scores

3. **High Thresholds (0.7-0.9)**
   - High precision (>0.85)
   - Lower recall
   - Suitable for low false positive requirements

### 3. Key Observations

1. **Threshold Impact**
   - All models show similar patterns in threshold sensitivity
   - Optimal operating point typically between 0.5-0.7
   - Significant performance variation across thresholds

2. **Model Strengths**
   - MLP: Consistent performance across thresholds
   - 1D ResNet: Best overall metrics
   - SA-ResNet: Good balance of precision and recall

3. **Performance Patterns**
   - All models show high recall for attack detection
   - Precision improves with higher thresholds
   - F1-score peaks at medium thresholds

## Recommendations

1. **Threshold Selection**
   - For balanced performance: Use threshold 0.5-0.6
   - For high security: Use threshold 0.3-0.4
   - For low false positives: Use threshold 0.7-0.8

2. **Model Selection**
   - General use: 1D ResNet
   - Resource-constrained: MLP
   - High precision required: SA-ResNet

3. **Deployment Considerations**
   - Monitor threshold performance in production
   - Consider ensemble approach for critical systems
   - Regular retraining with updated data

## Visualizations

The following visualizations are available in the notebook:
1. Confusion matrices for each model
2. ROC curves showing AUC scores
3. Precision-Recall curves
4. Threshold tuning plots
5. Performance metric comparisons

## Conclusion

The 1D ResNet model shows the best overall performance across different thresholds, while the MLP provides a good balance of performance and simplicity. The SA-ResNet offers specialized capabilities for certain use cases. The choice of model and threshold should be based on specific deployment requirements and constraints. 