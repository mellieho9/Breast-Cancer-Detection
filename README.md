# Breast Cancer Detection Using CNN in Python
A Python program that uses deep neural network techniques to conduct early diagnosis of breast cancer

## Background
Breast cancer is the most commonly diagnosed cancer among American women. As of January 2021, there are more than 3.8 million women with a history of breast cancer in the U.S. For women in the U.S., breast cancer is the second leading cause of cancer deaths. 

Screening mammography addresses this issue by allowing for early diagnosis and thus treatment of breast cancer. Despite its benefits, screening mammograms are associated with a high risk of false positives and false negatives. Researchers have been turned to deep learning as a way to improve the accuracy of screening mammography. Indeed, recent studients have shown that a deep learning based CAD system performed as well as radiologists in standalone mode and improved their performance in support mode. 

To test this, this project has utilized Convolutional Neural Network and the Keras/Tensorflow library to create a program that detects breast cancer.

## Input Data
Training data was obtained from the Breast Cancer Wisconsin dataset at [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/breast+cancer+wisconsin+(diagnostic)). This dataset includes 569 instances, a label, an ID, and 30 columns of feature space. 

## Approach
1. Install Tensorflow and import necessary libraries: 
  - For deep learning: Keras.layers, Keras.optimizers, and sklearn
  - For data analysis and visualization: Pandas, Numpy, Seaborn, Matplotlib
2. Load cancer datasets into the cancer variable.
3. Import dataset into a X vector, with data from the dataset, and columns from the feature names.
4. Import target points into a Y vector. With X and Y vectors, we can train the model.
5. Split the vectors into test and training data on a 2:8 ratio and stratify them accordingly to y.
6. Bring all the features in the X vectors to the same scale and convert them into a numpy array by calling <code>StandardScale()</code> and <code>scaler.fit_transform</code>.
7. Reshape the X vectors.
8. Build a sequential model.
9. Add a 1D convolutional layer of 32 filter size, 2 kernal size, and a 'relu' ativation function.
10. Add to this layer batch normalization and Drop out of 20%.
11. Add another 1D convolutional layer of 64 filter size, 2 kernal size, and a 'relu' ativation function.
12. Add to this layer batch normalization and Drop out of 50%.
13. Flatten the two-dimensional data into a vector.
14. Provide a dense layer with 64 units, relu activation function, and dropout of 50%.
15. Provide a dense layer with 1 unit and a sigmoid activation function.
16. Compile the model with an Adam optimizer at learning rate = 0.00005.
17. Train the now compiled model at epoch = 50, with the training data.

## References
1. “U.S. Breast Cancer Statistics | Breastcancer.org.” Breastcancer.org, 4 Feb. 2021, www.breastcancer.org/symptoms/understand_bc/statistics.
2. “National Performance Benchmarks for Modern Screening Digital Mammography: Update from the Breast Cancer Surveillance Consortium | Radiology.” Radiology, 2019, pubs.rsna.org/doi/10.1148/radiol.2016161174.
3. Rodríguez-Ruiz, Alejandro, et al. "Detection of breast cancer with mammography: effect of an artificial intelligence support system." Radiology 290.2 (2019): 305-314.
