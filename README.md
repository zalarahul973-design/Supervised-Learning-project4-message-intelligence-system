![Uploading gif3s.gif…]() 


🚀 Project 4 — KNN, SVM & Naive Bayes
A Machine Learning classification project to detect whether a message is Spam or Not Spam (Legitimate).
This project implements and compares three classification algorithms:
•	🔵 K-Nearest Neighbors (KNN)
•	🟢 Support Vector Machine (SVM)
•	🟠 Naive Bayes
The project also covers data preprocessing, feature scaling, probability, Bayes Theorem, model evaluation, misclassified messages, support vectors, and model comparison.
________________________________________
📌 Project Objective
The main objective of this project is to build a Machine Learning system that can classify messages into:
0 → Legitimate / Not Spam
1 → Spam
The project compares different Machine Learning algorithms and evaluates their performance using:
•	Accuracy
•	Precision
•	Recall
•	F1 Score
________________________________________
📂 Dataset
Dataset Name
Msg_Intelligence_Datasetpro4.csv
Dataset Size
Total Records: 5,200
Input Features: 7
Target Variable: spam_label
The notebook selects the following 7 features for Machine Learning:
Feature	Description
message_length	Length of the message
num_special_chars	Number of special characters
num_urls	Number of URLs
spam_keyword_score	Spam keyword score
sender_activity_score	Sender activity score
hour_of_day	Hour when message was received
day_of_week	Day of the week
Target
spam_label
0 = Legitimate
1 = Spam
The notebook confirms that the selected feature matrix contains 5,200 rows and 7 columns.
________________________________________
🧠 Project Workflow
                Dataset
                   ↓
             Feature Selection
                   ↓
          Missing Value Checking
                   ↓
            Median Imputation
                   ↓
             Feature Scaling
                   ↓
            Train-Test Split
                   ↓
       ┌───────────┼───────────┐
       ↓           ↓           ↓
      KNN         SVM      Naive Bayes
       ↓           ↓           ↓
       └───────────┼───────────┘
                   ↓
            Model Prediction
                   ↓
          Performance Evaluation
                   ↓
         Probability Analysis
                   ↓
           Model Comparison
                   ↓
          Final Recommendation
________________________________________
📋 Questions Covered: Q6 – Q24
Question	Topic
Q6	Feature Selection & Target Variable
Q7	Data Preprocessing & Scaling
Q8	Train-Test Split
Q9	Implement KNN
Q10	Experiment with Different K Values
Q11	Analyze Distance Metrics
Q12	Identify Misclassified Messages
Q13	SVM – Linear & RBF Kernel
Q14	Margin Separation & Support Vectors
Q15	Compare SVM with KNN
Q16	Implement Naive Bayes
Q17	Conditional Probability
Q18	Bayes Theorem
Q19	Theoretical Probability vs Model Prediction
Q20	Evaluate All Models
Q21	KNN vs SVM vs Naive Bayes
Q22	Best Model for Precision & Recall
Q23	Final Model Performance Report
Q24	Model Comparison Visualization
________________________________________
🔹 Q6 — Feature Selection
The project selects important numerical features from the dataset.
Input Features
message_length
num_special_chars
num_urls
spam_keyword_score
sender_activity_score
hour_of_day
day_of_week
Target
spam_label
The selected data contains:
X Shape = (5200, 7)
y Shape = (5200,)
This means the model uses 7 input features to predict the Spam label.
________________________________________
🔹 Q7 — Data Preprocessing & Scaling
The dataset is checked for missing values.
The notebook found:
sender_activity_score = 106 missing values
The other selected features contain no missing values.
Missing Value Handling
Median imputation is used:
SimpleImputer(strategy="median")
Feature Scaling
StandardScaler is applied:
StandardScaler()
This converts features to a comparable scale, which is especially useful for distance-based algorithms such as KNN.
________________________________________
🔹 Q8 — Train-Test Split
The dataset is divided into:
80% → Training
20% → Testing
The notebook produces:
Training Data: 4160
Testing Data : 1040
stratify=y is used to maintain the class distribution in the training and testing datasets.
Class Distribution
Training:
0 → 3382
1 → 778

Testing:
0 → 845
1 → 195
________________________________________
🔹 Q9 — Implement KNN
The first KNN model uses:
KNeighborsClassifier(n_neighbors=8)
The model is trained using:
knn.fit(X_train, y_train)
and predictions are generated using:
y_pred = knn.predict(X_test)
Result
KNN Accuracy = 1.00
The classification report also shows 1.00 for precision, recall and F1 score for both classes.
________________________________________
🔹 Q10 — Experiment with Different K Values
Different K values are tested:
1, 3, 5, 7, 9, 11, 15, 20
Results
K	Accuracy
1	1.0000
3	1.0000
5	1.0000
7	1.0000
9	1.0000
11	0.9990
15	0.9990
20	0.9971
The highest accuracy in this experiment is obtained with K values from 1 through 9.
________________________________________
🔹 Q11 — Distance Metrics
The project compares three KNN distance metrics:
•	Euclidean
•	Manhattan
•	Minkowski
Results
Distance Metric	Accuracy
Euclidean	1.0000
Manhattan	0.9971
Minkowski	1.0000
Euclidean and Minkowski achieved the highest accuracy in the experiment.
________________________________________
🔹 Q12 — Misclassified Messages
The project identifies incorrectly classified messages using:
wrong = y_test != y_pred
The result is:
Total Misclassified Messages: 0
The notebook also prepares the following information for misclassified records:
message_id
message_text
spam_label
Predicted_Label
No misclassified messages were found for the tested KNN configuration.
________________________________________
🔹 Q13 — SVM
Two SVM kernels are implemented.
Linear SVM
SVC(kernel="linear", random_state=42)
Accuracy
1.00
RBF SVM
SVC(kernel="rbf", random_state=42)
Accuracy
1.00
Both models also produce 1.00 precision, recall and F1 score in the notebook output.
________________________________________
🔹 Q14 — Margin Separation & Support Vectors
The Linear SVM model's support vectors are analyzed.
Support Vectors
Class 0 → 14
Class 1 → 10
Total
24 Support Vectors
Support vectors are the important training observations that define the SVM decision boundary.
________________________________________
🔹 Q15 — SVM vs KNN
The project compares:
•	KNN
•	Linear SVM
•	RBF SVM
Accuracy
Model	Accuracy
KNN	1.00
Linear SVM	1.00
RBF SVM	1.00
All three models achieve the same accuracy in this experiment.
________________________________________
🔹 Q16 — Naive Bayes
Gaussian Naive Bayes is implemented:
GaussianNB()
Result
Naive Bayes Accuracy = 1.00
Precision, recall and F1 score are also 1.00 for the tested data.
________________________________________
🔹 Q17 — Conditional Probability
The project manually calculates:
P(Spam | Number of URLs >= 1)
The result is:
0.66946
or approximately:
66.95%
This means that among messages having at least one URL, the calculated proportion classified as Spam in the dataset is approximately 66.95%.
________________________________________
🔹 Q18 — Bayes Theorem
The project demonstrates Bayes Theorem using:
P(Spam)
P(URL | Spam)
P(URL)
Calculated Values
P(Spam)       = 0.1871
P(URL | Spam) = 0.7390
P(URL)        = 0.2065
Using Bayes Theorem:
P(Spam | URL) = 0.66946
This matches the manually calculated conditional probability from Q17.
________________________________________
🔹 Q19 — Probability Prediction
Naive Bayes is used to generate probability predictions:
probabilities = nb.predict_proba(X_test)
The Spam probability is obtained using:
spam_probability = probabilities[:, 1]
The notebook displays the actual label, predicted label and Spam probability for the first 10 test samples.
Example format:
Actual: 1
Predicted: 1
Spam Probability: 1.0
________________________________________
🔹 Q20 — Evaluate All Models
All three models are evaluated using:
Accuracy
Correct Predictions / Total Predictions
Precision
Correct Spam Predictions / All Predicted Spam
Recall
Correct Spam Predictions / All Actual Spam
F1 Score
Balance between Precision and Recall
Results
Model	Accuracy	Precision	Recall	F1 Score
KNN	1.00	1.00	1.00	1.00
SVM	1.00	1.00	1.00	1.00
Naive Bayes	1.00	1.00	1.00	1.00
These are the recorded notebook results.
________________________________________
🔹 Q21 — KNN vs SVM vs Naive Bayes
A comparison DataFrame is created containing:
Model
Accuracy
Precision
Recall
F1 Score
Final Comparison
Model	Accuracy	Precision	Recall	F1 Score
KNN	1.00	1.00	1.00	1.00
SVM	1.00	1.00	1.00	1.00
Naive Bayes	1.00	1.00	1.00	1.00
Therefore, all three tested models show identical performance on this test split.
________________________________________
🔹 Q22 — Best Model for High Precision & Recall
The notebook automatically searches for the model with the highest:
•	Precision
•	Recall
The recorded result identifies:
Best Model for High Precision: KNN
Precision: 1.00

Best Model for High Recall: KNN
Recall: 1.00
Because all tested models have the same metric values, the max() selection returns KNN first.
________________________________________
🔹 Q23 — Final Model Report
The final report summarizes:
Accuracy
Precision
Recall
F1 Score
The notebook also identifies the best model for each metric.
Recorded Result
Best Accuracy : KNN → 1.00
Best Precision: KNN → 1.00
Best Recall   : KNN → 1.00
Best F1 Score : KNN → 1.00
The notebook also records the following model characteristics.
KNN
Strength: Simple and easy to understand.
Weakness: Sensitive to scaling and choice of K.
SVM
Strength: Strong classification and good decision boundary.
Weakness: Parameter selection can be difficult.
Naive Bayes
Strength: Fast and provides probability estimates.
Weakness: Assumes features are independent.
________________________________________
🔹 Q24 — Model Comparison Visualization
The project creates a bar chart comparing:
Accuracy
Precision
Recall
F1 Score
for:
KNN
SVM
Naive Bayes
The chart title is:
KNN vs SVM vs Naive Bayes
and the Y-axis is limited from:
0 → 1
This provides a visual comparison of the three classification algorithms.
________________________________________
📊 Final Model Comparison
                 Accuracy   Precision   Recall   F1 Score

KNN                 1.00       1.00       1.00      1.00
SVM                 1.00       1.00       1.00      1.00
Naive Bayes        1.00       1.00       1.00      1.00
🏆 Result
All three models achieved:
Accuracy  = 100%
Precision = 100%
Recall    = 100%
F1 Score  = 100%
on the recorded test split.
________________________________________
📌 Important Observation
Although the recorded test results are perfect, real-world Machine Learning performance should not automatically be assumed to be perfect.
The model should be validated on:
•	New unseen data
•	Cross-validation
•	Different train-test splits
•	External datasets
This is especially important before deploying a Spam Detection system in a real application.
________________________________________
💼 Business Recommendation
For Spam Message Detection, both Precision and Recall are important.
High Recall
Helps identify more actual Spam messages.
High Precision
Helps reduce legitimate messages being incorrectly marked as Spam.
Therefore, a practical Spam Detection system should focus on a good balance between:
Precision + Recall
        ↓
    F1 Score
The notebook recommends KNN based on the recorded F1-score selection.
________________________________________
🧠 Naive Bayes Assumption
Naive Bayes assumes that features are conditionally independent given the target class.
In simple words:
Feature 1
Feature 2
Feature 3
   ↓
Assumed to be conditionally independent
   ↓
Naive Bayes Prediction
If features are strongly related, this assumption can affect model performance.
________________________________________
🔍 Interpretability vs Performance
Model	Interpretation
KNN	Easy to understand
Naive Bayes	Easy probability interpretation
SVM	Strong classification but less interpretable
These characteristics are summarized in the project's final report.
________________________________________
🛠️ Technologies Used
Programming Language
🐍 Python
Libraries
Pandas
NumPy
Scikit-learn
Matplotlib
Machine Learning Algorithms
K-Nearest Neighbors
Support Vector Machine
Gaussian Naive Bayes
The notebook imports the required preprocessing, model, metrics and visualization libraries.
________________________________________
📁 Project Structure
Project-4-Spam-Message-Detection/
│
├── 📓 project4(1).ipynb
│
├── 📄 Msg_Intelligence_Datasetpro4.csv
│
└── 📄 README.md
________________________________________
▶️ How to Run
1. Install Python
Make sure Python is installed.
2. Install Libraries
pip install pandas numpy scikit-learn matplotlib
3. Open Jupyter Notebook
jupyter notebook
4. Open Notebook
project4(1).ipynb
5. Keep Dataset in the Same Folder
Msg_Intelligence_Datasetpro4.csv
6. Run All Cells
Run the notebook from Q6 through Q24.
________________________________________
🎓 Learning Outcomes
After completing this project, the following concepts are demonstrated:
•	Feature selection
•	Missing value handling
•	Median imputation
•	Standard scaling
•	Train-test split
•	Stratified splitting
•	KNN classification
•	K-value experimentation
•	Distance metrics
•	Misclassification analysis
•	SVM classification
•	Linear kernel
•	RBF kernel
•	Support vectors
•	Naive Bayes
•	Conditional probability
•	Bayes Theorem
•	Probability prediction
•	Accuracy
•	Precision
•	Recall
•	F1 Score
•	Model comparison
•	Business recommendation
•	Data visualization
________________________________________
🏁 Conclusion
This project demonstrates a complete Machine Learning workflow for Spam Message Detection.
The project starts with feature selection and preprocessing, followed by KNN, SVM and Naive Bayes classification.
Probability concepts are also connected with Machine Learning through Conditional Probability and Bayes Theorem.
Based on the recorded test results:
KNN          → 100%
SVM          → 100%
Naive Bayes  → 100%
for Accuracy, Precision, Recall and F1 Score.
The project successfully demonstrates how multiple Machine Learning algorithms can be trained, evaluated, compared and interpreted for a binary classification problem.
________________________________________
👨‍💻 Author
ZALA RAHULBHAI AMBALAL
Project
Spam Message Detection using Machine Learning
Algorithms
KNN
SVM
Naive Bayes
Skills Demonstrated
Python
Pandas
NumPy
Scikit-learn
Matplotlib
Machine Learning
Data Preprocessing
Classification
Probability
Model Evaluation
________________________________________
⭐ Project Highlights
📊 5,200 Messages
🔢 7 Machine Learning Features
🤖 3 Classification Algorithms
📈 4 Evaluation Metrics
🧮 Conditional Probability
📐 Bayes Theorem
📊 Model Comparison
🏆 Best Model Analysis
________________________________________
⭐ If you find this project useful, please give the repository a Star!
Machine Learning Project | Spam Message Detection | KNN | SVM | Naive Bayes


