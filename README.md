
# MNIST Handwritten Digit Recognition

> Classifying handwritten digits (0–9) using a Deep Neural Network built with TensorFlow & Keras — achieves **~98% test accuracy**

---

## Overview

This project implements a **Fully Connected Deep Neural Network (DNN)** to classify handwritten digit images from the MNIST dataset. The model is trained end-to-end from raw pixel values and demonstrates the impact of proper weight initialization, dropout regularization, and adaptive learning rate scheduling.

---

## Dataset

| Property | Detail |
|---|---|
| Name | MNIST (Modified National Institute of Standards and Technology) |
| Source | Yann LeCun, Corinna Cortes, Christopher J.C. Burges |
| Total Samples | 70,000 grayscale images |
| Training Set | 60,000 images |
| Test Set | 10,000 images |
| Image Size | 28 × 28 pixels |
| Classes | 10 (digits 0 through 9) |

---

## Project Workflow

```
1. Import Libraries & Set Seeds
          ↓
2. Load & Explore Dataset
          ↓
3. Visualize Sample Images
          ↓
4. Normalize Pixel Values (÷ 255)
          ↓
5. Build DNN Architecture
          ↓
6. Compile with Adam + Callbacks
          ↓
7. Train the Model
          ↓
8. Evaluate & Plot Results
```

---

## Model Architecture

| Layer | Type | Units | Activation |
|---|---|---|---|
| Input + Flatten | — | 784 | — |
| Hidden 1 | Dense | 512 | ReLU |
| Hidden 2 | Dense | 256 | ReLU |
| Hidden 3 | Dense | 256 | ReLU |
| Hidden 4 | Dense | 128 | ReLU |
| Output | Dense | 10 | Softmax |

- **Weight Initialization:** He Normal
- **Regularization:** Dropout (0.2 → 0.3 → 0.4)

---

## Training Configuration

| Parameter | Value |
|---|---|
| Optimizer | Adam |
| Loss Function | Sparse Categorical Crossentropy |
| Batch Size | 256 |
| Max Epochs | 15 |
| Early Stopping | patience=3, restore best weights |
| LR Reduction | factor=0.5, patience=2, min_lr=1e-6 |

---

## Results

| Metric | Value |
|---|---|
| Test Accuracy | ~98% |
| Test Loss | ~0.07 |

---

## Tech Stack

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.21.0-orange?logo=tensorflow)
![Keras](https://img.shields.io/badge/Keras-3.14.0-red?logo=keras)
![NumPy](https://img.shields.io/badge/NumPy-2.4.4-013243?logo=numpy)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.10.7-blue)
---

## How to Run

**1. Clone the repository**
```bash
git clone https://github.com/deepaksr-07/mnist-digit-classifier.git
cd mnist-digit-classifier
```

**2. Install dependencies**
```bash
pip install tensorflow numpy matplotlib
```

**3. Run the notebook**
```bash
jupyter notebook MNIST_Digit_Recognition.ipynb
```

---

## Repository Structure

```
mnist-digit-classifier/
│
├── MNIST_Digit_Recognition.ipynb   # Main notebook
└── README.md                       # Project documentation
```

---

## Future Improvements

- [ ] Implement a CNN for higher accuracy (99%+)
- [ ] Add Confusion Matrix and per-class accuracy analysis
- [ ] Deploy using Streamlit or Flask
- [ ] Experiment with Batch Normalization

---

## License

This project is open source and available under the [MIT License](LICENSE).
