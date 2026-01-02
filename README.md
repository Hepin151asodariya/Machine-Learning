ColumnTransformer is a tool in scikit-learn used to apply different preprocessing steps to different columns of a dataset at the same time.
It is especially useful when your dataset has both numerical and categorical features.

Instead of preprocessing everything separately, ColumnTransformer combines all transformations into one clean pipeline, making the workflow organized, reproducible, and less error-prone.

Why use ColumnTransformer?

Handle numeric and categorical columns differently

Prevent data leakage

Works smoothly with Pipelines

Ideal for real-world ML projects

Small Example
from sklearn.compose import ColumnTransformer
from sklearn.preprocessing import StandardScaler, OneHotEncoder

# column groups
num_cols = ["age", "salary"]
cat_cols = ["gender", "city"]

# ColumnTransformer
preprocessor = ColumnTransformer(
    transformers=[
        ("num", StandardScaler(), num_cols),
        ("cat", OneHotEncoder(), cat_cols)
    ]
)

# apply preprocessing
X_transformed = preprocessor.fit_transform(X)


What happens here?

Numerical columns → scaled

Categorical columns → one-hot encoded

Output → single transformed dataset ready for ML model
