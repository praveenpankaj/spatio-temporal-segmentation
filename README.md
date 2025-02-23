# 🌍 Spatio-Temporal Segmentation Performance Benchmarking

Spatio-temporal segmentation of satellite images for crop monitoring using Deep Learning and PASTIS dataset.

## About

This repository contains code and resources for performing spatio-temporal segmentation of satellite images, specifically for **crop monitoring**. The project uses **Deep Learning techniques** and the benchmark **PASTIS dataset** (https://github.com/VSainteuf/pastis-benchmark). A key contribution of this work, as presented at the 31st IEEE International Conference on High Performance Computing, Data, and Analytics (HiPC) 2024, is the **investigation of Gaussian noise addition as augmentation to the images and the effect's on the model's accuracies**. The study involves **using different cloud computing infrastructure (Google T4 GPU and AWS g4dn.xlarge) but same architecture and analyzing the impact on segmentation performance.**  The project includes comparisons of the model's performance under these conditions. The goal is to identify and delineate agricultural fields and monitor their temporal evolution using satellite image time series, while also assessing the model's reliability in real-world scenarios with different computations. We use **U-TAE (U-Net with Temporal Attention Encoder)** as a model.

🛰️ **Key Findings:**
- **AWS g4dn.xlarge** consistently outperforms **Google Colab T4 GPU** in accuracy and IoU.
- **Gaussian noise augmentation** improves generalization and model robustness.
- Hardware configurations significantly affect segmentation performance.

---

## 📂 Dataset

- **Dataset:** [PASTIS](https://github.com/VSainteuf/PASTIS)
- **Images:** 2,433 multispectral image sequences from Sentinel-2
- **Time Span:** September 2018 - November 2019
- **Resolution:** 10m spatial resolution
- **Annotations:** Semantic and panoptic labels for land-use mapping

---

## 🏗️ Methodology

1. **Pre-processing**
   - Applied **Gaussian noise augmentation** to 25% of images.
   - Images structured as **(T × C × H × W)**.

2. **Model Training**
   - Used **U-TAE** (U-Net with Temporal Attention Encoder).
   - Trained for **15 epochs** with **batch size 2**.

3. **Hardware Comparison**
   - Benchmarked **Google Colab T4 GPU** vs. **AWS g4dn.xlarge**.
   - Metrics: **Accuracy (%)** and **IoU (Intersection over Union %).**

---

## 🔥 Results

| **Metric**               | **Google Colab T4 GPU** | **AWS g4dn.xlarge** |
|--------------------------|------------------------|---------------------|
| **Training Accuracy (No Noise)** | 72.96% | 77.80% |
| **Training Accuracy (With Noise)** | 74.54% | 79.15% |
| **Validation IoU (No Noise)** | 31.00% | 38.02% |
| **Validation IoU (With Noise)** | 31.56% | 38.51% |

🔹 AWS g4dn.xlarge shows **higher accuracy and IoU** than Google Colab T4 GPU.

---

## ⚙️ Requirements
The following [requirements.txt](requirements.txt) file is recommended for specifying the necessary Python packages. Based on the notebook, please update the requirements based on your needs.
📦 Install the dependencies using:

```bash
pip install -r requirements.txt

## Resources

*   [HiPC\_Final.pdf](HiPC_Final.pdf): This document contains the detailed methodology, experimental results, and a comprehensive explanation of the spatio-temporal segmentation approach using deep learning. It describes the network architecture, training details, evaluation metrics, and the **noise injection experiments**.  Key aspects covered are the U-TAE model, temporal convolution, the PASTIS dataset, and the analysis of segmentation accuracy under different settings.
*   [PASTIS.ipynb](PASTIS.ipynb): A Jupyter Notebook containing the code implementation for the spatio-temporal segmentation. This notebook allows users to reproduce the results presented in the HIPC paper, including the noise experiments and performance comparisons.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.


