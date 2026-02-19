Title : Face Recognition: PCA vs Deep CNN Features

Project Overview :

This project compares classical feature extraction (PCA) with deep CNN-based feature representations (ResNet18) for face recognition using the LFW dataset.

We evaluate both approaches using Support Vector Machines (Linear and RBF kernels) and analyze performance using cross-validation, confusion matrices, and visual comparisons.

Dataset :

- Dataset : Labeled Faces in the Wild (LFW)
- Images resized and processed for both pipelines
- Multiple individuals with sufficient samples per class

# Method 1 : PCA + SVM

Pipeline :
1. Flatten image pixels
2. Standard scaling
3. PCA (150 components)
4. SVM (Linear & RBF)
5. 5-Fold Cross Validation


# Method 2 : Deep CNN Features + SVM

Pipeline :
1. Pretrained ResNet18 (ImageNet weights)
2. Remove final classification layer
3. Extract 512-dimensional deep features
4. Standard scaling
5. SVM (Linear & RBF)
6. 5-Fold Cross Validation


Results :


| Method            | Mean Accuracy | Std  |
|-------------------|--------------|------|
| PCA + Linear      | 0.820        | 0.011|
| PCA + RBF         | 0.832        | 0.021|
| Deep + Linear     | 0.891        | 0.018|
| Deep + RBF        | 0.895        | 0.016|



Key Findings :

- Deep CNN features significantly outperform PCA-based features.
- Deep representations are nearly linearly separable.
- RBF provides slight improvement over linear SVM.
- Deep features show better stability (lower standard deviation).


Visualizations Included :

- Model comparison bar plot
- Confusion matrix for best model (Deep + RBF)
- Example prediction


Conclusion :

Deep pretrained representations provide more discriminative and stable features compared to classical PCA-based approaches for face recognition tasks.


Technologies Used :

- Python
- PyTorch
- Scikit-learn
- NumPy
- Matplotlib


Author :

Undergraduate AI & ML Student  
