# Adversarial Patches 
## 📘 Project Overview
Artificial intelligence (AI) systems have achieved remarkable accuracy in image recognition, speech processing, and decision-making. However, they remain surprisingly vulnerable to subtle manipulations. Tiny, human-imperceptible changes can cause models to misclassify objects with high confidence.

To better understand this fragility, I built an **adversarial patch** — a small image designed to trick a model. I used a pretrained **ResNet34** model on the [ImageNet100 dataset](https://www.kaggle.com/datasets/ambityga/imagenet100) , with the purpose to train the patch to fool the model to predict the image as a **“magpie.”** no matter what the original picture showed.

The patch worked well on both digital photos and real-life scenes (e.g. book, pumpkin, microwave, etc), showing us how easily deep learning models can be deceived, and how important it is to build a resilient and trustworthy AI system.


## ⚙️ Methodology

### 1. Model & Dataset

   * Model: `ResNet34`
   * Dataset: [ImageNet100](https://www.kaggle.com/datasets/ambityga/imagenet100)

### 2. Patch Training

   * Target class: `magpie`
   * Patch size: `(75 × 75)`
   * Loss function combines adversarial loss + total variation (smoothness) regularization
   * Training performed on 5,000 sampled images

### 3. Evaluation

   * Tested on 5 unseen validation images from ImageNet100
   * Patch achieved **100% fooling success rate** in digital environment, consistently forcing “magpie” prediction, demonstrating strong attack effectiveness.


## 🧩 Results
### Digital Environment Test Results
![Digital Test Result](./Test_Images/Digital_Test_Result.png)

### Real-world Test Results
To validate the patch outside of digital environments, I printed the trained adversarial patch and tested it across **real-world scenes**, including book with bird, bush and building, keyboard, microwave, pillow and chair, pool and building, and pumpkin. Even under varying lighting, background clutter, and camera angles, the model continued to misclassify the scene as the target class “magpie.” 

#### 🎃 Pumpkin

![Pumpkin 1](./Real-life_Tests/Pumpkin%201.png)
![Pumpkin 2](./Real-life_Tests/Pumpkin%202.png)

#### 🍽️ Microwave

![Microwave 1](./Real-life_Tests/Microwave%201.png)
![Microwave 2](./Real-life_Tests/Microwave%202.png)

#### ⌨️ Keyboard

![Keyboard 1](./Real-life_Tests/Keyboard%201.png)
![Keyboard 2](./Real-life_Tests/Keyboard%202.png)

#### 📖 Book with Bird

![Book with Bird 1](./Real-life_Tests/Book%20with%20bird%201.png)
![Book with Bird 2](./Real-life_Tests/Book%20with%20bird%202.png)

#### 🛋️ Pillow & Chair

![Pillow & Chair 1](./Real-life_Tests/Pillow%20%26%20Chair%201.png)
![Pillow & Chair 2](./Real-life_Tests/Pillow%20%26%20Chair%202.png)

#### 🏢 Pool & Building

![Pool & Building 1](./Real-life_Tests/Pool%20%26%20Building%201.png)
![Pool & Building 2](./Real-life_Tests/Pool%20%26%20Building%202.png)

#### 🌿 Bush & Building

![Bush & Building 1](./Real-life_Tests/Bush%20%26%20Building%201.png)
![Bush & Building 2](./Real-life_Tests/Bush%20%26%20Building%202.png)


