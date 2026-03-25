# 🚀 HRSNet: High-Resolution Scalable Network for Image Classification

A deep learning project implementing a **custom High-Resolution Network (HRNet)** from scratch in PyTorch, designed for **multi-scale feature learning and high-accuracy image classification** on CIFAR-100.

This project explores **parallel multi-resolution feature extraction + fusion**, inspired by HRNet, with custom architectural improvements, training strategies, and performance optimizations.

---

## 🔥 Key Highlights

- Built **HRNet architecture from scratch** (no pretrained backbone)
- Multi-branch feature learning across resolutions
- Custom **feature fusion mechanism**
- Trained on **CIFAR-100 (100 classes)**
- Implemented **early stopping + checkpointing**
- Compared multiple configurations (C=2 vs C=30)
- Visualized training and evaluation metrics

---

## 🏗️ Architecture Overview

HRSNet maintains **high-resolution representations throughout the network** instead of aggressively downsampling like traditional CNNs.

### Core Components

### 1. Stem Layer
- Reduces spatial resolution to 1/4
- Extracts initial features

### 2. Stage 1 (Bottleneck Blocks)
- Residual learning with bottleneck layers
- Expands channel depth

### 3. Multi-Resolution Stages (Stage 2–4)
- Parallel branches at different resolutions
- Independent feature processing
- Continuous feature fusion across scales

### 4. Fusion Mechanism
- Upsampling + Downsampling across branches
- Preserves both:
  - High-resolution spatial features
  - Low-resolution semantic features

### 5. Classification Head
- Aggregates multi-scale features
- Global pooling → Fully connected layer
- Outputs predictions for 100 classes

---

## 🧩 Model Variants

| Model        | Channels (C) | Purpose |
|-------------|-------------|--------|
| HRSNet-C2   | Lightweight | Faster training, experimentation |
| HRSNet-C30  | Full model  | Higher accuracy, deeper features |

---

## 📊 Dataset

- Dataset: CIFAR-100  
- Classes: 100  
- Image Size: 224×224  
- Split:
  - 80% Training
  - 20% Validation
  - Separate Test Set  

---

## ⚙️ Training Details

- Framework: PyTorch  
- Loss Function: CrossEntropyLoss  
- Optimizer: SGD  
- Learning Rate: 0.005  
- Batch Size: 16  
- Epochs: ~25  
- Early Stopping: Enabled  

---

## 📈 Results

- Stable convergence during training  
- Reduced overfitting using early stopping  
- Evaluated using:
  - Test accuracy
  - Per-class accuracy
  - Top-performing classes  

---

## 📊 Visualizations

- Training vs Validation Loss  
- Class-wise accuracy  
- Sample predictions  

---

## 🧪 Experimentation

- Channel scaling (C=2 vs C=30)
- Fusion depth tuning
- Early stopping optimization
- Learning rate and optimizer tuning

---

## 🧠 Key Learnings

- Designing multi-scale architectures from scratch  
- Feature fusion across resolutions  
- Training deep neural networks efficiently  
- Implementing checkpointing and early stopping  
- Understanding accuracy vs compute trade-offs  

---

## ⚡ Challenges Faced

- Training instability in deep architectures  
- Overfitting on CIFAR-100  
- Memory constraints with larger models  
- Complex fusion logic  

### Solutions

- Early stopping and validation monitoring  
- Modular architecture design  
- Lightweight model variant (C=2)  
- Efficient batching  

---

## 🔮 Future Improvements

- Add pretrained HRNet backbone  
- Use mixed precision training (FP16)  
- Deploy as API (FastAPI / Flask)  
- Extend to segmentation tasks  
- Hyperparameter tuning (Optuna / Ray Tune)  

---

## 💻 Tech Stack

- Python  
- PyTorch  
- NumPy  
- Matplotlib  
- Torchvision  

---

## 🏁 Conclusion

HRSNet demonstrates how **multi-resolution learning + feature fusion** can improve image classification performance while preserving spatial detail.

This project showcases strong skills in:
- Deep learning architecture design  
- Model optimization  
- End-to-end ML pipeline development  

