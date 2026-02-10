# B-Cell-Epitope-Prediction

📌 Project Overview

This project presents a comprehensive data science and machine learning pipeline for the prediction of B-cell epitopes based on physicochemical and structural properties of peptide sequences. The main objective is to identify epitope candidates efficiently, reducing experimental time and cost while prioritizing sensitivity toward immunologically relevant regions.

Given the biological relevance of epitope detection, the problem is formulated as a binary classification task, where the primary focus is placed on minimizing false negatives.

🎯 Objectives

Develop predictive models to classify epitopes vs. non-epitopes

Perform extensive exploratory data analysis (EDA) to understand biological patterns

Apply feature engineering guided by immunological knowledge

Evaluate multiple supervised and unsupervised learning techniques

Prioritize recall of the positive class (epitopes) over global accuracy

Compare model performance in terms of predictive power and computational cost

📊 Dataset Description

The data used in this project were obtained from the Immune Epitope Database (IEDB) and consist of peptide- and protein-level information.

Data Files

input_bcell.csv: Main training dataset (14,387 rows, 14,362 peptides, 757 proteins)

input_sars.csv: Additional training dataset (520 rows)

input_covid.csv: Target dataset without labels (used for prediction)

Key Variables

Peptide-level features:
chou_fasman, emini, kolaskar_tongaonkar, parker

Protein-level features:
isoelectric_point, aromaticity, hydrophobicity, stability

Positional and sequence features:
peptide_length, relative_position

Target variable:
target (epitope vs. non-epitope)


🧠 Modeling Approach
Supervised Models Evaluated

Logistic Regression (baseline)

Random Forest

Random Forest (GridSearchCV optimized)

XGBoost (GridSearchCV optimized)

Multilayer Perceptron (MLP)

Unsupervised Learning

Hierarchical Clustering (Ward and Complete linkage)

Cluster labels used as additional features

Evaluation Metrics

Recall (positive class – epitopes) (primary metric)

F1-score

ROC-AUC

Confusion Matrix

🏆 Results Summary
Model	Recall (Epitope)	F1-score	AUC	Training Time
Random Forest (GSCV)	0.744	0.87	0.92	~1124 s
XGBoost (GSCV)	0.683	0.867	0.92	~929 s
Random Forest	0.658	0.865	0.93	Low
MLP	Lower	Lower	Lower	Very High
Logistic Regression	Poor	Poor	Low	Very Low
⭐ Best Model

The Random Forest optimized via GridSearchCV was selected as the best-performing model, achieving the highest recall for epitopes while maintaining strong overall performance.

🧬 Conclusions

This project demonstrates that tree-based ensemble models, combined with biologically informed feature engineering, provide a robust framework for B-cell epitope prediction. The selected model effectively prioritizes epitope detection, making it a valuable tool for computational immunology and vaccine research.

Future improvements may include:

Additional feature engineering

Expanded hyperparameter searches

Inclusion of epitope data from related viruses

Further strategies to address class imbalance

🛠️ Technologies Used

Python

Pandas, NumPy

Scikit-learn

XGBoost

Matplotlib, Seaborn

👤 Author

Jose F. Drube
Biologist | Data Science | Machine Learning
