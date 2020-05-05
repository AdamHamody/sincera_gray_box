# Gray Box Classification

This package contains helpful functions/classes for classification. What makes the package comfortable is the ability to perform grid-search in order to  select the optimum data features, hyper-parameters, and classifiers as needed.
There are three feature selection methods, "chi2", "ANOVA F-value","Kullback–Leibler divergence".

## Getting Started

To install the package:\
      pip install gray_box_clf

## Example

->>!pip install gray_box_clf

->> from gray_box_clf.classification_functions import PraperClassified\
->>import numpy as np\
->>from sklearn.svm import SVC\
->>from sklearn.datasets import make_classification

->>X,y = make_classification(random_state=10)\
->>model=PraperClassified(X,y,classifier=[{'cls': SVC( probability=True,), 'name': 'svm'},{'parametrs': {'C': [1,10], 'kernel': ["linear", "rbf"]}}], optimizer='accuracy')
                           
->>model.grid_search(n_features_list=[10, 15, "all"])\
->>model.k_folds()\
->>model.show_roc()\
->>print(model.class_report_)

->>model.best_model_

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Maked by

* Adam H. Agbaria 
