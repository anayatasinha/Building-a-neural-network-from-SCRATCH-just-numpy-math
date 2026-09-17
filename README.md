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

A two-layer fully connected network:

```
   Input          Hidden Layer         Output Layer
  (784)      →      (10, ReLU)     →    (10, Softmax)   →   Digit 0–9
 pixels            Z1 = W1·X + b1       Z2 = W2·A1 + b2
                   A1 = ReLU(Z1)        A2 = Softmax(Z2)
```

| Layer | Operation | Activation | Shape |
|-------|-----------|------------|-------|
| Input | flattened 28×28 image | — | `X: (784, m)` |
| Hidden | `Z1 = W1·X + b1` | ReLU | `W1: (10, 784)`, `b1: (10, 1)` |
| Output | `Z2 = W2·A1 + b2` | Softmax | `W2: (10, 10)`, `b2: (10, 1)` |

Note the data layout: `X` has shape **(784, m)** — one **column** per training example — so all `m` images are pushed through the network in a single matrix multiplication.

### Forward propagation

```
Z1 = W1 · X  + b1
A1 = ReLU(Z1)              ReLU(z) = max(0, z)
Z2 = W2 · A1 + b2
A2 = Softmax(Z2)           Softmax(z)ᵢ = e^zᵢ / Σ e^zⱼ
```

`A2` is a (10, m) matrix of class probabilities — column *i* holds the network's confidence for each digit 0–9 on image *i*.

### Backward propagation

Labels are one-hot encoded into `Y` of shape (10, m). Because Softmax is paired with cross-entropy loss, the output gradient collapses to a single subtraction:

```
dZ2 = A2 − Y
dW2 = (1/m) · dZ2 · A1ᵀ
db2 = (1/m) · Σ dZ2

dZ1 = W2ᵀ · dZ2 ∗ ReLU′(Z1)     ReLU′(z) = 1 if z > 0, else 0
dW1 = (1/m) · dZ1 · Xᵀ
db1 = (1/m) · Σ dZ1
```

### Parameter update

```
W1 := W1 − α · dW1        b1 := b1 − α · db1
W2 := W2 − α · dW2        b2 := b2 − α · db2
```

where `α` is the learning rate. That loop — forward, backward, update — runs for every iteration of training.

---

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



