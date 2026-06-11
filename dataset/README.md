# 📦 Dataset Setup

This directory is a placeholder for the Animals dataset. The dataset is **not included** in this repository due to its large size (~100MB+).

## 📊 Dataset Overview

| Property | Details |
|----------|---------|
| **Source** | Custom collection (stored on Google Drive) |
| **Total Images** | 5,400 |
| **Classes** | 90 animal species |
| **Images per Class** | 60 |
| **Image Format** | JPEG (`.jpg`) |
| **Resolution** | Variable (resized to 64×64 during preprocessing) |
| **Structure** | `animals/{class_name}/{image}.jpg` |

---

## 🚀 Setup Instructions

### Option 1: Google Colab (Recommended)

The notebook is configured to automatically load the dataset from **Google Drive**. Follow these steps:

1. **Download the dataset** (or use your own copy)
2. **Upload `animals.zip`** to your Google Drive at the following path:
   ```
   MyDrive/project_1_data/animals.zip
   ```
3. **Open the notebook** in Google Colab:
   [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/shivanshu1512/PyTorch_CV_Animals/blob/main/animals_classification_computer_vision.ipynb)
4. **Run Cell 1** — It will mount your Google Drive
5. **Run Cell 2** — It will extract the zip to `/content/data/animals/`

> The extraction code is already written in the notebook. Just ensure the file is at the correct Drive path.

---

### Option 2: Local Setup

If you want to run the notebook locally:

1. Download the dataset and extract it manually
2. Place the extracted `animals/` folder inside a `data/` directory:
   ```
   PyTorch_CV_Animals/
   └── data/
       └── animals/
           ├── antelope/
           ├── bat/
           ├── bear/
           ├── ... (90 folders total)
           └── zebra/
   ```
3. Update the `image_path` variable in the notebook to point to your local path:
   ```python
   image_path = Path("./data/animals")
   ```

---

## 📂 Expected Directory Structure After Extraction

```
animals/
├── train/
│   ├── antelope/    (~48 images)
│   ├── bat/         (~48 images)
│   ├── bear/        (~48 images)
│   └── ...          (90 species × ~48 images)
└── test/
    ├── antelope/    (~12 images)
    ├── bat/         (~12 images)
    ├── bear/        (~12 images)
    └── ...          (90 species × ~12 images)
```

---

## 🐾 Animal Classes (90 Species)

```
antelope, badger, bat, bear, bee, beetle, bison, boar, butterfly,
cat, caterpillar, chimpanzee, cockroach, cow, coyote, crab, crow,
deer, dog, dolphin, donkey, dragonfly, duck, eagle, elephant,
flamingo, fly, fox, goat, goldfish, goose, gorilla, grasshopper,
hamster, hare, hedgehog, hippopotamus, hornbill, horse, hummingbird,
hyena, jellyfish, kangaroo, koala, ladybugs, leopard, lion, lizard,
lobster, mosquito, moth, mouse, octopus, okapi, orangutan, otter,
owl, ox, oyster, panda, parrot, pelecaniformes, penguin, pig,
pigeon, porcupine, possum, raccoon, rat, reindeer, rhinoceros,
sandpiper, seahorse, seal, shark, sheep, snake, sparrow, squid,
squirrel, starfish, swan, tiger, turkey, turtle, whale, wolf,
wombat, woodpecker, zebra
```

---

> **Note:** This `dataset/` folder is tracked in git with only this README. The actual image data should never be committed to the repository.
