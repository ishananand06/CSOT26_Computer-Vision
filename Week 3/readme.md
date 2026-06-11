# 🚀 CAIC Summer of Technology 2026

## 🧠 Computer Vision Track: Week 3

### 🔍 Transfer Learning, Feature Extraction & Fine-Tuning

---

## 🗒️ Track Context

Over the last two weeks, we’ve trained architectures completely from scratch. However, in professional computer vision pipelines, starting with randomly initialized weights is rarely efficient. Instead, we stand on the shoulders of giants by leveraging models already trained on millions of images.

This week, we master **Transfer Learning**, learning how to take a massive, pretrained neural network, adapt its deep feature-extraction layers to our specific domain, and optimize it to achieve near-perfect accuracy with minimal training time.

---

## 🎯 Week 3 Objectives

Before jumping into the code, our structural goals are to master:

* The core philosophy of Transfer Learning: Transferring knowledge across domain boundaries.
* **Feature Extraction vs. Fine-Tuning**: Knowing exactly when to freeze a backbone network versus updating all parameter weights.
* Advanced optimization management: Learning rate scaling strategies for pretrained weights to prevent destroying existing structural features.

---

## 🗂️ Step-by-Step Action Plan

### Step 1: Initialize Your Compute Environment

* **Do this first**: Open your **Google Colab** or local notebook environment, confirm your GPU runtime is active, and import your dependencies.
* Ensure you are pulling from `torchvision.models` to gain access to production-grade pretrained model zoos.

### Step 2: Study the Philosophy of Pretrained Models

* **Read this guide**: Review the [PyTorch Transfer Learning for Computer Vision Tutorial](https://pytorch.org/tutorials/beginner/transfer_learning_tutorial.html) (https://pytorch.org/tutorials/beginner/transfer_learning_tutorial.html) or read [Andrej Karpathy's CS231n notes on Transfer Learning](https://cs231n.github.io/transfer-learning/) (https://cs231n.github.io/transfer-learning/).
* Focus heavily on the quadrant strategy: How your dataset size and similarity to the original dataset (like ImageNet) dictate whether you should freeze or fine-tune.

### Step 3: Implement Feature Extraction / Frozen Backbone (Build 1)

* **Build this first**: Load a pretrained ResNet-18 model. Programmatically loop through all of its baseline convolutional layers and freeze their gradients so they don't update during training.
* Chop off the original final linear classification layer, and replace it with a brand-new, randomly initialized linear layer matched to the number of classes in our satellite imagery dataset (**EuroSAT**).
* Train *only* this new classification head on EuroSAT and record your metrics.

### Step 4: Implement Full Model Fine-Tuning (Build 2)

* **Build this next**: Instantiate the exact same pretrained ResNet-18 architecture, but this time leave all of its layers completely un-frozen.
* **Watch out for this**: Instead of using your standard learning rate from Week 1, set up your optimizer with a highly conservative, much smaller learning rate (e.g., 10x or 100x smaller). This allows the deep layers to gently adapt to satellite images without erasing the powerful edge and texture detectors they already possess.
* Train the entire model end-to-end on EuroSAT.

### Step 5: Run the Comparative Analysis

* **Compare your results**: Evaluate the convergence speed and final accuracy curves of Build 1 (Frozen Backbone) against Build 2 (Fine-Tuned). Note how both configurations compare to the models you painstakingly trained entirely from scratch back in Week 2.

---

### 🧠 Core Concepts to Remember While Building

* **Gradient Management**: In PyTorch, setting `parameter.requires_grad = False` is what actively stops the backpropagation engine from spending computation time calculating gradients for your frozen layers.
* **The Catastrophic Forgetting Trap**: If you run full model fine-tuning with a high learning rate, your gradients will wipe out the model’s pretrained general knowledge, reducing its performance to a baseline model built from scratch. Read [this article](https://www.projectpro.io/article/catastrophic-forgetting/1034) (https://www.projectpro.io/article/catastrophic-forgetting/1034) before Step 4 if this concept is new to you.
* **Consistency Check**: Keep using the exact same EuroSAT dataset splits and base augmentations from Week 2 to ensure your historical performance comparison is clean and scientific!

---

## ✅ Week 3 Deliverables

* ✅ Completed PyTorch training notebook evaluating both Transfer Learning setups.
* ✅ Inference submission of predictions on the EuroSAT evaluation split using your absolute best-performing pipeline configuration.

🏆 **Leaderboard Target**: Your progress is measured directly against your Week 2 scores. Can you beat your scratch-trained baseline using the power of **Transfer Learning**?

---

## 🔮 What’s Next (Week 4)

* Shifting our focus entirely from standard global image classification to localized scene tracking and understanding.
* Introducing real-time deep object detectors: Breaking down the core historical mechanics leading up to modern **YOLOv8** pipelines.
* Learning how to evaluate spatial coordinates using Intersection over Union (IoU) and mean Average Precision (mAP).

---

*Borrow the intelligence. Refine the weights. Let's dominate the leaderboard!* 🚀