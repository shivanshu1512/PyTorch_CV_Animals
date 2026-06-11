<div align="center">

# 🦁 PyTorch Animal Classification — 90 Species

<p align="center">
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white" alt="PyTorch"/>
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/Google%20Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white" alt="Google Colab"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge" alt="License"/>
</p>

<p align="center">
  <strong>A Computer Vision project built with PyTorch for classifying 90 different animal species using deep learning and transfer learning techniques.</strong>
</p>

<p align="center">
  <a href="https://colab.research.google.com/github/shivanshu1512/PyTorch_CV_Animals/blob/main/animals_classification_computer_vision.ipynb" target="_parent">
    <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
  </a>
</p>

</div>

---

## 📖 Table of Contents

- [Overview](#-overview)
- [Dataset](#-dataset)
- [Model Architecture](#-model-architecture)
- [Results](#-results)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
- [Usage](#-usage)
- [Requirements](#-requirements)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🔍 Overview

This project implements an **image classification pipeline** to identify **90 distinct animal species** using PyTorch and Transfer Learning. It demonstrates core deep learning concepts including:

- 📦 **Custom Dataset Loading** with `torchvision.datasets.ImageFolder`
- 🔄 **Data Augmentation & Preprocessing** with `torchvision.transforms`
- 🧠 **Transfer Learning** using pretrained CNN backbones (EfficientNet/ResNet)
- 📊 **Training & Evaluation** loops with loss tracking
- 🎯 **Multi-class Classification** across 90 animal categories

---

## 📊 Dataset

The dataset consists of **5,400 images** across **90 animal species** (60 images per class).

> **⚠️ Note:** The dataset is **not included** in this repository due to its large size.  
> Please follow the instructions in [`dataset/README.md`](dataset/README.md) to download and set up the dataset from Google Drive.

### Animal Classes (90 total)

<details>
<summary>Click to expand the full list of animal classes</summary>

| # | Animal | # | Animal | # | Animal |
|---|--------|---|--------|---|--------|
| 1 | antelope | 31 | goose | 61 | pigeon |
| 2 | badger | 32 | gorilla | 62 | porcupine |
| 3 | bat | 33 | grasshopper | 63 | possum |
| 4 | bear | 34 | hamster | 64 | raccoon |
| 5 | bee | 35 | hare | 65 | rat |
| 6 | beetle | 36 | hedgehog | 66 | reindeer |
| 7 | bison | 37 | hippopotamus | 67 | rhinoceros |
| 8 | boar | 38 | hornbill | 68 | sandpiper |
| 9 | butterfly | 39 | horse | 69 | seahorse |
| 10 | cat | 40 | hummingbird | 70 | seal |
| 11 | caterpillar | 41 | hyena | 71 | shark |
| 12 | chimpanzee | 42 | jellyfish | 72 | sheep |
| 13 | cockroach | 43 | kangaroo | 73 | snake |
| 14 | cow | 44 | koala | 74 | sparrow |
| 15 | coyote | 45 | ladybugs | 75 | squid |
| 16 | crab | 46 | leopard | 76 | squirrel |
| 17 | crow | 47 | lion | 77 | starfish |
| 18 | deer | 48 | lizard | 78 | swan |
| 19 | dog | 49 | lobster | 79 | tiger |
| 20 | dolphin | 50 | mosquito | 80 | turkey |
| 21 | donkey | 51 | moth | 81 | turtle |
| 22 | dragonfly | 52 | mouse | 82 | whale |
| 23 | duck | 53 | octopus | 83 | wolf |
| 24 | eagle | 54 | okapi | 84 | wombat |
| 25 | elephant | 55 | orangutan | 85 | woodpecker |
| 26 | flamingo | 56 | otter | 86 | zebra |
| 27 | fly | 57 | owl | 87 | ox |
| 28 | fox | 58 | oyster | 88 | panda |
| 29 | goat | 59 | parrot | 89 | penguin |
| 30 | goldfish | 60 | pelecaniformes | 90 | pig |

</details>

---

## 🧠 Model Architecture

The project uses **Transfer Learning** with a pretrained CNN backbone:

```
Input Image (64×64×3)
        │
        ▼
┌─────────────────────┐
│  Pretrained Backbone│  ← EfficientNet / ResNet (ImageNet weights)
│  (Feature Extractor)│
└─────────────────────┘
        │
        ▼
┌─────────────────────┐
│   Custom Classifier │  ← Fully Connected Layers
│   Dropout + ReLU    │
└─────────────────────┘
        │
        ▼
   Output (90 classes)
```

**Key Techniques Used:**
- ✅ Pretrained weights from ImageNet
- ✅ Fine-tuning of the classification head
- ✅ Data normalization using ImageNet mean/std
- ✅ Learning rate scheduling
- ✅ CrossEntropyLoss with Adam optimizer

---

## 📈 Results

| Metric | Value |
|--------|-------|
| Dataset Size | 5,400 images |
| Number of Classes | 90 |
| Image Resolution | 64×64 |
| Train/Test Split | 80% / 20% |

> Training was performed on **Google Colab T4 GPU**.

---

## 📁 Project Structure

```
PyTorch_CV_Animals/
│
├── 📓 animals_classification_computer_vision.ipynb   # Main notebook
│
├── 📂 dataset/
│   └── 📄 README.md       # Instructions to download the dataset
│
├── 📄 requirements.txt    # Python dependencies
├── 📄 .gitignore          # Git ignore rules
├── 📄 LICENSE             # MIT License
└── 📄 README.md           # This file
```

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/shivanshu1512/PyTorch_CV_Animals.git
cd PyTorch_CV_Animals
```

### 2. Set Up the Dataset

Follow the instructions in [`dataset/README.md`](dataset/README.md) to download the `animals.zip` dataset from Google Drive and place it in the correct location.

### 3. Run on Google Colab (Recommended)

Click the badge below to open the notebook directly in Google Colab:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/shivanshu1512/PyTorch_CV_Animals/blob/main/animals_classification_computer_vision.ipynb)

> **Make sure your dataset is uploaded to Google Drive** at `MyDrive/project_1_data/animals.zip` before running the notebook.

---

## 💻 Usage

### Running Locally

```bash
# Install dependencies
pip install -r requirements.txt

# Launch Jupyter Notebook
jupyter notebook animals_classification_computer_vision.ipynb
```

### Notebook Walkthrough

| Step | Description |
|------|-------------|
| **1. Data Loading** | Mount Google Drive and extract `animals.zip` |
| **2. Data Exploration** | Visualize dataset structure and sample images |
| **3. Preprocessing** | Apply transforms (resize, normalize, augment) |
| **4. DataLoaders** | Create train/test DataLoaders with batching |
| **5. Model Setup** | Load pretrained model, replace classifier head |
| **6. Training** | Train with loss tracking and evaluation |
| **7. Evaluation** | Test accuracy, confusion matrix visualization |

---

## 📦 Requirements

```
torch>=2.0.0
torchvision>=0.15.0
Pillow>=9.0.0
matplotlib>=3.5.0
numpy>=1.22.0
tqdm>=4.64.0
scikit-learn>=1.0.0
```

> Install all dependencies at once:
> ```bash
> pip install -r requirements.txt
> ```

---

## 🤝 Contributing

Contributions are welcome! Here's how to get started:

1. **Fork** the repository
2. **Create** a feature branch: `git checkout -b feature/amazing-feature`
3. **Commit** your changes: `git commit -m 'Add amazing feature'`
4. **Push** to the branch: `git push origin feature/amazing-feature`
5. **Open** a Pull Request

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 👤 Author

**Shivanshu Shukla**

[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/shivanshu1512)

---

<div align="center">

⭐ **Star this repo if you found it helpful!** ⭐

</div>
