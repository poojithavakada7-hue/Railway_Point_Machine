#  Railway Point Machine Predictive Maintenance Using Machine Learning

##  Project Overview

The **Railway Point Machine Predictive Maintenance System** is a Machine Learning project designed to predict whether a railway point machine requires maintenance based on operational and sensor parameters.

The project uses the **XGBoost classification algorithm** to analyze railway point machine data and predict maintenance requirements. A user-friendly web interface is developed using **Gradio**, allowing users to enter sensor readings and obtain predictions without directly interacting with the machine learning code.

The main objective is to support predictive maintenance, identify potential machine problems earlier, and reduce unexpected equipment failures.

##  Objectives

* Develop a Machine Learning model for railway point machine maintenance prediction.
* Use XGBoost for binary classification.
* Reduce the number of inputs required from users.
* Evaluate the model using Accuracy, Precision, Recall, and F1 Score.
* Build an interactive web interface using Gradio.
* Save and reuse the trained model using Joblib.
* Provide a foundation for future railway maintenance monitoring systems.

##  Technologies Used

| Technology   | Purpose                                 |
| ------------ | --------------------------------------- |
| Python       | Programming language                    |
| Pandas       | Dataset processing                      |
| NumPy        | Numerical operations                    |
| Scikit-learn | Data splitting and model evaluation     |
| XGBoost      | Machine Learning classification         |
| Joblib       | Saving and loading the trained model    |
| Gradio       | Interactive web interface               |
| Google Colab | Model training and experimentation      |
| GitHub       | Source code and project version control |

##  Dataset Description

The project uses a railway point machine dataset containing operational and sensor-related parameters.

The original dataset includes features such as:

* Operational Mode
* Season
* Ambient Temperature
* Humidity
* Supply Voltage
* Inrush Current
* Steady-State Current
* Peak Current
* Throw Time
* Throw Force
* Lock Displacement
* Track Vibration
* Acoustic Noise
* Motor Temperature
* Throw Energy
* Fault Class

**Target variable:** `Maintenance_Required`

The target indicates whether maintenance is required for the machine.

The project uses a dataset containing approximately **200K records**.
Data set name is **railway_point_machine_200k** Taken from the **Kaggle**

##  Selected Input Features

To make the application simple and user-friendly, the model uses **Six** selected inputs:

1. **Throw Time (ms)** - Time taken by the machine to complete its movement.
2. **Steady-State Current (A)** -  Current consumed by the motor during normal operation.
3. **Track Vibration (Hz)** - Vibration frequency that may indicate mechanical issues.
4. **Motor Temperature (°C)** - Motor temperature that helps identify overheating.
5. **Ambient Temperature (°C)** - Temperature of the surrounding environment.
6. **Season** - Season during operation that may affect machine performance.
These parameters are used as inputs to the trained model. Their usefulness should be validated against the dataset and real-world railway engineering knowledge before operational deployment.

##  Machine Learning Algorithm

The project uses **XGBoost (Extreme Gradient Boosting)**, an ensemble learning algorithm based on decision trees.

XGBoost builds multiple trees sequentially, with each new tree helping improve the model's predictions.

### Workflow

1. Load the railway point machine dataset.
2. Select the relevant sensor features and target column.
3. Handle missing values where necessary.
4. Divide the data into training and testing sets.
5. Train the XGBoost classification model.
6. Generate predictions for unseen test records.
7. Evaluate model performance.
8. Save the trained model using Joblib.
9. Load the model into the Gradio application.
10. Accept user inputs and display the prediction.

##  Model Evaluation

The model is evaluated using the following metrics:

* **Accuracy:** Percentage of correctly classified test samples.
* **Precision:** Percentage of predicted maintenance cases that are actual maintenance cases.
* **Recall:** Percentage of actual maintenance cases identified by the model.
* **F1 Score:** Harmonic mean of Precision and Recall.

The project aims to achieve performance metrics between **95% and 98%**. Actual results must be measured on an appropriately separated test set and reported accurately.

##  Application Features

* Interactive Gradio web interface.
* Simple input fields for three sensor parameters.
* Prediction of maintenance requirements.
* Display of maintenance probability.
* Reusable trained XGBoost model.
* Model performance evaluation.
* Lightweight interface suitable for demonstration and experimentation.

### Example Output

```text
Railway Point Machine Prediction

Throw Energy: 1500
Throw Time: 3800
Inrush Current: 9.5

Prediction: Maintenance Required
Maintenance Probability: Model-generated result
```

*The values above are illustrative. The actual result depends on the trained model and input values.*

## Trained Model

The trained model is saved as:

`railway_point_machine_xgboost.joblib`

The saved package contains the trained XGBoost model, selected feature names, target name, and evaluation metrics.

The Gradio application loads this file to make predictions without retraining the model every time.


##  Future Enhancements

* Integrate real-time sensor data.
* Add fault classification alongside maintenance prediction.
* Store prediction history in a database.
* Display sensor trends and maintenance dashboards.
* Develop a REST API for integration with Android applications.
* Deploy the Gradio interface to Hugging Face Spaces.
* Validate the model using real railway point machine data.
* Add model monitoring and retraining capabilities.

##  Limitations

This project is a machine learning prototype intended for experimentation and demonstration. Model predictions are dependent on the quality and representativeness of the training data.

The predicted probability is not necessarily a calibrated measure of real-world failure risk. The model must be validated using independent, representative operational data before being considered for actual railway maintenance decisions.

The application should not replace railway engineering inspections, established safety procedures, or qualified maintenance personnel.

##  Project Summary

This project demonstrates how Machine Learning can be applied to railway point machine predictive maintenance. By combining XGBoost, Python, Joblib, and Gradio, it provides an interactive prototype that predicts maintenance requirements from selected sensor parameters.

The project establishes a foundation for further development in intelligent railway monitoring and predictive maintenance.

##  Author

**Name:** Poojitha Vakada
**Project:** Railway Point Machine Predictive Maintenance Using Machine Learning
**Technology:** Python, XGBoost, Gradio
**GitHub:** (https://github.com/poojithavakada7-hue/Railway_Point_Machine)
