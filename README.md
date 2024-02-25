TechProject - 2
------------

This project have multiple notebooks, each with a specific scope. The idea is to simplify the analysis and make it easier to follow.
All notebooks cross-reference each other, accordingly to the flow of the analysis. Using magic runs, such as: `%run 'notebooks/data_collection.ipynb'`

#### Notebooks/

* [supervisor.ipynb](notebooks/supervisor.ipynb)
* [data_loader](notebooks/data_loader.ipynb)
* [Task_2_Bagging.ipynb](notebooks/Task_2_Bagging.ipynb)
* [Task_2_Boosting.ipynb](notebooks/Task_2_Bagging.ipynb)
* [Task_2_Stacking.ipynb](notebooks/Task_2_Stacking.ipynb)

##### Feature Engineering

* [LassoCV.ipynb](notebooks/FeatureEngineering/LassoCV.ipynb)
* [PCA.ipynb](notebooks/FeatureEngineering/PCA.ipynb)
* [GeneticAlgorithms.ipynb](notebooks/FeatureEngineering/GeneticAlgorithms.ipynb)
  * `Not fully implemented yet`

##### Hyperparameter Tuning

* [GridSearchCV.ipynb](notebooks/HyperparameterTuning/GridSearchCV.ipynb)
* [Bayesian_optimization.ipynb](notebooks/HyperparameterTuning/Bayesian_optimization.ipynb)
  * `Not fully implemented yet`

### Diagrams of Ensemble Methods used

![bagging_regressor_diagram.jpg](documents%2Fimages%2Fbagging_regressor_diagram.jpg)
![gradient_boosting_diagram.jpg](documents%2Fimages%2Fgradient_boosting_diagram.jpg)
![voting_regressor_diagram.jpg](documents%2Fimages%2Fvoting_regressor_diagram.jpg)
![stacking_diagram.jpg](documents%2Fimages%2Fstacking_diagram.jpg)

### Feature Engineering with LassoCV 

![lasso_coefficient.png](documents%2Fimages%2Flasso_coefficient.png)


### Metrics and Evaluation Across Ensemble Methods

![performance_metrics_table.png](documents%2Fimages%2Fperformance_metrics_table.png)

### Final metrics Plots after Feature Engineering and Hyperparameter Optimizations


![regressor_predictions_avg.png](documents%2Fimages%2Fregressor_predictions_avg.png)

![metrics_performance_scores_bar.png](documents%2Fimages%2Fmetrics_performance_scores_bar.png)

![metrics_performance_scores_line.png](documents%2Fimages%2Fmetrics_performance_scores_line.png)


### References to the libraries and functions used in this project

* **Feature Engineering**
  * [PCA](https://scikit-learn.org/stable/modules/generated/sklearn.decomposition.PCA.html)
  * [DEAP](https://deap.readthedocs.io/en/master/index.html)
    * DEAP is a novel evolutionary computation framework for rapid prototyping and testing of ideas.
    * [overview](https://deap.readthedocs.io/en/master/overview.html)
  * [Pandas astype('category')](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.astype.html)
  * [scikit-optimizer](https://scikit-optimize.github.io/stable/auto_examples/sklearn-gridsearchcv-replacement.html)


* **Stacking**
  * [Stacking Regressor](https://scikit-learn.org/stable/modules/ensemble.html#stacking)
  * [KNeighbors Regressor](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsRegressor.html#sklearn.neighbors.KNeighborsRegressor)
* **Boosting**
  * [Gradient Boosting Regressor](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.GradientBoostingRegressor.html#sklearn.ensemble.GradientBoostingRegressor)
* **Bagging**
  * [Bagging Regressor](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.BaggingRegressor.html#sklearn.ensemble.BaggingRegressor)
  * [Random Forest Regressor](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestRegressor.html#sklearn.ensemble.RandomForestRegressor)


* **Evaluation and Estimatiors**
  * [cross_val_score](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.cross_val_score.html)
  * [cross-validation](https://scikit-learn.org/stable/modules/cross_validation.html#cross-validation)
  * [RidgeCV](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.RidgeCV.html#sklearn.linear_model.RidgeCV)
  * [LassoCV](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LassoCV.html#sklearn.linear_model.LassoCV)
  * [KFold](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.KFold.html)


* **Metrics**
  * [r2_score](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.r2_score.html)
  * [mean_squared_error](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.mean_squared_error.html)
  * [variance_score](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.explained_variance_score.html)

* References:
  * [Alibrahim, H. and Ludwig, S.A., 2021, June. Hyperparameter optimization: Comparing genetic algorithm against grid search and bayesian optimization. In 2021 IEEE Congress on Evolutionary Computation (CEC) (pp. 1551-1559). IEEE.](https://ieeexplore.ieee.org/abstract/document/9504761)
  * [Maclin, R. and Opitz, D., 1997. An empirical evaluation of bagging and boosting. AAAI/IAAI, 1997, pp.546-551.](https://citeseerx.ist.psu.edu/document?repid=rep1&type=pdf&doi=ff298c9ad0aaf574219cb9d470a0ff9ef2f8f3ce)
