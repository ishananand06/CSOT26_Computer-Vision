# 🚀 CAIC Summer of Technology 2026

## 🧠 Computer Vision Track: Week 1

### 🔍 Neural Networks, CNNs & PyTorch Foundations

---

## 🗒️ Track Context

We're shifting our focus from raw numbers to pixel data, diving deep into how machines learn to perceive visual information. Over the next few weeks, you will build increasingly complex spatial and temporal vision architectures.

This week, we lay down the absolute bedrock: building structural neural networks from scratch using PyTorch and transitioning into Convolutional Neural Networks (CNNs).

---

## 🎯 Week 1 Objectives

Before we dive into advanced computer vision modeling, we need to master:

* The core math behind Perceptrons, activation functions, and backpropagation.
* PyTorch essentials (Tensors, Autograd, Layer Modules, and data pipeline setups).
* The spatial mechanics of Convolutions (kernels, padding, stride, and pooling).
* Training, hardware acceleration (GPU utilization), and debugging optimization loops.

---

## 🗂️ Step-by-Step Action Plan

### Step 1: Environment Setup & Cloud GPU Check

* **Do this first**: Set up a **Google Colab** notebook for this week.
* Head to the settings and change your runtime type to use a T4 GPU accelerator. (PyTorch requires hardware acceleration to train these networks efficiently, and Colab provides this with zero local setup required!)

### Step 2: Master the Mathematical Foundations

* **Watch this video series**: Dive into the core math of deep learning by watching **Videos 1-4** of the [3Blue1Brown Neural Networks Playlist](https://youtube.com/playlist?list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi&si=YigXBaf3nSdXYbqL).
* Pay close attention to how weights, biases, activation functions, and backpropagation step-by-step update a network's memory.

### Step 3: Get Comfortable with PyTorch

* **Read and code along**: Work through **Sections 1-7** of the official [PyTorch Beginner Tutorials](https://docs.pytorch.org/tutorials/beginner/basics/intro.html).
* Focus heavily on understanding how `Tensors` store data, how `autograd` tracks gradients automatically, and how `Dataset` and `DataLoader` pipelines handle mini-batches.

### Step 4: Build a Fully Connected Network (Build 1)

* **Build this first**: Load up the classic **Fashion MNIST** dataset (a collection of 28x28 grayscale clothing images across 10 classes).
* Flatten those 2D image matrices into a 1D vector of 784 pixels, and build a standard multi-layer perceptron using linear layers and ReLU activations.
* Run your training loop and observe your baseline test metrics.

### Step 5: Shift to Spatial Thinking & CNNs

* **Read this reference**: Study the [Stanford CS231n: Convolutional Networks Notes](https://cs231n.github.io/convolutional-networks/) or watch the [Stanford CS231n Lecture Video on CNN Architectures](https://youtu.be/LxfUGhug-iQ?si=nUAxdBrhoNhdD7KE).
* Understand why flattening images discards vital spatial relationships, and see how sliding convolutional kernels, padding, stride, and Max Pooling preserve spatial properties.

### Step 6: Build a Convolutional Neural Network (Build 2)

* **Build this next**: Using the exact same Fashion MNIST dataset, replace your flattened linear network with a proper Convolutional Neural Network (CNN).
* Route your tensors through Conv2D and MaxPool2D layers before passing them into a final classification head.

---

### 🧠 Core Concepts to Remember While Building

* **Hardware Acceleration**: Always remember to push both your image/label tensors and your model structure to your GPU using your device setup (`.to(device)`) or you will experience massive computational slowdowns!
* **Tracking Shapes**: Keep an explicit mental log of your tensor dimensions—especially when determining the math required to flatten your final convolutional feature maps before sending them into a linear classifier.
* **The Cyclic Training Loop**: Ensure your loop strictly follows the rule: *Set to Train mode ➡️ Forward Pass ➡️ Calculate Loss ➡️ Zero Gradients ➡️ Backward Pass ➡️ Optimizer Step.*

---

## ✅ Week 1 Deliverables

* ✅ Completed PyTorch notebook compiling both your architectural setups.
* ✅ Inference submission of predictions on the held-out test set from Build 1 (Fully Connected NN).
* ✅ Inference submission of predictions on the exact same test set from Build 2 (Convolutional NN).

🏆 **Leaderboard Target**: Your final score for the week will be evaluated based on your **Build 2 CNN Test Accuracy**.

---

## 🔮 What’s Next (Week 2)

* Confronting optimization hurdles when architectures scale deeper (degradation and vanishing gradients).
* Deconstructing residual blocks, skip connections, and Batch Normalization via ResNet-18.
* Leveraging **Data Augmentation** techniques to artificially enhance dataset diversity and performance.

---

*Plan your steps. Train deep. Let’s hit the leaderboard!* 🚀