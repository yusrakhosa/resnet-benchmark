# 🧠 ResNet Residual Learning Benchmark

<p align="center">
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white" alt="PyTorch"/>
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/Google%20Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white" alt="Google Colab"/>
  <img src="https://img.shields.io/badge/Computer%20Vision-8A2BE2?style=for-the-badge" alt="Computer Vision"/>
</p>

<p align="center">
  <b>Residual network image classification and reproduction study | CS-320 ANN & Deep Learning | Fall 2026</b>
</p>

---

## 📌 About the Project

Deep neural networks become harder to optimize as depth increases: very deep plain networks can show higher training error than shallower ones, a problem called degradation[cite: 4]. Residual Networks (ResNets) address this with identity shortcut connections that let layers learn residual functions[cite: 4]. 

This project reproduces the CIFAR-10 experiments of He et al. (2016), compares plain and residual networks of increasing depth, and extends the study to CIFAR-100 to test whether the findings carry over to a harder 100-class task[cite: 4].

### 🎯 Research Questions & Evaluation

| Research Question | Method and Evaluation |
|---|---|
| **Q1. Can the CIFAR-10 results of the ResNet paper be reproduced?** | Train ResNet-20, 32, 44, and 56 with the paper's recipe (SGD, momentum 0.9, step learning-rate schedule). Compare test error with the published values over several seeds[cite: 4]. |
| **Q2. Do residual connections reduce degradation compared with plain networks?** | Train plain and residual networks of equal depth on CIFAR-10. Compare training and test error curves, convergence speed, and accuracy as depth increases[cite: 4]. |
| **Q3. How do the findings transfer to CIFAR-100, and which design choices matter?** | Train the same models on CIFAR-100; report top-1/top-5 error and macro-F1. Change one factor at a time where feasible: shortcut type, depth, and augmentation[cite: 4]. |

## 🗂️ Datasets & Repository

* **CIFAR-10:** Contains 60,000 images in 10 classes (50,000 training and 10,000 test) and is used to reproduce the paper's results[cite: 4].
* **CIFAR-100:** Has the same size and image format but 100 fine-grained classes (600 images each) and is used as the new dataset[cite: 4].
* **Repository:** https://github.com/yusrakhosa/resnet-benchmark[cite: 4, 5]

## 🔄 Planned Approach

* Load and explore CIFAR-10 and CIFAR-100; inspect class distributions, image dimensions, sample images, and data-quality issues[cite: 4].
* Prepare train/validation/test splits (45k/5k as in the paper), preprocessing, and augmentation; record seeds and configurations[cite: 4].
* Implement plain and residual CIFAR networks ($6n+2$ layers with $3\times3$ convolutions, batch normalization, and identity shortcuts) in PyTorch; train depths 20, 32, 44, and 56 on CIFAR-10[cite: 4].
* Extend to CIFAR-100 with the same architectures and recipe; compare with ResNet-110 if compute allows, under a documented budget[cite: 4].
* Run feasible ablations; evaluate with accuracy, precision, recall, macro-F1, confusion matrices, learning curves, and training time[cite: 4].

## 🚀 Planned Tools
Python, PyTorch, torchvision, NumPy, pandas, scikit-learn, Matplotlib, Pillow, Google Colab, Git, and GitHub[cite: 4].

## 👥 Team Members & Role Split

| Member | Lead Role | Responsibilities |
|---|---|---|
| **Yusra Khosa** | Team lead | Plain and residual network implementation and CIFAR-10 training; coordinate integration, milestones, and team progress[cite: 5]. |
| **Muhammad Zafeer** | Data and pipeline lead | Data pipeline, preprocessing and augmentation, CIFAR-100 experiments, and ablation experiments[cite: 5]. |
| **Faizan Bukhari** | Evaluation and demo lead | Reproduction checks, model evaluation, comparisons, visualizations, and demo development[cite: 5]. |
| **All members** | Shared | Read the original paper, review results, contribute to the report and slides, and prepare for the viva[cite: 5]. |

## 🗺️ Milestones

* **Milestone 1 — Setup and data review:** read the paper, set up the environment, verify dataset access, and complete initial exploration[cite: 5].
* **Milestone 2 — Data preparation and baseline:** finalize preprocessing and augmentation, then establish initial plain-network results[cite: 5].
* **Milestone 3 — ResNet implementation:** train residual networks on CIFAR-10 and compare with the paper's reported errors[cite: 5].
* **Milestone 4 — Experiments and evaluation:** run CIFAR-100 experiments, comparisons, and selected ablations, and analyze errors[cite: 5].
* **Milestone 5 — Final submission:** finish visualizations, demo, report, repository documentation, slides, and viva preparation[cite: 5].

*(Note: Exact milestone dates will follow the course schedule[cite: 5].)*

## ⚖️ Ethics and Disclosure

The project will use public datasets in accordance with their licences and attribution requirements. Results will be reported only when supported by recorded experiments. Differences in preprocessing, augmentation, training schedules, and compute budgets will be documented because they affect fair comparison with the published results. Compute limits, shortened schedules, and seed variation may restrict the experiments; these limitations and any external code or generative-AI assistance will be disclosed according to course requirements[cite: 5].

## 📚 References

1. ResNet: Enabling Deep Convolutional Neural Networks through Residual Learning Xingyu Liu
2. Project repository: https://github.com/yusrakhosa/resnet-benchmark[cite: 4, 5].
3. CIFAR-10 and CIFAR-100: [cs.toronto.edu/~kriz/cifar.html](https://www.cs.toronto.edu/~kriz/cifar.html)[cite: 5].
