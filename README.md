# Machine Learning Model Trainer

This project focuses on developing and deploying a machine learning pipeline to predict target variables using various regression models. The goal is to identify the best-performing model based on evaluation metrics and save it for future use.

## Table of Contents

- [Project Overview](#project-overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Evaluation](#evaluation)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)

## Project Overview

The project involves training and evaluating multiple regression models on a given dataset to predict a target variable. The models included are Linear Regression, Lasso, Ridge, ElasticNet, and Decision Tree Regressor. The best-performing model is identified based on R² score and saved for future predictions.

## Features

- Developed and deployed a machine learning pipeline with models including Linear Regression, Lasso, Ridge, ElasticNet, and Decision Tree Regressor.
- Achieved a Decision Tree model R² score of 0.92 and an overall pipeline R² score of 0.85.
- Engineered a comprehensive evaluation system for model performance assessment.
- Incorporated robust error handling and logging mechanisms.
- Followed industry practices like pipelining, modular code design, and proper project structuring.

## Installation

To install the required packages, run:

```bash
pip install -r requirements.txt
```

## Usage

1. **Data Preparation**: Ensure your data is formatted correctly and split into training and testing datasets.
2. **Model Training**: Use the `ModelTrainer` class to initiate model training and evaluation.
3. **Model Saving**: The best-performing model is saved automatically to the specified path.

Example:

```python
from src.model_trainer import ModelTrainer

# Assuming train_array and test_array are prepared
model_trainer = ModelTrainer()
model_trainer.initate_model_training(train_array, test_array)
```

## Configuration

The configuration for the project is handled through a data class, `ModelTrainerConfig`, which specifies the path for saving the trained model.

```python
@dataclass
class ModelTrainerConfig:
    trained_model_file_path = os.path.join('artifacts', 'model.pkl')
```

## Evaluation

The evaluation of models is conducted using the `evaluate_model` function, which returns a report of R² scores for each model.

```python
from src.utils import evaluate_model

model_report = evaluate_model(X_train, y_train, X_test, y_test, models)
print(model_report)
```

## Results

- Developed and deployed a machine learning pipeline with an overall R² score of 0.85.
- The Decision Tree model achieved the highest R² score of 0.92.

