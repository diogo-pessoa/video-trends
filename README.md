TechProject1
------------

### Introduction

### Notebooks description

This project have multiple notebooks, each with a specific scope. The idea is to simplify the analysis and make it easier to follow.
All notebooks cross-reference each other, accordingly to the flow of the analysis. Using magic runs, such as: `%run 'notebooks/data_collection.ipynb'`

#### Notebooks/

  * [supervisor](notebooks/supervisor.ipynb) - One to rule them all!
    * Calls notebooks in order to run the full analysis. Handy as I don't need to re-run previous steps, when I need to re-run subsets of the analysis.

### Questions

#### Using the Notebook

Here are a few important points:
* Using `dotenv` to load certain environment variables, without explicity declaring sensitive information in the notebook.
* Python version is 3.9
  * I loaded a virtual environment and had the dependencies listed here: [requirements.txt](requirements.txt)
    * Install venv: `python -m venv venv` (make sure to run this using python3.9
    * Activate the virtual environment: `source venv/bin/activate`
    * Install dependencies:  `pip install -r requirements.txt`
  * Create a `.env` file:
    * for now the only required entry is the `IMAGE_PATH`. This is the path to save plot figures and load then to our LaTeX report.
      * The `.env` file should be in the root of the project.
        * Example:
          ```dotenv
             IMAGES_PATH='../Reports/TechReport/images/'
             DATA_COLLECTION_DIR='../data/'
          ```
  * PySpark preset Schema for Divvy Trip Data:
    * The schema example is defined in the [divvy-tripdata-schema.yaml](documents/divvy-tripdata-schema-example.yaml).
      * Copy this file to the DATA_COLLECTION_DIR and rename it to `divvy-tripdata-schema.yaml`
      * The function [`load_divvy_trip_data`](divvy_bike_share_data_analysis/utils_pyspark.py#L51) will use this file to create a PySpark StructType object.

##### Pylint & Unit Tests

* Pylint
  * The project uses pylint to check the code for errors and style issues.
  * To run pylint, use the following command:
    * `pylint $(git ls-files '*.py') `
* Unit Tests
  * The project uses the `unittest` module to run tests.
  * To run the tests, use the following command:
    * `python -m unittest discover -s tests/ -p '*_test.py'`


#### DataSet Schema

```yaml
data_set: divvy-tripdata
version: 1.0.0
description: Divvy trip data
columns:
  ride_id: string
  rideable_type: string
  started_at: datetime
  ended_at: datetime
  start_station_name: string
  start_station_id: string
  end_station_name: string
  end_station_id: string
  start_lat: float
  start_lng: float
  end_lat: float
  end_lng: float
  member_casual: string
```

### Supporting module divvy_bik_share_data_analysis

The module [divvy_bik_share_data_analysis](divvy_bik_share_data_analysis.py) is intended to simplify the notebook with
the analysis. By removing the initial data loading and csv parsing from the notebook, the notebook content focus on
pyspark DataFrames.

Functions in the module:
<Draft>

### References and links to resources used

* [Divvy Data](https://divvybikes.com/system-data)
* [Divvy Data License](https://www.divvybikes.com/data-license-agreement)
* [Confusion Matrix scikit-learn user-guide](https://scikit-learn.org/stable/modules/model_evaluation.html#confusion-matrix)
* [Sillhoute index Analysis scikit-learn](https://scikit-learn.org/stable/auto_examples/cluster/plot_kmeans_silhouette_analysis.html)
* [PCA scikit-learn](https://scikit-learn.org/stable/auto_examples/decomposition/plot_pca_iris.html#sphx-glr-auto-examples-decomposition-plot-pca-iris-py)
* [PCA Towards Science article PCA discussion](https://towardsdatascience.com/a-one-stop-shop-for-principal-component-analysis-5582fb7e0a9c)
* [Optimal K=n for kmeans clustering ML tutorial](https://pub.towardsai.net/get-the-optimal-k-in-k-means-clustering-d45b5b8a4315)**
* PySpark Functions:
    * [udf](https://spark.apache.org/docs/3.1.3/api/python/reference/api/pyspark.sql.functions.udf.html)
    * [dayofweek](https://spark.apache.org/docs/3.1.3/api/python/reference/api/pyspark.sql.functions.dayofweek.html)
    * [hour](https://spark.apache.org/docs/3.1.3/api/python/reference/api/pyspark.sql.functions.hour.html)
    * [col](https://spark.apache.org/docs/3.1.3/api/python/reference/api/pyspark.sql.functions.col.html)
* [PySpark StructType](https://spark.apache.org/docs/3.1.3/api/python/reference/api/pyspark.sql.types.StructType.html#pyspark.sql.types.StructType)
* [PySpark SQL User-guides](https://spark.apache.org/docs/latest/sql-programming-guide.html)
* [PySpark MLlib User-guides](https://spark.apache.org/docs/latest/ml-guide.html)
* [PySpark Functions User-guides](https://spark.apache.org/docs/3.1.2/api/python/user_guide/arrow_pandas.html#pandas-udfs-a-k-a-vectorized-udfs)
* [PySpark Pipeline](https://spark.apache.org/docs/latest/api/python/reference/api/pyspark.ml.Pipeline.html)
* [Spark ML Lib Pipeline main guide](https://spark.apache.org/docs/latest/ml-pipeline.html)

* Referenced articles:
  * [Traffic prediction in a bike-sharing system](https://dl.acm.org/doi/abs/10.1145/2820783.2820837)
  * [Bicycle-Sharing System Analysis and Trip Prediction](https://ieeexplore.ieee.org/abstract/document/7517792)
  * [Bike-sharing systems: Accessibility and availability](https://www.sciencedirect.com/science/article/pii/S0965856419301063)
