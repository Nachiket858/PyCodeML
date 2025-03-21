# PyCodeml

**PyCodeml** is a Python package designed to automate the training, evaluation, and selection of the best-performing machine learning models for regression and classification tasks. It simplifies the process of model training, comparison, and deployment.

## Features
✅ Supports **Regression** and **Classification** tasks  
✅ Evaluates multiple models and selects the best one  
✅ Saves and loads trained models for future use  
✅ Simple and intuitive API  

---

## Installation

You can install PyCodeml using pip:

```sh
pip install pycodeml
```


Usage

1️⃣ Train and Save the Best Model
```sh
import pandas as pd
from PyCodeml.regressor import RegressorTrainer  # For regression tasks

# Load dataset from a CSV file (Ensure "target" column exists)   you can give another name to target col 
df = pd.read_csv("data.csv")

# Initialize and train the model
trainer = RegressorTrainer(df, "target")
best_model = trainer.train_and_get_best_model()

# Save the best model
trainer.save_best_model("best_model.pkl")

```
2️⃣ Load and Use the Saved Model

```sh
import pandas as pd
import numpy as np
from PyCodeml.utils import load_model

# Load the saved model
model = load_model("best_model.pkl")

# Load new data from a CSV file (without target column)
new_data = pd.read_csv("new_data.csv")

# Ensure the new data has the same feature columns as the training data
# (Make sure "new_data.csv" has the same structure as the training dataset)
prediction = model.predict(new_data)

# Print the predictions
print("Predicted Values:", prediction)

```

# Supported Models

## Regression
- Linear Regression  
- Decision Tree Regressor  
- Random Forest Regressor  
- Support Vector Machine (SVR)  
- Gradient Boosting Regressor  
- Ridge Regression  
- Lasso Regression  
- Elastic Net  

## Classification *(Coming Soon)*
- Logistic Regression  
- Random Forest Classifier  
- Support Vector Machine (SVM)  
- Gradient Boosting Classifier  
- K-Nearest Neighbors (KNN)  

## Contributing
Contributions are welcome! If you’d like to improve this package, feel free to **fork the repository** and submit a **pull request**.  
https://github.com/Nachiket858/PyCodeML