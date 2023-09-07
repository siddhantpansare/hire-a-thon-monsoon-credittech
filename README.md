# hire-a-thon-monsoon-credittech
Monsoon Credittech Assessment
The conda environment to run the notebook is placed in the DS Test folder under the name monsoon-hire-a-thon.yml as a YAML file
Final Deliverables:
- Predictions:  
    - Final submission file is placed in the DS Test folder under the name submission.csv file.
- Code:
    - The Jupyter Notebook is placed in the DS Test folder under the name feature_engg_model_selectn_experiments.ipynb 
- Solution Description:
    - Initially while examining the data and performing EDA it was found out that more than 80% of the numerical data contained missing values. A set of different experiments for keeping or imputing the missing values were performed. 
    - It was also found out that there were highly correlated numerical features which were dropped to improve model performance. The correlation threshold set is 0.85.
    - Following are the methods used to deal with missing values
        - Using MICE Imputation Technique to impute the data (Imputation)
            - Reason- much more accurate than KNN imputation and Regression based imputation, cutting-edge machine learning technique
            - ML Models used for this technique: 'LogisticRegression','DecisionTree','RandomForest',"AdaBoost",'XGBoost'
                - LogisticRegression :
                    | metric | score |
                    | ------- |------ |
                    |accuracy|	0.700151|
                    |recall|	0.700151|
                    |precision|	0.700151|
                    |roc_auc_score|	0.548747|
                - DecisionTree :
                    | metric | score |
                    | ------- |------ |
                    |accuracy|	0.713767|
                    |recall|	0.713767|
                    |precision|	0.713767|
                    |roc_auc_score|	0.601428|
                - RandomForest :
                    | metric | score |
                    | ------- |------ |             
                    |accuracy|	0.732375|
                    |recall|	0.732375|
                    |precision|	0.732375|
                    |roc_auc_score|	0.610144|
                - AdaBoost :
                    | metric | score |
                    | ------- |------ |
                    |accuracy|	0.730257|
                    |recall|	0.730257|
                    |precision|	0.730257|
                    |roc_auc_score|	0.613491|
                - XGBoost :
                    | metric | score |
                    | ------- |------ |
                    |accuracy|	0.737216|
                    |recall|	0.737216|
                    |precision|	0.737216|
                    |roc_auc_score|	0.617170|

            - XGBoost performance was considered best out of all above

        - Using the Missing Values to build the model and adding an additional boolean feature (contains_missing_value) to the feature set (No Imputation)
            - Reason- Sometimes the missing values also can be used for extracting information from data, no imputation only adding an additional boolean feature (contains_missing_value) to the feature set which tells us if a row has missing value 
            - ML Models used for this technique: 'DecisionTree','XGBoost'
                - DecisionTree: 
                 	| metric | score |
                    | ------- |------ |
                    |accuracy|	0.719818|
                    |recall|	0.719818|
                    |precision|	0.719818|
                    |roc_auc_score|	0.592386|
                - XGBoost
                    | metric | score |
                    | ------- |------ |
                    |accuracy|	0.734796|
                    |recall|	0.734796|
                    |precision|	0.734796|
                    |roc_auc_score|	0.612979|
        - XGBoost performance was considered best out of both above

    - XGBoost with imputation performed the best for the analysis hence the final submission file is modelled with XGboost ML model using MICE imputation technique 


