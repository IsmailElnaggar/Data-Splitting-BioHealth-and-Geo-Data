# Data-Splitting-BioHealth-and-Geo-Data
Different exercises from my Applications of Data Analysis course click on a notebook file to view the exercise

**This README will contain a short description of each exercise notebook in this repo.**

**1.  Water permability prediction in forestry using "Exercise 4 data"**
----------------
In this task, the client wants you to estimate the spatial prediction performance of K-nearest neighbor regression model with K=5 (5NN), using spatial leave-one-out cross-validation (i.e. SKCV, with number of folds == number of data points). The client wants you to use the C-index as the performance measure.  

In other words, the client wants you to answer the question: "What happens to the prediction performance of water permeability using 5-nearest neighbor regression model, when the geographical distance between known data and unknown data increases?".

In this task, you have three data files available (with 1691 data points).

Implement the following tasks to complete this exercise:

#### 1. Z-score standardize the predictor features (input.csv). 

#### 2. Create your own implementation of spatial leave-one-out cross-validation with 5NN model for the provided data set (check the end of the lecture slides for the pseudocode). Estimate the water permeability prediction performance (using 5NN model and C-index) with the following distance parameter values: d = 0, 10, 20, ..., 250 (that is, 10 meter intervals). 

#### 3. When you have calculated the C-index performance measure for each value of d, visualize the results with the C-index (y-axis) as a function of d (x-axis).

- Plot of the graph C-index vs. distance parameter value. 


**2. Pain Assessment From Biosignal Data**
--------------
**K-Nearest Neighbor Classification with euclidean distance for pain intensity level prediction using biosignal features.**

<b>Data upload:</b><br>
1. Read data from the open data source https://raw.githubusercontent.com/elmasyr/ada/master/ex3_biovid_subset.csv<br>
Note! Use the url to obtain the data, not a local copy of the file.<br>
2. Check the uploaded data shortly. Note that the file contains more data than the listed features. Make sure you understand what is included in the dataset before proceeding. 

<b>Preprocessing:</b><br>
- 3. Check the two label columns "Label" and "Label_ord" distribution, answer the question 1)--3)
- 4. Check the descriptive statistics of the features, answer the question 4)
- 5. Standarize data using z-score.
- 6. Check the descriptive statistics of the standardized features, answer the question 5)
- 7. Validate the c-index code you use (your own or library version)

<b>Analysis:</b><br>
- 7. With kNN classification (k=29), implement *your own Leave-Subject-Out cross-validation* (do not used ready-made libraries)<br>

- 8. Report the C-index for each subject fold and average performance
- 9. Report also min, max and standard deviation of the C-indices
- 10. Answer the question vi)


**3. Metal Ion Concentration Prediction**
--------------------------
Prediction of the metal ion content from multi-parameter data 
Use K-Nearest Neighbor Regression with euclidean distance to predict total metal concentration (c_total), concentration of Cadmium (Cd) and concentration of Lead (Pb), for each sample using number of neighbors k = 3.

- You may use Nearest Neighbor Regression from https://scikit-learn.org/stable/modules/neighbors.html 
- The data should be standarized using z-score.
- Implement your own Leave-One-Out cross-validation and calculate the C-index for each output (c_total, Cd, Pb). 
- Implement your own Leave-Replicas-Out cross-validation and calculate the C-index for each output (c_total, Cd, Pb).



**4.  Cross-Validation with Symmetric Pair-Input Data using "Exercise 5 data"**
---------------
Assignment consists of two tasks. In both tasks, use the K-nearest neighbors classifier with K=1 and Euclidean distance for learning and the concordance index for evaluation.

**Task 1**
1. Implement the modified leave-one-out cross-validation scheme that is described in the lecture notes.

2. Estimate and report the generalisation performance of the K-nearest neighbor classifier in predicting the functional similarity of proteins. Use both the unmodified and the modified leave-one-out cross-validation.

3. Discuss your results. In particular, answer the following questions:
 - Why do the two cross-validation schemes produce notably different estimates?
 - For which types of pairs (A, B, or C) are these schemes appropriate and why?
 
 **Task 2**
 **Successfully completing this task will give you an extra point in the exam.**

1. Design a leave-one-out cross-validation scheme that is appropriate for the type of pairs that was not covered by the task 1.

2. Explain why your cross-validation scheme is appropriate.

3. Implement your cross-validation scheme. Estimate and report the generalisation performance as in the first task.

4. Discuss your results. In particular, compare the results to those you obtained in the first task and give reasons for any similarities or differences you observe.



**5. Non-Signal Data**
------------


In this exercise you take on the role of a senior data analyst correcting mistakes made by a junior analyst. Your consulting company has received the MysteryData data set, and your goal is to build a classifier out of it, and evaluate how well the classifer works. You assigned the job to junior trainee Tux the Linux Penguin (who works for food).

Tux is very excited to work on the data and has produced very promising results. What Tux does not yet know is that MysteryData is actually just random non-signal data where the features x and the class label y are independent of each other - it is not possible to learn anything meaningful from this data. Tux has never taken any of the UTU data analytics courses and has not noticed this. You should help Tux to correct the analyses, so you do not end up reporting incorrect results to your customers.

The analysed problem is a binary classification task. We will follow the convention of using +1 to represent the positive class, and -1 the negative. In all but one task we will use area under ROC curve (AUC) to evaluate how well the classifier predicts. For binary classification tasks AUC and c-index are equivalent, 0.5 means random performance and 1.0 perfect predictions. The "true" AUC you would expect to see on a large enough sample of independent test data for any classifier trained on non-signal data is 0.5.


