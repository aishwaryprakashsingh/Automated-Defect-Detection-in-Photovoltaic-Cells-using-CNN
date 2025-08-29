# ⚡ Solar Panel Defect Detection using CNN

## 📌 Overview
This project applies **Convolutional Neural Networks (CNNs)** to detect **defects in solar cells** such as **cracks and inactive regions** using **Electroluminescence (EL) images**.  
It leverages the **ELPV dataset** and demonstrates both **binary (defective vs. non-defective)** and **multi-class (defect type classification)** approaches using **TensorFlow/Keras** and **PyTorch**.

---

## 🎯 Objectives
- Automate defect detection in photovoltaic (PV) cells to support **quality control** and **preventive maintenance**.  
- Compare **binary vs multi-class classification** approaches.  
- Benchmark **TensorFlow/Keras** and **PyTorch** implementations.

---

## 🗂️ Dataset
- **Source:** [ELPV Dataset](https://github.com/zae-bayern/elpv-dataset)  
- **Size:** ~2,600 EL images of solar cells labeled as *functional* or *defective*.  
- **Preprocessing:**
  - Resized images (300×300 px for Keras pipeline).  
  - Normalized pixel values.  
  - Applied data augmentation (flips, rotations).  

---

## 🔧 Methodology
1. **Keras/TensorFlow Pipeline (Binary Classification)**
   - Input: (300, 300, 3)
   - Architecture: 3 × (Conv2D + MaxPooling) → Flatten → Dense → Dropout → Output
   - Loss: SparseCategoricalCrossentropy
   - Optimizer: Adam
   - Epochs: 20, Batch size: 10

2. **PyTorch Pipeline (Multi-class Classification)**
   - Custom `Net(nn.Module)` with convolution + pooling layers
   - Optimizer: SGD with momentum
   - Loss: CrossEntropyLoss
   - Manual training loop with mini-batches

---

## 📊 Results
- **Keras (Binary classification):**
  - Training Accuracy: ~99%  
  - Validation Accuracy: ~98%  

- **PyTorch (Multi-class classification):**
  - Trained a 4-class model to identify different defect types.  
  - Demonstrated class-wise learning (future improvement: add validation metrics & confusion matrix).  

---



---

## 🛠️ Tech Stack
- **Languages:** Python  
- **Frameworks:** TensorFlow/Keras, PyTorch  
- **Libraries:** NumPy, Pandas, Matplotlib, Seaborn  
- **Environment:** Jupyter Notebook  

---

## 🚀 How to Run
1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/Solar-Panel-Defect-Detection.git
   cd Solar-Panel-Defect-Detection
