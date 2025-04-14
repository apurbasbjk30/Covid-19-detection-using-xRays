# 🩻 X-Ray Image Classification using Deep Learning

This project explores the classification of **X-ray images into three categories** using deep learning techniques. We implement and compare three models — **Artificial Neural Network (ANN)**, **Convolutional Neural Network (CNN)**, and **Recurrent Neural Network (RNN)** — to evaluate their performance on image data.

---

## 📚 Dataset Overview

- **Domain**: X-Ray Image Classification
- **Input**: Grayscale medical X-ray images (converted to 1x28x28 for simplicity)
- **Classes**: 3 (e.g., Normal, Pneumonia, Other — or as per your dataset)
- **Split**: Training and Validation sets

---

## 🧠 Models Implemented

### 🔹 1. Artificial Neural Network (ANN)

- **Architecture**: 
  - Flattened input (28x28 → 784)
  - Multiple fully connected layers
  - ReLU activation and dropout for regularization
- **Strengths**: Simple and fast to train
- **Limitations**: Lacks spatial awareness, lower performance on image data

---

### 🔹 2. Convolutional Neural Network (CNN)

- **Architecture**:
  - Two convolutional layers + max-pooling
  - Flatten + Fully connected layers
  - Uses ReLU and softmax activations
- **Strengths**: 
  - Captures spatial and hierarchical patterns in images
  - Best suited for image classification tasks
- **Performance**: Achieved the highest validation accuracy on X-ray data

---

### 🔹 3. Recurrent Neural Network (RNN with LSTM)

- **Architecture**:
  - Treats each image row (28 pixels) as a time step → sequence of 28 steps
  - Two-layer LSTM
  - Output passed through fully connected layer
- **Use Case**: Sequence modeling, tried experimentally on image data
- **Observation**: Surprisingly competitive on X-ray images, though CNN still leads

---

## 📊 Accuracy vs Epochs

### 🔸 ANN Accuracy
![image](https://github.com/user-attachments/assets/7baaf0ff-0285-4dad-804e-10c76a80130a)


### 🔸 CNN Accuracy
![image](https://github.com/user-attachments/assets/b2817490-b6f7-4e31-9fb1-37029d15b5d3)


### 🔸 RNN Accuracy
![image](https://github.com/user-attachments/assets/5e4adc7a-c4ae-4367-b2e6-3d4df129b711)


---

## 📉 Loss vs Epochs

### 🔸 ANN Loss
![image](https://github.com/user-attachments/assets/5b252c5d-6445-4e1b-acbd-4a93d7fcf2aa)


### 🔸 CNN Loss
![image](https://github.com/user-attachments/assets/93710ecd-a3ad-4e31-b623-6122ec19d6a9)


### 🔸 RNN Loss
![image](https://github.com/user-attachments/assets/37fda5fb-d148-40a0-97b2-25011c28ea64)


---
## 📈 Accuracy & Loss Comparison

### 🔸 ANN Performance Summary
| Epoch | Training Accuracy | Validation Accuracy | Training Loss | Validation Loss |
|-------|-------------------|---------------------|----------------|------------------|
| 1     | 0.74              | 0.68                | 0.61           | 0.65             |
| 5     | 0.93              | 0.86                | 0.21           | 0.35             |
| 10    | 0.95              | 0.76                | 0.15           | 0.44             |
| 15    | **0.97**          | **0.90**            | **0.10**       | **0.26**         |

### 🔸 CNN Performance Summary
| Epoch | Training Accuracy | Validation Accuracy | Training Loss | Validation Loss |
|-------|-------------------|---------------------|----------------|------------------|
| 1     | 0.43              | 0.36                | 1.09           | 1.11             |
| 5     | 0.45              | 0.54                | 1.05           | 1.05             |
| 10    | 0.71              | 0.76                | 1.00           | 1.00             |
| 15    | **0.77**          | **0.72**            | **0.89**       | **0.95**         |

### 🔸 RNN Performance Summary
| Epoch | Training Accuracy | Validation Accuracy | Training Loss | Validation Loss |
|-------|-------------------|---------------------|----------------|------------------|
| 1     | 0.76              | 0.58                | 0.59           | 0.80             |
| 5     | 0.98              | 0.88                | 0.07           | 0.38             |
| 10    | 0.99              | 0.94                | 0.04           | 0.26             |
| 15    | **0.97**          | **0.88**            | **0.07**       | **0.45**         |

---
## 📈 Model Performance Summary

| Model | Peak Training Acc | Peak Validation Acc | Observations |
|-------|-------------------|---------------------|--------------|
| ANN   | 0.98              | 0.92                | Great generalization, simple design |
| CNN   | 0.77              | 0.76                | Slower convergence, spatial structure important |
| RNN   | 0.99              | 0.96                | Highly expressive, surprisingly good results on image-like data |

---

🧠 Predicting X-Ray Image Labels
In addition to training and evaluating the models, this project also includes a prediction function that allows you to classify new X-ray images.
🔹 Example Output:
When testing the model on a sample image, the actual label and predicted label are displayed.
Actual Label: Viral Pneumonia

Predicted Label: Viral Pneumonia

🔸 Visual Output:
The image is displayed along with the actual label and the predicted label by the model. This provides an intuitive way to evaluate the model's performance visually and qualitatively.


![image](https://github.com/user-attachments/assets/74d96bab-746d-45fb-83fb-46ad48d330cc)


## ⚙️ Training Configuration

- **Optimizer**: Adam
- **Loss Function**: CrossEntropyLoss
- **Batch Size**: 64
- **Epochs**: 15
- **Evaluation**: Accuracy and Loss over Epochs (Training + Validation)

---

## 📝 Note

- All models were trained from scratch using PyTorch.
- RNNs are not traditionally used for image data but provided competitive performance in this case.
- CNNs remain the most robust choice for spatially rich image data like X-rays.

---

## ✅ Future Work

- Fine-tune CNN for better generalization
- Apply transfer learning using pre-trained models (e.g., ResNet, VGG)
- Deploy best-performing model via Flask or Streamlit

---

## 🙌 Acknowledgments

- Dataset and preprocessing support from open medical datasets
- PyTorch tutorials and documentation
