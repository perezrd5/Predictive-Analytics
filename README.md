# Predictive Analytics

Coursework and applied modeling projects completed for **DDS-8555: Predictive Analytics**, part of the **Data Science Ph.D. program at National University**.

This repository is an evolving academic portfolio that documents the development of predictive-modeling skills through reproducible Python analyses. DDS-8555 is the fourth of 20 courses in the program and is being completed during the first year of study, well before the dissertation phase.

## Current focus

The repository currently emphasizes nonlinear regression and model evaluation. Its analyses compare linear and flexible functional forms, use cross-validation to estimate out-of-sample performance, examine model assumptions, and distinguish statistical significance from practical predictive value.

Current topics include:

- Exploratory data analysis and data-quality assessment
- Polynomial regression
- Cubic regression splines
- Multivariable additive models
- Ridge regularization
- Cross-validation and held-out validation
- Regression diagnostics and assumption checks
- Feature importance and partial-dependence analysis
- Kaggle submission development

## Projects

### Nonlinear modeling of automobile fuel economy

[`PerezDDDS8555-4-AppliedQuestion8.ipynb`](PerezDDDS8555-4-AppliedQuestion8.ipynb) addresses Applied Question 8 from Chapter 7 of *An Introduction to Statistical Learning with Applications in Python*.

Using the `Auto` dataset, the analysis:

- Investigates nonlinear relationships between vehicle characteristics and miles per gallon (`mpg`)
- Compares polynomial models of degrees 1–5 and cubic regression splines with 3–7 knots
- Uses shuffled 10-fold cross-validation for model selection
- Applies partial F-tests to assess departures from linearity
- Compares multivariable additive linear and spline models

The fitted relationships provide especially strong evidence of nonlinearity for horsepower, weight, and displacement. In the recorded notebook results, the additive spline model reduces cross-validated RMSE by approximately 13.5% relative to the additive linear model.

### Kaggle: Regression with an Abalone Dataset

[`PerezDDDS8555-4-Kaggle.ipynb`](PerezDDDS8555-4-Kaggle.ipynb) develops two nonlinear regression pipelines for the Kaggle [Regression with an Abalone Dataset](https://www.kaggle.com/competitions/playground-series-s4e4) competition.

The notebook:

- Audits and explores the competition data
- Predicts abalone ring counts using a log-transformed response
- Compares quadratic polynomial ridge regression with additive cubic regression splines
- Uses five-fold cross-validation and a separate validation set
- Evaluates RMSLE, RMSE, MAE, and R²
- Investigates functional form, heteroscedasticity, residual normality, independence, and multicollinearity
- Uses permutation importance and partial-dependence plots for interpretation
- Generates two Kaggle-ready submission files

The cubic regression spline model is selected by held-out RMSLE in the current notebook run. Kaggle submission evidence is included in [`kaggle_submission_evidence.png`](kaggle_submission_evidence.png).

## Repository structure

```text
Predictive-Analytics/
├── PerezDDDS8555-4-AppliedQuestion8.ipynb
├── PerezDDDS8555-4-Kaggle.ipynb
├── kaggle_submission_evidence.png
├── outputs/
│   ├── submission_polynomial.csv
│   └── submission_splines.csv
└── upload/
    ├── sample_submission.csv
    ├── test.csv
    └── train.csv
```

## Running the notebooks

### Prerequisites

- Python 3.10 or later
- JupyterLab, Jupyter Notebook, or another notebook-compatible environment

Install the principal dependencies with:

```bash
python -m pip install jupyter numpy pandas matplotlib seaborn scipy scikit-learn statsmodels ISLP
```

Then clone the repository and start JupyterLab:

```bash
git clone https://github.com/perezrd5/Predictive-Analytics.git
cd Predictive-Analytics
jupyter lab
```

Open a notebook and run its cells from top to bottom. Random seeds are fixed where applicable to improve reproducibility. The Abalone notebook expects the Kaggle CSV files in the repository root or in the included `upload/` directory.

## Tools and methods

The work currently uses Python, Jupyter, pandas, NumPy, Matplotlib, Seaborn, SciPy, scikit-learn, statsmodels, and the ISLP package.

## Academic context

These materials reflect coursework, experimentation, and learning in progress. Interpretations may be refined as the course advances and additional projects are added. Results are presented for educational purposes and should not be treated as causal conclusions or production-ready predictions without further validation.

If you are completing similar coursework, use this repository as a reference for concepts and reproducible practices—not as a substitute for producing and explaining your own work.

## Author

**Doug Perez**  
Ph.D. Student, Data Science  
National University
