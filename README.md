# Parkinson-Disease-Prediction-using-ML-Algorithms


Abstract:

Parkinson's disease is a complex and debilitating neurological disorder affecting millions of people worldwide. Early detection of the disease plays a crucial role in providing effective treatment and better management of symptoms. In this article, we explore the potential of various machine learning algorithms, including XGBoost, KNN, SVMs, and Random Forest, to detect the early onset of Parkinson's disease. We utilize a valuable dataset available from the UCL Parkinson Data-set to train and evaluate these algorithms.

Motivation:

The impact of Parkinson's disease on a person's quality of life can be profound, making early detection a matter of utmost importance. Timely diagnosis allows for prompt medical intervention, enabling healthcare professionals to implement appropriate treatment strategies and improve the overall prognosis for patients. With the rising prevalence of Parkinson's disease on a global scale, there is an increasing need for accurate and efficient methods to detect its early onset.

Machine learning algorithms hold great promise in addressing this challenge, as they can analyze complex patterns in the data and potentially identify subtle indicators of the disease that might not be apparent through traditional diagnostic methods. Leveraging the power of machine learning can revolutionize the early detection of Parkinson's disease and lead to improved patient outcomes.

Introduction:

Parkinson's disease is characterized by a range of motor symptoms, such as tremors, stiffness, and difficulties in body movements. Detecting the disease at an early stage is critical, as it allows for timely medical intervention and significantly enhances the chances of effectively managing the disease progression. However, many existing diagnostic methods can only identify Parkinson's disease at an advanced stage, by which time there is already a substantial loss of dopamine in the basal ganglia, a region responsible for controlling body movements.


link to know about Parkinson Disease:
https://www.analyticsvidhya.com/blog/2021/07/parkinson-disease-onset-detection-using-machine-learning/

DATASET:

Dataset 1:
download link of dataset: 
https://archive.ics.uci.edu/dataset/174/parkinsons

This dataset is composed of a range of biomedical voice measurements from 31 people, 23 with Parkinson's disease (PD). Each column in the table is a particular voice measure, and each row corresponds one of 195 voice recording from these individuals ("name" column). The main aim of the data is to discriminate healthy people from those with PD, according to "status" column which is set to 0 for healthy and 1 for PD. 
The data is in ASCII CSV format. The rows of the CSV file contain an instance corresponding to one voice recording. There are around six recordings per patient, the name of the patient is identified in the first column.

Additional Information

Matrix column entries (attributes):
name - ASCII subject name and recording number
MDVP:Fo(Hz) - Average vocal fundamental frequency
MDVP:Fhi(Hz) - Maximum vocal fundamental frequency
MDVP:Flo(Hz) - Minimum vocal fundamental frequency
MDVP:Jitter(%),MDVP:Jitter(Abs),MDVP:RAP,MDVP:PPQ,Jitter:DDP - Several measures of variation in fundamental frequency
MDVP:Shimmer,MDVP:Shimmer(dB),Shimmer:APQ3,Shimmer:APQ5,MDVP:APQ,Shimmer:DDA - Several measures of variation in amplitude
NHR,HNR - Two measures of ratio of noise to tonal components in the voice
status - Health status of the subject (one) - Parkinson's, (zero) - healthy
RPDE,D2 - Two nonlinear dynamical complexity measures
DFA - Signal fractal scaling exponent
spread1,spread2,PPE - Three nonlinear measures of fundamental frequency variation

Dataset 2:

3 repetitions for each patient.
PD          : 188 patients
Healthy     : 64  patients
Total       : 252 patients
no. of rows : 756

download link of dataset: https://www.kaggle.com/datasets/dipayanbiswas/parkinsons-disease-speech-signal-features?resource=download

Data Set Information:
The data used in this study were gathered from 188 patients with PD (107 men and 81 women) with ages ranging from 33 to 87 (65.1 ±10.9) at the Department of Neurology in CerrahpaÅŸa Faculty of Medicine, Istanbul University. The control group consists of 64 healthy individuals (23 men and 41 women) with ages varying between 41 and 82 (61.1 ±8.9). During the data collection process, the microphone is set to 44.1 KHz and following the physicianâ€™s examination, the sustained phonation of the vowel /a/ was collected from each subject with 3 repetitions.

Attribute Information:
Various speech signal processing algorithms including Time Frequency Features, Mel Frequency Cepstral Coefficients (MFCCs), Wavelet Transform based Features, Vocal Fold Features and TWQT features have been applied to the speech recordings of Parkinson's Disease (PD) patients to extract clinically useful information for PD assessment.

Preprocessing:
Random sampling : data is split using simple random sampling, which means that the samples are randomly shuffled and divided into training and testing sets. This randomness may lead to different distributions of classes in the training and testing sets, especially if the dataset is imbalanced. In some cases, the test set might have an unrepresentative proportion of one class, leading to potentially higher accuracy.

Stratified sampling:
split using stratified sampling, which ensures that the proportion of classes in the training and testing sets remains similar to the original dataset. This is particularly important when dealing with imbalanced datasets, as it helps the model to be trained on a more balanced representation of classes. However, in cases where the data is not highly imbalanced, stratified sampling might lead to slightly smaller variations in class distribution between the training and testing sets compared to random sampling. This could result in a lower accuracy in some situations.

stratified sampling are expected due to the nature of the stratified split. The stratified sampling aims to maintain the class distribution in both the training and testing sets, which can lead to unequal class sizes in the test set, especially when the original dataset has an imbalanced class distribution.
In the context of Parkinson's disease prediction, when dealing with imbalanced data, stratified sampling is generally preferred over random sampling. Here's why:

Stratified Sampling:
Balances Class Distribution: Stratified sampling ensures that the class distribution in both the training and testing sets is representative of the original dataset. It maintains the proportions of different classes, making it suitable for imbalanced datasets like Parkinson's disease prediction, where one class (e.g., Parkinson's positive) might be significantly smaller than the other (e.g., healthy).

Better Generalization: By preserving the class distribution, stratified sampling helps the model to be exposed to a more balanced representation of classes during training. This allows the model to learn patterns from both the majority and minority classes, leading to better generalization and improved performance on unseen data.

More Reliable Evaluation: When evaluating the model's performance on the test set, stratified sampling ensures that the results are representative of the real-world scenario, where class imbalance might be present. This provides a more reliable estimate of the model's performance.

Random Sampling:
Suitable for Balanced Data: Random sampling is generally suitable when the dataset is balanced, meaning there is an equal representation of classes. In such cases, random sampling ensures that each data point has an equal chance of being included in the training or testing set.

Speed and Simplicity: Random sampling can be computationally faster and simpler to implement, especially for large datasets. When class distribution is not imbalanced, random sampling can still provide reasonable results.

In summary, for Parkinson's disease prediction with an imbalanced dataset, stratified sampling is the better choice. It helps to ensure that the model is trained and evaluated in a way that reflects the real-world class distribution, which can lead to improved performance and better generalization on unseen data.
