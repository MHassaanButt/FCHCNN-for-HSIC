# A-Fast-and-Compact-Hybrid-CNN-for-Hyperspectral-Imaging-based-Bloodstain-Classification

This repository contains code for my research paper "A Fast and Compact Hybrid CNN for Hyperspectral Imaging-based Bloodstain Classification". 
The full text of the paper can be found at [this URL](https://ieeexplore.ieee.org/abstract/document/9870277).


If you use this code in your own research, please consider citing our paper:

```@INPROCEEDINGS{9870277,
  author={Butt, Muhammad Hassaan Farooq and Ayaz, Hamail and Ahmad, Muhammad and Li, Jian Ping and Kuleev, Ramil},
  booktitle={2022 IEEE Congress on Evolutionary Computation (CEC)}, 
  title={A Fast and Compact Hybrid CNN for Hyperspectral Imaging-based Bloodstain Classification}, 
  year={2022},
  volume={},
  number={},
  pages={1-8},
  doi={10.1109/CEC55065.2022.9870277}}
```

## Required Python Libraries

 * spectral
 * numpy 
 * pandas 
 * scipy.io 
 * seaborn 
 * plotly
 * matplotlib
 * sklearn
 * keras 
 * h5py
 * plotly
 * tensorflow

## The dataset associated with the source code:
The dataset is available online: https://zenodo.org/record/3984905

## Dataset Descrption
The sensitivity of hyperspectral imaging (imaging spectroscopy) to haemoglobin derivatives makes it a promising tool for detection and classification of blood. However, due to complexity and high dimensionality of hyperspectral images, the development of hyperspectral blood detection algorithms is challenging. To facilitate their development, we present a new hyperspectral blood detection dataset. This dataset consists of 14 hyperspectral images (ENVI format) of a mock-up scene containing blood and visually similar substances (e.g. artificial blood or tomato concentrate). Images were taken over a period of three weeks and differ in terms of background composition and lighting intensity. To facilitate the use of data, the dataset includes an annotation of classes: pixels where blood and similar substances are visible have been marked by the authors. The main intention behind the dataset is to serve as testing data for Machine Learning methods for hyperspectral target detection and classification.

## Algorithm Descrption

**Fast Compact 3D CNN:** the HSI cube is first divided into small overlapping 3-D patches, which are processed to generate 3-D feature maps using a 3-D kernel function over multiple contiguous bands of the spectral information in a computationally efficient way. In brief, our end-to-end trained model requires fewer parameters to significantly reduce the convergence time while providing better accuracy than existing models.

**Hybrid CNN:** Basically, the HybridSN is a spectral-spatial 3D-CNN followed by spatial 2D-CNN. The 3D-CNN facilitates the joint spatial-spectral feature representation from a stack of spectral bands. The 2D-CNN on top of the 3D-CNN further learns more abstract level spatial representation. Moreover, the use of hybrid CNNs reduces the complexity of the model compared to 3D-CNN alone.

## Comparison Table 1

| Classifiers | Sample | Precision | Recall | F1-score |
| --- | --- | --- | --- | --- |
| `Hybird CNN`  | --- | --- | --- |--- |
| ---| blood    |   0.99    |  0.98   |   0.98    |
| ---| ketchup    |   0.99  |  0.98  |   0.99  |
| ---| artificial blood |   0.93   |  0.92 |   0.92   |
| ---| poster paint   |   0.99   |  0.99  |   0.99 |
| ---| tomato concentrate   |   0.94   |  0.91  |   0.92   |
| ---| acrylic paint   |   0.96   |  0.99  |   0.97  | 
| `Fast Compact 3D CNN`  | --- | --- | --- |--- |
| ---|     blood   |    0.94   |    0.97   |   0.96    |
| --- |   ketchup   |       0.97   |   0.99  |    0.98   |
| --- |   artificial blood   |       0.89  |    0.88   |   0.88   |
| ---  |  poster paint   |     1.00   |   0.99  |    1.00    |
   | ---| tomato concentrate   |    0.95   |   0.82   |   0.88     |
| ---   | acrylic paint   |    0.92   |   0.98   |   0.95    | 

## Comparison Table 2 

| Classifiers | Accuracy | Macro avg | Weighted avg|
| --- | --- | --- | --- | 
| `Fast Compact 3D CNN` |0.95    | 0.95 | 0.95|
| `Hybird CNN`  | 0.96 | 0.97 |0.96 |0.96 |  

## Conclusion
The first one is a fast and compact 3D CNN model which classified substances with an overall precision of 95% having 90% above accuracy to classify each blood-like substance individually. In the other deep learning architecture, we have introduced a hybrid 3D and 2D model for hyperspectral image classification which combines spatio-spectral and spectral information using 3D and 2D convolutions. The Hybrid model sums up complementary information and gives higher accuracy of 96% than fast and compact 3D CNN. The aforesaid models have been compared with a relatively fewer number of training samples i.e., only 5% (792 samples) samples are used to train the models, and validated again on 5% (792 samples) samples. Finally, the trained models are blindly tested on 90% (14260 samples) of the data samples.
