# Spatio-temporal segmentation

Spatio-temporal segmentation of satellite images for crop monitoring using Deep Learning and PASTIS dataset.

## About

This repository contains code and resources for performing spatio-temporal segmentation of satellite images, specifically for **crop monitoring**. The project uses **Deep Learning techniques** and the benchmark **PASTIS dataset** (https://github.com/VSainteuf/pastis-benchmark). A key contribution of this work, as presented at the 31st IEEE International Conference on High Performance Computing, Data, and Analytics (HiPC) 2024, is the **investigation of Gaussian noise addition as augmentation to the images and the effect's on the model's accuracies**. The study involves **using different cloud computing infrastructure (Google T4 GPU and AWS g4dn.xlarge) but same architecture and analyzing the impact on segmentation performance.**  The project includes comparisons of the model's performance under these conditions. The goal is to identify and delineate agricultural fields and monitor their temporal evolution using satellite image time series, while also assessing the model's reliability in real-world scenarios with different computations.

## Resources

*   [HiPC\_Final.pdf](HiPC_Final.pdf): This document contains the detailed methodology, experimental results, and a comprehensive explanation of the spatio-temporal segmentation approach using deep learning. It describes the network architecture, training details, evaluation metrics, and the **noise injection experiments**.  Key aspects covered are the U-TAE model, temporal convolution, the PASTIS dataset, and the analysis of segmentation accuracy under different settings.
*   [PASTIS.ipynb](PASTIS.ipynb): A Jupyter Notebook containing the code implementation for the spatio-temporal segmentation. This notebook allows users to reproduce the results presented in the HIPC paper, including the noise experiments and performance comparisons.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Requirements

A `requirements.txt` file is recommended for specifying the necessary Python packages. Based on the HiPC_Final.pdf and typical deep learning tasks, the following packages are likely required (this is an *example*, please verify using the notebook):

