# ML-Classified

This repository is a personal learning workspace for machine learning concepts and implementations.

## Learning Roadmap

This roadmap tracks the topics I'll study and the code/notebooks I create while learning.

- Univariate Linear Regression — `Univariate_Linear_Regression_From_Scratch.ipynb`
- Linear Regression with Multiple Variables (current) — `Linear_Regression_with_Multiple_Variables.ipynb`

Goals:

- Understand algorithms by implementing them from scratch.
- Create small, well-documented notebooks and reusable Python modules.

Progress:

- [x] Univariate Linear Regression — notebook created and explanations improved.
- [x] Linear Regression with Multiple Variables — notebook created and explanations added.

Files to check:

- `Univariate_Linear_Regression_From_Scratch.ipynb` — code and explanations.
- `Linear_Regression_with_Multiple_Variables.ipynb` — multi-feature linear regression with concise explanations and a quick visualization.

## How to run (macOS, zsh)

Use the provided virtual environment if available, then install requirements and open the notebooks.

```bash
# Activate venv (if it already exists in this repo)
source env/bin/activate

# Install dependencies
pip install -r requirement.txt

# Launch Jupyter
jupyter notebook
```

If you prefer VS Code, open the folder and select the `env` interpreter for the notebooks.

Next steps:

- Create `topics/linear_regression/` and add a script-based implementation (`src/linear_regression.py`).
- Add tests under `tests/`.
