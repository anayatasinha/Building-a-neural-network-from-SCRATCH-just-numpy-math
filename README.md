# Building-a-neural-network-from-SCRATCH-no-Tensorflow-Pytorch-just-numpy-math-
A neural network built completely from scratch using NumPy and mathematics — no TensorFlow or PyTorch. Implements forward propagation, backpropagation, ReLU, Softmax, and gradient descent for handwritten digit classification.

# Neural Network From Scratch 🧠

⭐ Built from scratch to understand the mathematics behind neural networks.

A simple **2-layer neural network built completely from scratch using NumPy and mathematics**, without TensorFlow or PyTorch.

The model is trained to classify **28×28 handwritten digits** using a dataset containing 784 pixel features.

## 🚀 Features

* Neural network implemented from scratch
* Forward propagation
* Backpropagation
* Gradient descent
* ReLU activation
* Softmax output
* One-hot encoding
* NumPy-based matrix operations
* Training & validation accuracy evaluation

## 🏗️ Architecture

```text
 NEURAL NETWORK FROM SCRATCH
                              │
                              ▼
                    ┌───────────────────┐
                    │   Input Image     │
                    │      28 × 28      │
                    │    784 Pixels     │
                    └─────────┬─────────┘
                              │
                              ▼
                    ┌───────────────────┐
                    │   Input Layer     │
                    │      784           │
                    └─────────┬─────────┘
                              │
                         W₁X + b₁
                              │
                              ▼
                    ┌───────────────────┐
                    │   Hidden Layer    │
                    │       10          │
                    │      ReLU         │
                    └─────────┬─────────┘
                              │
                         W₂A₁ + b₂
                              │
                              ▼
                    ┌───────────────────┐
                    │   Output Layer    │
                    │       10          │
                    │     Softmax       │
                    └─────────┬─────────┘
                              │
                              ▼
                    ┌───────────────────┐
                    │ Digit Prediction  │
                    │      0 – 9        │
                    └───────────────────┘


              ┌──────────────────────────────┐
              │       TRAINING LOOP          │
              │                              │
              │ Forward Propagation          │
              │          ↓                   │
              │ Prediction                   │
              │          ↓                   │
              │ Backpropagation              │
              │          ↓                   │
              │ Calculate Gradients          │
              │          ↓                   │
              │ Gradient Descent              │
              │          ↓                   │
              │ Update Weights & Biases      │
              │          ↓                   │
              │      Repeat × 1000           │
              └──────────────────────────────┘
```

## 📊 Results

* Training iterations: **1000**
* Learning rate: **0.1**
* Validation Accuracy: **~87.36%**

## 🛠️ Tech Stack

* Python
* NumPy
* Pandas
* Matplotlib
* Jupyter Notebook

## 📁 Project Structure

```text
Neural-Network-From-Scratch/
│
├── Neural Network From Scratch.ipynb
├── train.csv
└── README.md
```

## 🎯 Purpose

The goal of this project is to understand **how neural networks actually work internally** by implementing the core mathematical operations.



