# Fastreport

Get report of different metrices  for classification and regression problem for many popular algorithms with single line of code, passing only features(dataframe) and target(series) as arguments


Link to [PyPI](https://pypi.org/project/fastreport/)

Link to [Classification detailed example](https://github.com/kishore-s-gowda/fastreport/blob/master/Classification%20example.ipynb)

Link to [Regression detailed example](https://github.com/kishore-s-gowda/fastreport/blob/master/Regression%20Problem.ipynb)


## Installation

Run the following to install:

```python
pip install fastreport
```

## Usage


### Classification

```python
import report


report.report_classification(df_features,df_target,algorithms='default',test_size=0.3,scaling=None,
                             large_data=False,encode='dummy',average='binary',change_data_type = False,
                             threshold=8,random_state=None):
   

```
    parameters
    ----------------------------

    df_features : Pandas DataFrame
    
    df_target : Pandas Series
    
    algorithms : List ,'default'=
                 [LogisticRegression(),
                 GaussianNB(),
                 DecisionTreeClassifier(),
                 RandomForestClassifier(),
                 GradientBoostingClassifier(),
                 AdaBoostClassifier()]
                 The above are the default algorithms, if one needs any specific algorithms, they have to import
                 libraries then pass the instances of alogorith as list
                 For example, if one needs random forest and adaboost only, then pass 
                 
                 algorithms=[RandomForestClassifier(max_depth=8),AdaBoostClassifier()]
                 But, these libraries must be imported before passing into above list like
                 
    
    test_size: If float, should be between 0.0 and 1.0 and represent the proportion of the 
               dataset to include in the test split.
    
    scaling : {'Standard-scalar', 'Min-Max'} or None , default=None
    
    encode : {'dummy','onehot','label'} ,default='dummy'
    
    change_data_type : bool, default=False
                       Some columns will be of numerical datatype though there are only 2-3 unique values in that column,
                       so these columns must be converted to object as it is more relevant.
                       By setting change_data_type= True , these columns will be converted into object datatype
    
    threshold : int ,default=8
                Maximum unique value a column can have
    
    large_data : bool, default=False
                If the dataset is large then the parameter large_data should be set to True, 
                make sure if your system has enough memory before setting Large_data=True
    
                
    average : {'micro', 'macro', 'samples','weighted', 'binary'} or None, default='binary'
    This parameter is required for multiclass/multilabel targets.
    If ``None``, the scores for each class are returned. Otherwise, this
    determines the type of averaging performed on the data:

    ``'binary'``:
        Only report results for the class specified by ``pos_label``.
        This is applicable only if targets (``y_{true,pred}``) are binary.
    ``'micro'``:
        Calculate metrics globally by counting the total true positives,
        false negatives and false positives.
    ``'macro'``:
        Calculate metrics for each label, and find their unweighted
        mean.  This does not take label imbalance into account.
    ``'weighted'``:
        Calculate metrics for each label, and find their average weighted
        by support (the number of true instances for each label). This
        alters 'macro' to account for label imbalance; it can result in an
        F-score that is not between precision and recall.
    ``'samples'``:
        Calculate metrics for each instance, and find their average (only
        meaningful for multilabel classification where this differs from
        :func:`accuracy_score`).
        
    random_state : int, RandomState instance or None, default=None


### Regression

```python
import report

report.report_regression(df_features,df_target,algorithms='default',test_size=0.3,
                      scaling=None,large_data=False,change_data_type=True,encode='dummy',
                      threshold=8,random_state=None):

```
    parameters
    ----------------------------

    df_features : Pandas DataFrame
    
    df_target : Pandas Series
    
     algorithms : List ,'default'=
                 [LinearRegression(),
                 Lasso(),
                 Ridge(),
                 RandomForestRegressor(),
                 GradientBoostingRegressor(),
                 AdaBoostRegressor()]
                 The above are the default algorithms, if one needs any specific algorithms, they have to import
                 libraries then pass the instances of alogorith as list
                 For example, if one needs random forest and adaboost only, then pass 
                 
                 algorithms=[RandomForestRegressor(max_depth=8),AdaBoostRegressor()]
                 But, these libraries must be imported before passing into above list like
                 
    test_size: If float, should be between 0.0 and 1.0 and represent the proportion of the 
               dataset to include in the test split.
    
    scaling : {'Standard-scalar', 'Min-Max'} or None , default=None
    
    encode : {'dummy','onehot','label'} ,default='dummy'
    
    change_data_type : bool, default=False
                       Some columns will be of numerical datatype though there are only 2-3 unique values in that column,
                       so these columns must be converted to object as it is more relevant.
                       By setting change_data_type= True , these columns will be converted into object datatype
    
    threshold : int ,default=8
                Maximum unique value a column can have
                
    large_data : bool, default=False
                If the dataset is large then the parameter large_data should be set to True, 
                make sure if your system has enough memory before setting Large_data=True
                
    random_state : int, RandomState instance or None, default=None


## Future works

1. Optimization
2. Add more functionality

## Drawbacks

1. Not suitable for very large datasets
2. Limited to existing users only

## License

© 2021 KISHORE S
This repository is licensed under the MIT license. See LICENSE for details.
