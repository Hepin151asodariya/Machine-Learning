✨ What is ColumnTransformer?

ColumnTransformer is a preprocessing tool from scikit-learn that lets you apply different transformations to different columns of a dataset at the same time.

👉 It is mainly used when:

Some columns are numeric (need scaling)

Some columns are categorical (need encoding)

Instead of preprocessing columns separately, ColumnTransformer combines everything into one clean pipeline.

🧠 Why use it?

Keeps preprocessing organized & readable

Prevents data leakage

Works perfectly with pipelines & models

Ideal for real-world datasets

⚙️ How it works (Simple Flow)
Numeric Columns  ──▶ Scaling
Categorical Cols ──▶ One-Hot Encoding
                     ↓
              Combined Feature Matrix

🧪 Small Example
from sklearn.compose import ColumnTransformer
from sklearn.preprocessing import StandardScaler, OneHotEncoder

preprocessor = ColumnTransformer(
    transformers=[
        ("num", StandardScaler(), ["age", "salary"]),
        ("cat", OneHotEncoder(), ["gender"])
    ]
)

X_transformed = preprocessor.fit_transform(X)


✅ Numeric columns are scaled
✅ Categorical columns are encoded
✅ Output is model-ready
