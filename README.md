# Wine-Prediction
This is an analysis on kaggle dataset of wine quality. Basic data exploration, feature engineering, and modelling/prediction is implemented. Details are plotted, coded, and explained in Juypter Notebook.

(Summary described below is the same as the summary mentioned in Jupyter Notebook. Jupyter Notebook contains all the visualizations and explanations. 
- Goal: Predict wine quality through other variables(acidity, sugar level, chlorides, sulfur dioxide, density, pH, sulphates, and alcohol)
- EDA
    - created feature engineered values diff acidity(fixed acidity - volatile acidity) and diff dioxide(total sulfur dioxide - free sulfur dioxide), as those values have similarity in measurements. Quantifying the differences might be contributive toward further predictions of wine quality
    - data is already cleaned, no null and extreme/unpractical outliers
    - wine quality is most correlated with volatile acidity and alcohol by heatmap and correlation
        -  "diff dioxide", "total sulfur dioxide", "free sulfur dioxide", "alcohol", and "diff acidity" are selected using SelectkBest
- predictions
    - feature engineer data
        - utilize binarizers(thresholding) and kBinsDiscretizer
        - utilize pipeline to automate and deal with feature engineering coherently
    - RandomForestClassifiers using GridSearchCV and randomSearchCV
        -plot training accuracy and testing accuracy with respect to random_states, max_depth, test_size, and etc
    
    - Support Vector Machines
        - Experiment SVC with linear, rbf, polynomial kernel
            -linear and polynomial kernel doesn't converge, therefore RBF is used
        - Tune Parameters (C, gamma, degree)
            - larger C avoids misclassification and potentially overfits
    - Guassian Naive Bayes
        -Doesn't perform as well as other models mentioned above
    - Stochastic Gradient Descent 
        -Doesn't perform well since increment in number of iterations doesn't improve its accuracy
            
- Conclusion
    - This project is a practice and demo of data science cycle, including Exploratory Data Analysis, Data Engineering, and Data Modelling (machine learning prediction). Due to limitations in domain knowledge, data engineering is restricted and doesn't raise the accuracy by a large amount. Within machine learning prediction, the goal was to predict the level of wine quality, and most of the predictions were accurate. RandomForestClassifier yields the best prediction accuracy, yet the training data sometimes overfit(training accuracy = 1). On the other hand, support vector machine has an accuracy around 85%, yet the training accuracy doesn't excel too much. Gaussian Naive Bayes and Stochastic Gradient Descent Classifier doesn't work well on the data, due to assumptions made on the models and can be inferred by the plots being drawn. Further research is required to make better engineered feature and optimize model through parameter tuning.<br> **Below are detailed descriptions,code, and plots of my work**
