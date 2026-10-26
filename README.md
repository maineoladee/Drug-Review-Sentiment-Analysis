# Drug Review Sentiment Analysis

**Natural Language Processing | Supervised Machine Learning | Deep Learning | Python**

An exploratory machine learning project investigating how written drug reviews can be classified by sentiment. The work compares conventional classification algorithms with neural network approaches and documents the steps from text preprocessing and feature preparation through training and model evaluation.

> **Project scope:** This is an academic/portfolio experiment, not a clinical decision-support tool. Sentiment in a public drug review does not establish a medicine's safety, effectiveness, or suitability for an individual.

## Project highlights

- Investigated drug-review text alongside contextual fields such as drug name, condition and rating.
- Explored and cleaned review data, including text processing and sentiment scoring using NLTK VADER.
- Compared classical supervised-learning methods and neural networks, including LSTM-based models.
- Evaluated models using classification metrics, training/validation accuracy and confusion matrices, with hyperparameter search and cross-validation in selected experiments.
- Documented the experiments in a Jupyter notebook and a separate written analysis report.

## Data

The notebook loads `drugsComTrain_raw.tsv` and `drugsComTest_raw.tsv`, with columns including `drugName`, `condition`, `review`, `rating`, `date`, and `usefulCount`. The notebook initially selects up to **10,000 rows from each file** for analysis. The source TSV files are **not included in this repository**.

To reproduce the exploration, obtain the original drug review dataset from a source that permits your use of it and place the files beside the notebook using the filenames above. Check the dataset's applicable licence and citation requirements before redistributing it.

## Approach

1. **Load and explore:** Inspect records, rating distributions, review content and potential data-quality issues.
2. **Prepare text:** Clean and transform free-text reviews, investigate lexical sentiment using VADER, and create model-ready features/sequences.
3. **Train baseline classifiers:** Explore Multinomial Naive Bayes, Linear Discriminant Analysis, Decision Trees/CART, bagging and Random Forest.
4. **Train neural models:** Experiment with an artificial neural network and LSTM architectures using TensorFlow/Keras.
5. **Evaluate:** Compare model results, inspect classification reports and confusion matrices, and consider generalisation rather than training accuracy alone.

The full workflow, including experiment-specific preprocessing choices, appears in [`Sentiment Analysis.ipynb`](Sentiment%20Analysis.ipynb).

## Results recorded in the notebook

The notebook includes the following **training** and **validation** accuracy summary. Values below are rounded from its saved comparison table; they are results of the recorded experiment, not independently rerun benchmarks.

| Model | Training accuracy | Validation accuracy |
|---|---:|---:|
| LSTM | 95.31% | 80.03% |
| Artificial Neural Network (ANN) | 99.98% | **81.38%** |
| Multinomial Naive Bayes | 79.52% | 77.44% |
| Linear Discriminant Analysis (LDA) | 84.56% | 78.95% |
| Decision Tree (CART) | 71.02% | 71.97% |
| Random Forest | 99.97% | 79.19% |

**Interpretation:** The ANN has the highest reported validation accuracy *in this comparison*, but its near-perfect training score alongside substantially lower validation performance suggests overfitting. Random Forest exhibits a similar train/validation gap. These scores should not be interpreted as externally validated clinical performance.

## Repository contents

```text
Drug-Review-Sentiment-Analysis/
├── README.md
├── Sentiment Analysis.ipynb
└── sentiment Analysis report.pdf
```

- **Notebook:** exploratory analysis, data preparation, model training and recorded outputs.
- **Report:** accompanying written analysis and discussion.

## Running the notebook

1. Clone the repository:

   ```bash
   git clone https://github.com/maineoladee/Drug-Review-Sentiment-Analysis.git
   cd Drug-Review-Sentiment-Analysis
   ```
2. Create and activate a Python virtual environment.
3. Install Jupyter and the packages used in the notebook, including NumPy, Pandas, Matplotlib, Seaborn, scikit-learn, NLTK, imbalanced-learn, Gensim, spaCy, WordCloud and TensorFlow/Keras.
4. Place the source TSV files in the working directory, retaining the expected filenames.
5. Start `jupyter notebook`, open `Sentiment Analysis.ipynb`, and run through the cells, reviewing compatibility issues before execution.

> **Reproducibility note:** The repository currently does not contain a pinned `requirements.txt` or the source dataset. Some imports use older library APIs, so execution may require a compatible Python environment or small updates. The notebook's saved outputs document the original experiments; this README does not claim that a clean end-to-end rerun has been verified.

## Limitations and potential improvements

- **Data splitting and leakage:** Revisit the notebook's handling of the original train/test files and ensure that final evaluation uses a genuinely untouched holdout set. Fit text transformations and any resampling only on training folds.
- **Model generalisation:** Consider stratified evaluation, class-level precision/recall/F1 and tests across drug categories, not accuracy alone.
- **Overfitting:** Investigate regularisation, early stopping and cross-validation for architectures with wide training/validation gaps.
- **Reproducibility:** Add pinned dependencies, fixed random seeds, a consistent data-loading path and a small automated evaluation script.
- **Interpretation:** Drug reviews are self-selected, may contain ambiguous language, and do not represent verified medical outcomes.

## Skills demonstrated

`Python` · `Pandas` · `NLP` · `Sentiment Analysis` · `scikit-learn` · `TensorFlow / Keras` · `LSTM` · `Model Evaluation` · `Hyperparameter Tuning` · `Exploratory Data Analysis`

---

**Author:** [maineoladee](https://github.com/maineoladee)  
**Purpose:** Applied ML/NLP portfolio and academic experimentation.
