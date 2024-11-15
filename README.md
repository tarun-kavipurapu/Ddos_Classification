# DDoS Traffic Classification

This project uses a Feedforward Neural Network (FNN) to classify network traffic as either regular or DDoS (Distributed Denial of Service) traffic. By training a model on a variety of traffic features, we aim to accurately identify potential DDoS traffic.

## Dataset

The dataset used for this project contains various network traffic parameters, which help in distinguishing between regular and DDoS traffic. The dataset is attached to this repository.

### Features Used for Classification

The following features were utilized to classify the traffic:

1. **switch** - Identifier for the switch.
2. **src** - Source address.
3. **dst** - Destination address.
4. **pktcount** - Packet count.
5. **bytecount** - Byte count.
6. **dur** - Duration of traffic.
7. **dur_nsec** - Duration in nanoseconds.
8. **tot_dur** - Total duration.
9. **flows** - Number of flows.
10. **packetins** - Packet-ins count.
11. **pktperflow** - Packets per flow.
12. **byteperflow** - Bytes per flow.
13. **pktrate** - Packet rate.
14. **Pairflow** - Paired flow information.
15. **Protocol** - Protocol used.
16. **port_no** - Port number.
17. **tx_bytes** - Transmitted bytes.
18. **rx_bytes** - Received bytes.
19. **tx_kbps** - Transmission rate in kbps.
20. **rx_kbps** - Reception rate in kbps.
21. **tot_kbps** - Total rate in kbps.

## Model Architecture

The model architecture is a simple feedforward neural network with the following structure:

1. **Input Layer**
   - **Type**: Dense
   - **Units**: 64
   - **Activation**: ReLU (Rectified Linear Unit)

2. **Hidden Layer 1**
   - **Type**: Dense
   - **Units**: 32
   - **Activation**: ReLU

3. **Output Layer**
   - **Type**: Dense
   - **Units**: 1
   - **Activation**: Sigmoid
   - **Output Dimension**: 1 (for binary classification)

### Compilation Parameters

- **Optimizer**: Adam
- **Loss Function**: Binary Crossentropy
- **Metrics**: Accuracy

### Training Parameters

- **Epochs**: 10
- **Batch Size**: 32
- **Validation Split**: 0.1 (10% of the training data is used for validation)
- **Verbose**: 1

## Results

The model achieved high performance metrics:
- **Accuracy**: 99.5%
- **F1 Score**: 99.3%

These results demonstrate the model's effectiveness in accurately classifying DDoS traffic.

![Model Accuracy](image.png)

## Usage

To use this model for DDoS traffic classification, load the dataset and follow the provided training script. Make sure to preprocess the dataset as per the specified features.

## Dependencies

- TensorFlow / Keras
- Python 3.x

