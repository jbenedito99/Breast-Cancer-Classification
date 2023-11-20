# Breast Cancer Classification
Breast cancer is a disease that takes the lives of many people, mainly women, year after year. This project’s aim is to increase diagnostic accuracy by pointing out the most important attributes when classifying a breast tumor as benign (non-cancerous) or malignant (cancerous). For two datasets, I created various classifiers. The chosen model for the <b>first dataset</b> had an <b>accuracy of about 98.26%</b>, while the final classifier selected for the <b>second dataset</b> posted an <b>accuracy of around 86.75%</b>.

![image](https://github.com/jbenedito99/Breast-Cancer-Classification/assets/125815448/f57acf21-503c-4a29-a4ec-affa2a9bfb30)
![image source](https://www.researchgate.net/figure/FNA-results-for-benign-and-malignant-tumor-under-the-microscope_fig1_286571014) 

# Business Understanding
Breast cancer accounts for 12.5% of all new cancer cases, deeming it the most common cancer in the world. In the United States, around 30% of all new cancer cases diagnosed in women are breast cancer. 1 in 8 U.S. women are expected to develop breast cancer some time in their life. Currently, more than 4 million U.S. women have a history of breast cancer. It is estimated that approximately 300,000 more women in the United States will be diagnosed with breast cancer in 2023 [(breastcancer.org)](https://www.breastcancer.org/facts-statistics).

Given the statistics, it is obvious why accurate screenings are important. The sooner a doctor is able to catch breast cancer in a patient’s imaging, the more likely they can get lifesaving treatment before their disease progresses to a fatal, irreversible state. The main stakeholders for this project are gynecologists and other medical professionals who are in charge of examining tumor biopsies and images. I want them to know the top characteristics to look for when determining whether a tumor is cancerous or not on both a cellular and whole-tumor level. 

# Data Understanding
The first dataset I used was <b>breast-cancer.csv</b>. Each row represented a group of cells in a tumor captured in one image. Each column was a different cellular characteristic, which was calculated from a fine needle aspirate (FNA) biopsy image of a breast mass. The target variable was the <b>diagnosis</b> column, which had an 'M' to denote 'malignant' and a 'B' to signify 'benign'. There were <b>10 features</b> that were looked at and quantified when analyzing the FNA images; for each one, the <b>mean</b>, <b>standard error (SE)</b>, and <b>worst (largest)</b> value were determined. The 10 features were as follows:
* Radius
* Perimeter
* Area
* Compactness
* Smoothness
* Concavity
* Concave Points
* Symmetry
* Fractal Dimensions
* Texture

The second dataset I used was called <b>mammographic_masses.csv</b>, which contained a series of BIRADS evaluations for various mammographies. This dataset had several rows, each one representing a patient and their tumor. Similar to the first dataset, the target variable was <b>severity</b>, which had a '1' to indicate malignancy and a '0' to denote benign. The other columns were as follows:
* <b>Score:</b> BIRADS assessment (0-6)
* <b>Age:</b> how old a patient is (years)
* <b>Shape:</b> the shape of the mass
* <b>Margin:</b> the margin of the mass
* <b>Density:</b> the density of the mass

For both datasets, there was <b>no class imbalance</b> issue, as demonstrated by the images below: 
![image](https://github.com/jbenedito99/Breast-Cancer-Classification/assets/125815448/edfce5e1-8cab-48e0-ae21-042a11d75307) 

For <b>breast cancer</b> dataset

![image](https://github.com/jbenedito99/Breast-Cancer-Classification/assets/125815448/3ecb4b5f-b379-46cf-867c-12dcc4692f9e)

For <b>mammographic masses</b> dataset

# Modeling and Evaluation 
For the first dataset, I created the following models (decision trees and random forests):
* Model 1a: dtree_baseline
* Model 1b: dtree_tuned
* Model 2a: forest_baseline
* Model 2b: forest_tuned

Compared to the baseline decision tree, which had an accuracy of about 86%, the final model had an accuracy of about 98%.

For the second dataset, I generated the following classifiers (decision trees, random forests, KNNs, XGBoost models):
* Model 3a: dtree_baseline_mm
* Model 3b: dtree_tuned_mm
* Model 4a: forest_baseline_mm
* Model 4b: forest_tuned_mm
* Model 5a: knn_baseline_mm
* Model 5b: knn_tuned_mm
* Model 6a: XGB_baseline_mm
* Model 6b: XGB_tuned_mm

Compared to the baseline decision tree, which had an accuracy of about 80%, the final model had an accuracy of about 88%.

# Conclusion 
For my first model, I suggest that it be used to determine which <b>cellular level</b> characteristics are most important in deeming malignancy, particularly when looking at FNA images. For my second model, I recommend it be deployed for <b>whole-tumor level</b> purposes, such as deciding on the shape or margin type that is the best predictor of whether a mass is malignant or not. 

Based on my analysis, my final suggestions for determining malignancy are to look for:
* <b>Cellular level:</b>
  * Largest area
  * Largest number of concave points
  * Largest radius
  
* <b>Whole-tumor level:</b>
  * BIRADS score of 5 or 6
  * Spiculated tumor margin
  * Irregular tumor shape

Here are some visualizations that guided my stakeholder recommendations:
![image](https://github.com/jbenedito99/Breast-Cancer-Classification/assets/125815448/e3efd74f-904e-4bbb-95ee-e7b2d1715de6)

![image](https://github.com/jbenedito99/Breast-Cancer-Classification/assets/125815448/2a539e05-75e5-44e7-83ce-758017eb6f9e)

![image](https://github.com/jbenedito99/Breast-Cancer-Classification/assets/125815448/bdd20a8e-f39a-4a8e-ab9a-1ab49a7813d7)

![image](https://github.com/jbenedito99/Breast-Cancer-Classification/assets/125815448/1cef4126-f2af-4fe2-bdfa-cc5507a8c9a2)

# Repository Navigation and Resources
This repository contains the following files:
* <b>breast-cancer.csv:</b> data focuses on cellular level characteristics of breast cancer tumors and was quantified from FNA images; [Kaggle link](https://www.kaggle.com/datasets/yasserh/breast-cancer-dataset)
* <b>mammographic_masses.csv</b>: data focuses on whole-tumor characteristics; can be downloaded from [this source](https://data.world/julio/mammographic-masses)
* A non-technical [presentation](https://docs.google.com/presentation/d/1R1fnb6mz5Ys-XjyiQNYs3zTC6d4QnR0xKSUEoEQ9JJY/edit?usp=sharing)
* A Jupyter notebook: contains all of the necessary code and models

# Reproducibility Instructions
To reproduce this project, begin by cloning the repository, which contains both datasets. You can also download the datasets from the links above. Then, run the Jupyter notebook, which houses the code for the final models.  

