# Machine Learning
Documenting the process...
ANOMALY DETECTION

Anomaly detection (aka outlier analysis) is a step in data mining that identifies data points, events, and/or observations that deviate from a dataset's normal behavior1. Anomaly detection is applicable in domains such as fraud detection, intrusion detection, a structural defect, medical problems or errors in a text2 etc.
Broad categories of Anomaly detection include:
i)	Unsupervised Anomaly detection: detect anomalies in an unlabeled test data set under the assumption that the majority of the instances in the data set are normal by looking for instances that seem to fit least to the remainder of the data set e.g K-Means, Unsupervised Neural Networks, Fuzzy C-Means etc.
ii)	Supervised Anomaly detection: techniques require a data set that has been labeled as "normal" and "abnormal" and involves training a classifier e.g K-Nearest Neighbor, Support Vector Machine, Decision Tree etc.
iii)	Semi-supervised Anomaly detection: construct a model representing normal behavior from a given normal training data set, and then seeks to identify an unlabeled data during inference.

A). BRIEF SUMMARY OF THE DATA SET CHOSEN:
The dataset chosen is a Breast Cancer Diagnostic cell data available on the website of the University of California, Irvine Machine Learning Repository (http://archive.ics.uci.edu/ml/index.php ). The repository hosts 599 data sets ranging across different fields. The Breast cancer dataset includes properties of cancer cells for 699 cases, with 458 benign (65.5%) and 241 (34.5%) malignant cases.

B). HOW DATA WAS COLLECTED:
Data was collected by downloading the csv dataset from UC Irvine’s repository. The breast cancer dataset consists of cell information for 699 cases. The attributes (cell information collected) includes: 
i)	ID- Patient Identifier
ii)	Clump- Clump Thickness
iii)	UnifSize- Uniformity of Cell Size
iv)	MargAdh- Marginal Adhession
v)	SingEpiSize- Single Epithelial Cell Size
vi)	BareNuc- Bare Nuclei
vii)	Bland Chrom- Bland Chromatin
viii)	Norm Nucl- Normal Nucleoli
ix)	Mit- Mitoses
x)	Class- #2 for Benign and #4 for Malignant.

C). ALGORITHM USED:
Support Vector Machine (SVM) was used for the training and classification. SVM is a form of supervised machine learning technique used for both classification and regression purposes. SVM was to used to build and train model using human cell records and further classify the cells into two classes which includes benign (non- cancerous) and malignant (cancerous).
SVM works by mapping data to a high-dimensional feature space so that data points can be categorized even when data points are not linearly separable. This is achieved by the kernel function of the SVM. SVM can handle outliers, misclassifications and overlapping classifications. 

D). EXPERIMENTAL SETUP
The dataset is processed with the ‘panda’ library using the ‘python’ programming language. The loaded CSV file contained 9 missing values in the ‘BareNuc’ attribute. The missing values were replaced with the median values for the attribute. Also the ‘ID’ attribute was dropped as it has no effect on the operation of the SVM. 100 cases of the dataset was expunged and used for inference while 599 cases was used in training and testing of the SVC algorithm.
The ‘Sklearn’ library was used to split dataset (using a split size of 80/20), classify data and provide classification report. Also, a linear ‘kernel’ was used.

E). RESULTS
A validation accuracy of 97% was obtained as shown in fig 1. Also, Benign cases (#2) were predicted better (precision accuracy of 99%) than Malignant cases (#4) with (precision accuracy of 96%). Also, when we used a different dataset for inference, the inference accuracy was 92% with Benign cases being better predicted (precision=100%) than Malignant cases (precision=84%)

Also, the dataset was applied to Decision Tree Machine Learning algorithm and a validation accuracy of 92.5% was obtained. However, when a new dataset was applied for inference. The inference accuracy was 74.26% as shown in figure 3 and figure 4. While it is difficult to categorically say a Machine Learning classifier is better than another, it is safe to say that the choice of dataset would determine the performance of the Algorithm. For our choice of dataset (Breast Cancer Diagnostic cell data), SVM performed better than Decision tree Algorithm. This could be associated with the ‘kernel’ trick which easily converts a linearly inseparable problem to a linearly separable one.
  
F). STRENGTH and WEAKNESS of SVM: The major strengths of SVM are the training is relatively easy. No local optimal, unlike in neural networks. It scales relatively well to high dimensional data and the trade-off between classifier complexity and error can be controlled explicitly. The weakness includes the need for a good kernel function as an inappropriate choice of kernel function would reduce the accuracy of the classifier3.

G). REFERENCES
1)	Liu, Fei Tony; Ting, Kai Ming; Zhou, Zhi-Hua (December 2008). Isolation Forest. 2008 Eighth IEEE International Conference on Data Mining. pp. 413-422. doi: 10.1109/ICMD.2008.17. ISBN 9780769535029.   

2)	 Zimek, Arthur; Schubert, Erich (2017), "Outlier Detection", Encyclopedia of Database Systems, Springer New York, pp. 1-5, doi:10.1007/978-1-4899-7993-3_80719-1, ISBN 9781489979933

3)	Tutorial slides by Andrew Moore. Http://www.cs.cmu.edu/~awm

4)	V. Vapnik. The Nature of Statistical Learning Theory. Springer, N.Y., 1995. ISBN 0-387-94559-8.

5)	Burges C., “A tutorial on support vector machines for pattern recognition”, In “Data Mining and Knowledge Discovery”. Kluwer Academic Publishers, Boston, 1998, (Volume 2).
