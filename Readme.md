# Hybrid Unsupervised Classification Technique for Automatic Brain MRI Tumor Recognition

This folder contains work done on my thesis which can be read in the pdf Khan_OmarIrfan_202001_MSc. The code is designed to automatically classify high grade gliomas (HGG) and low grade gliomas (LGG). Moreover, to differentiate between tumors and normal brains, normal brain MRIs were utilized to show how the algorithm perceives it. 

Online thesis: https://hdl.handle.net/10214/17779

### Objectives

*   Devise a hybrid algorithm to differentiate between HGG and LGG tumors.
*   Create a classification model to differentiate between tumors and normal brain scans.
*   Produce insights on how normal brain differ from tumors.
*   Design a method to achieve higher accuracy in a short period of time.

### Dataset

There were two datasets utilized for this experiments. The [BraTS 2018 dataset](https://www.med.upenn.edu/sbia/brats2018/data.html) contains axial views of the brains in different modalities along with their ground truths. The [Brain tumor public dataset](https://www.kaggle.com/navoneel/brain-mri-images-for-brain-tumor-detection) contains normal images for comparison to tumor images.


### Libraries required

*   [Pandas](https://pandas.pydata.org/) - input data analysis and manipulation tool.
*   [NumPy](https://numpy.org/) - further data manipulation and conversion.
*   [Scikit-learn](https://scikit-learn.org/) - contains machine learning models, feature extraction and metrics for evaluation.
*   [SimpleITK](https://simpleitk.readthedocs.io/en/master/gettingStarted.html#python-binary-files) - contains various filters and helps in separating MRI slices for processing.
*   [Nibabel](https://nipy.org/nibabel/) - required for reading MRI images which are NifTI files.
*   [HDBSCAN](https://hdbscan.readthedocs.io/en/latest/how_hdbscan_works.html) - is a hierarchical clustering algorithm that differentiates outliers from points of interest.
*   [Matplotlib](https://matplotlib.org/) - creating static graphs.
*   [Seaborn](https://seaborn.pydata.org/) - drawing more creative graphs.


### Method

*   Preprocessing: To reduce image biases and noises, we apply an [N4 bias filter](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3071855/) and a smoothing/denoising filter.
*   Clustering: To cluster the MRI scan, we use one of the clustering algorithms such as HDBSCAN. Clustering algorithms such as K-Means, Meanshift, DBSCAN and Agglomerative clustering were used for comparison.
*   Thresholding: The clustered image is passed into a thresholding filter to determine if the image contains a tumor.
*   Evaluation and Analysis: After thresholding, the image is passed into several external and internal cluster metrics such as silhouette score, calinski harabasz score, precision, recall, accuracy and F1 score.