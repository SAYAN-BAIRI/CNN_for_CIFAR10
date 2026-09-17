# CNN for CIFAR-10 Image Classification

This project implements a **Convolutional Neural Network (CNN)** using **PyTorch** to classify images from the **CIFAR-10 dataset** into 10 different classes.

## 📌 Project Overview

CIFAR-10 is an image classification dataset containing images belonging to 10 classes. A CNN is trained to learn visual features from the images and predict the correct class.

The project includes:

* CIFAR-10 dataset loading
* Image normalization
* DataLoader preparation
* CNN model construction
* Model training
* Training accuracy evaluation
* Test accuracy evaluation

## 🛠️ Technologies Used

* Python
* PyTorch
* Torchvision
* CNN
* CIFAR-10
* Google Colab / Jupyter Notebook

## 📂 Dataset

The **CIFAR-10** dataset is loaded using `torchvision.datasets.CIFAR10`.

The images are converted into tensors and normalized using:

```python
transforms.Normalize((0.5, 0.5, 0.5),
                     (0.5, 0.5, 0.5))
```

The DataLoader uses a batch size of **64**.

## 🧠 CNN Architecture

The CNN consists of three convolutional blocks:

```text
Input Image
    ↓
Conv2D: 3 → 32
    ↓
ReLU
    ↓
MaxPooling
    ↓
Conv2D: 32 → 64
    ↓
ReLU
    ↓
MaxPooling
    ↓
Conv2D: 64 → 128
    ↓
ReLU
    ↓
MaxPooling
    ↓
Flatten
    ↓
Fully Connected: 2048 → 256
    ↓
ReLU
    ↓
Fully Connected: 256 → 10
    ↓
Output
```

The final layer contains **10 outputs**, corresponding to the 10 CIFAR-10 classes.

## ⚙️ Training

The model is trained for **10 epochs**.

### Loss Function

```python
nn.CrossEntropyLoss()
```

### Optimizer

```python
optim.Adam(model.parameters())
```

The training loss decreased from approximately **1.03 in epoch 1** to **0.14 in epoch 10**.

## 📊 Results

| Metric            |     Result |
| ----------------- | ---------: |
| Epochs            |         10 |
| Batch Size        |         64 |
| Training Accuracy | **96.68%** |
| Test Accuracy     | **75.06%** |

The notebook reports a training accuracy of **96.68%** and a test accuracy of **75.06%**.

## 📈 Accuracy Interpretation

The model correctly classified about **75% of the test images**.

The difference between the training accuracy (**96.68%**) and test accuracy (**75.06%**) indicates that the model performs much better on the training data than on unseen test data. This can be a sign that the model has learned the training examples very strongly and may benefit from techniques such as data augmentation, dropout, batch normalization, or additional tuning.

## 🚀 How to Run

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd <repository-folder>
```

### 2. Install dependencies

```bash
pip install torch torchvision
```

### 3. Run the notebook

Open:

```text
CNN_for_CIFAR_10.ipynb
```

using Jupyter Notebook or Google Colab.

The CIFAR-10 dataset will be downloaded automatically when the notebook is executed.

## 📁 Project Structure

```text
CNN-CIFAR10/
│
├── CNN_for_CIFAR_10.ipynb
├── README.md
└── data/
```

> The `data/` folder is created when CIFAR-10 is downloaded locally.

## 🎯 Objective

The main objective of this project is to understand how a **Convolutional Neural Network** can be used for image classification and to evaluate its performance on the CIFAR-10 dataset.

## 🔮 Future Improvements

Possible improvements include:

* Data augmentation
* Dropout
* Batch Normalization
* Learning-rate scheduling
* Increasing/decreasing model depth
* Hyperparameter tuning
* Training for more epochs
* Confusion matrix and per-class accuracy
* Visualization of CNN predictions

## 👨‍💻 Author

**Sayan Bairi**

B.Tech – Computer Science & Engineering (AIML)

## 📜 License

This project is intended for educational and learning purposes.
