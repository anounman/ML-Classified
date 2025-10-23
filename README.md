# ML-Classified

This repository is a personal learning workspace for machine learning concepts and hands-on experiments. It contains Jupyter notebooks that implement basic ML algorithms from scratch, TensorFlow/Keras examples, and small experiments used while learning.

## Repository structure (important files / folders)

- `Unsupervise Learning/Classification/` — classification notebooks (e.g., `logistic_regression.ipynb`).
- `Supervise Learning/` — regression notebooks and examples (linear, polynomial).
- `NLP/` — small NLP and forward-prop experiments (e.g., `nlp_tenserflow.ipynb`, `forward_prop.ipynb`).
- `learn/` — assorted notebooks and experiments.
- `env/` — optional virtual environment used during development (contains Python and packages).
- `requirement.txt` — Python dependencies (install with pip).

## Quickstart (macOS, zsh)

1. (Optional) Activate the included venv if you want to reuse the same environment:

```bash
# Activate the repo virtualenv (if present)
source env/bin/activate
```

2. Install dependencies (use the system Python or the venv's pip):

```bash
pip install -r requirement.txt
```

3. Launch Jupyter and open the notebook you want to run (e.g. logistic regression):

```bash
jupyter notebook
# or
jupyter lab
```

4. In VS Code: open the folder, pick the `env` Python interpreter (or your Python interpreter) and open the desired `.ipynb` file.

## Key notebooks and purpose

- `Unsupervise Learning/Classification/logistic_regression.ipynb` — plain-NumPy logistic regression implementation (useful for understanding cost, gradients, regularization).
- `NLP/nlp_tenserflow.ipynb` — small TensorFlow/Keras binary classifier example built with Sequential API.
- `NLP/forward_prop.ipynb` — forward propagation examples (two-layer network) and utilities for visualizing decision boundaries.

If you are debugging model divergence (cost increasing to NaN) in the logistic regression notebook, check the following common causes (see Troubleshooting):

## Troubleshooting (common issues)

- Cost increases / becomes NaN:

  - Learning rate (alpha) is too large — reduce it (try 1e-3 or 1e-2 initially).
  - Features not normalized — apply standardization (zero mean, unit variance) to input features.
  - Regularization implemented incorrectly — make sure you add the derivative of the regularization term to the gradient, and the regularization term to the cost uses lamda/(2\*m).
  - Numerical instability in log/sigmoid — add small epsilon (1e-15) inside log to avoid log(0), and clip probabilities if needed.

- Shape / broadcasting errors:
  - When using matrix multiplication ensure shapes align: X shape should be (m, n) and weights w shape should be (n,) or (n,1) depending on implementation. Transpose appropriately.
  - Be careful with argument order when calling helper functions (e.g., `predict(X, w, b)` not `predict(X, y, w, b)`).

## Small checklist when running a notebook

1. Ensure the correct Python interpreter (the `env` venv if you use it).
2. Run cells in order (top to bottom) to avoid missing imports or variable definitions.
3. Normalize features before training.
4. Start with conservative training hyperparameters (small alpha, small lamda) and monitor cost.

## Next steps / TODO

- Add a short script interface under `scripts/` so notebooks can be run from the command line.
- Add tests for numeric gradient checks (finite differences) for the scratch implementations.
- Add a short CONTRIBUTING.md and small code-style checks.

## Notes

This repo is a learning exercise. Notebooks contain exploratory code and intermediate cells. If you want help debugging a specific notebook, open an issue here and include the notebook path and a short error trace.

---

If you want, I can (a) fix the logistic regression notebook's regularization/gradient code, (b) standardize the TensorFlow example in `NLP/nlp_tenserflow.ipynb`, or (c) add a small test harness and scripts to run specific notebooks non-interactively — tell me which and I'll proceed.
