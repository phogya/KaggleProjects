# KaggleProjects
A collection of my Kaggle competition projects. Includes two attempts at the beginner housing regression competition with two different approaches attempting to classify numeric and categoric data for regression. Also includes one attempt at a plant pathology competition using convolutional neural networks for multiclass image classification.

## Housing Regression
Uses the Pandas, Numpy, Scikit-learn, Tensorflow, and Keras libraries to predict housing prices with neural networks. Mostly an exploratory attempt to learn about various data science techniques. Some of these techniques seemed to have a particularly large ratio of development time to perfromance improvement. This was the primary motivation for trying an alternative approach later. The separate encodings of categoric features based on the relationship between their categories seemed particularly helpful, but the learned embeddings were unnecessary for features this simple.

  RMSE : 0.14
  
  Competition Placement : 2600/5400, 48%

## Housing Regression 2
Uses the Pandas, Numpy, Scikit-learn and XGBoost libraries to predict housing prices using various regression algorithms from Scikit and XGBoost and uses a Scikit ensemble to combine them. This project used the same separation of categoric feature encodings but without learned embeddings. Using the boxcox transformation on the skewed features and target value seemed a particularly valuable improvement and worked better than a log transformation. The ensemble of Scikit regressors and XGBoost regressors was both much faster and easier to implement and also yielded better results.

  RMSE : 0.12
  
  Competition Placement : 1425/5400, 26%

## Plant Pathology
Uses the Pandas, Numpy, Scikit-learn, Tensorflow, and Keras libraries as well as the Kaggle TPUs to perform multiclass image classification using convolutional neural networks. The multiple classes in this project overlapped in that one of the classes was a combination of two others. This led me to create an ensemble of binary classifiers for each class and then use a final neural network to combine the results. Due to the way the images are handled by tensorflow datasets and the TPU these separate classifiers decreased available computational power significantly. At the same time the results achieved were about equal or slightly better than other notebooks that opted for the more conventional approach. Finding a way to make this approach work well with the TPU may be valuable in the rare of case overlapping multiclass classification. 

  Accuracy : 0.97
  
  Competition Placement : 171/1317, 13%
