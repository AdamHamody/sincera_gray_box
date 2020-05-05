# Gray Box Classification

This package contains helpful functions/classes for classification

## Getting Started

To install the package:\
      pip install gray_box_clf

## Example

>>!pip install gray_box_clf

>>from gray_box_clf.classification_functions import PraperClassified
>>import numpy as np
>>from sklearn.svm import SVC
>>from sklearn.datasets import make_classification

>>X,y = make_classification(random_state=10)
>>model=PraperClassified(   X,
                            y,
                            classifier=[{'cls': SVC( probability=True,), 'name': 'svm'},
                                        {'parametrs': {'C': [1,10], 'kernel': ["linear", "rbf"]}}],
                            optimizer='accuracy'
                            )
>>model.grid_search(n_features_list=[10, 15, "all"])
>>model.k_folds()
>>model.show_roc()
>>print(model.class_report_)
precision    recall  f1-score   support

           0       0.89      0.92      0.90        51
           1       0.91      0.88      0.90        49

    accuracy                           0.90       100
   macro avg       0.90      0.90      0.90       100
weighted avg       0.90      0.90      0.90       100

>>model.best_model_
Pipeline(memory=None,
         steps=[('feature_selection_method',
                 SelectKBest(k=10,
                             score_func=<function chi2 at 0x7fc43a941400>)),
                ('classifier',
                 SVC(C=1, break_ties=False, cache_size=200, class_weight=None,
                     coef0=0.0, decision_function_shape='ovr', degree=3,
                     gamma='scale', kernel='linear', max_iter=-1,
                     probability=True, random_state=None, shrinking=True,
                     tol=0.001, verbose=False))],
         verbose=False)
## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Maked by

* Adam H. Agbaria 
