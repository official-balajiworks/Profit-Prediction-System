# Business Profit Predictor

A compact notebook-based project that trains a linear regression model to predict company profit given R&D spend, Administration spend, Marketing spend, and State. The project includes a trained model (`linear_reg_model.pkl`), the original dataset (`company.csv`), and a Jupyter Notebook (`Business Profit Predictor.ipynb`) that demonstrates data preparation, training, evaluation, and a simple Gradio interface for predictions.

## What's included

- `Business Profit Predictor.ipynb` — main notebook with end-to-end steps: data loading, preprocessing (log transform + one-hot State encoding), model training (Linear Regression), evaluation, and a Gradio demo.
- `company.csv` — the dataset used to train the model.
- `linear_reg_model.pkl` — the trained Linear Regression model saved using pickle.

## Dependencies

You can use Python 3.8+ (3.10 is a good option). Install the main dependencies with pip:

```powershell
pip install pandas numpy scikit-learn gradio
```

If you use a virtual environment (recommended):

```powershell
python -m venv .venv; .\.venv\Scripts\Activate.ps1
pip install pandas numpy scikit-learn gradio
```

## Run the notebook

Open `Business Profit Predictor.ipynb` in Jupyter or VS Code and run the cells sequentially. The notebook will:

1. Load `company.csv` and inspect data
2. Preprocess (handle missing values, one-hot encode `State`, log-transform numeric features)
3. Split into train/test sets and train a Linear Regression model
4. Save the trained model to `linear_reg_model.pkl`
5. Define a `predict_profit` helper function and launch a Gradio UI for interactive predictions

## Use the saved model programmatically

The notebook defines a `predict_profit` function that:
- Loads `linear_reg_model.pkl`
- Accepts: `rd_spend`, `administration`, `marketing_spend`, `state` (one of: `New York`, `California`, `Florida`)
- Returns the predicted profit in the original scale.

You can import or copy the function into a script/notebook and call it directly.

## Run the Gradio demo (from the notebook)

Run the cells that create and launch the Gradio interface. If running inside a notebook cell, the demo will start and provide a shareable link.

## Notes

- The model expects input features in the same order and pre-processing used during training: `R&D Spend`, `Administration`, `Marketing Spend`, `State_California`, `State_Florida`, `State_New York` (the notebook handles this internally).
- The notebook uses a log transform on numeric features and on the target (Profit) — predictions are inverse-transformed back to the original scale.

## License & Credits

This repository was created as a simple educational demo. Adapt and reuse it freely.

---

If you'd like, I can also:
- Add a requirements.txt or pyproject.toml, or
- Add a small Python script to run predictions from the command line.

Tell me what you'd prefer next.