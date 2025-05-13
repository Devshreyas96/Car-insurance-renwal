# Predicting Insurance Renewals

This project implements a full analytical workflow to predict motor-insurance contract renewals and quantify customer sensitivity to pricing changes. It features a robust data-cleaning pipeline, exploratory analyses to pinpoint renewal drivers, and both logistic regression and price-elasticity models to generate actionable recommendations for optimizing pricing and retention strategies.

## Table of Contents
- [Features](#features)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Project Structure](#project-structure)
- [Usage](#usage)
- [Modeling Details](#modeling-details)
- [Results & Insights](#results--insights)
- [Contributing](#contributing)
- [License](#license)

## Features
- **Data Pipeline**: Automated ingestion, de-duplication, missing-value handling, outlier filtering, and factor encoding.
- **Exploratory Analysis**: Frequency distributions, correlation heatmaps, and distribution plots to uncover key patterns.
- **Logistic Regression**: Predicts individual renewal probabilities and evaluates performance via ROC/AUC.
- **Price Elasticity Modeling**: Measures how renewal likelihood changes with policy-price adjustments.
- **Actionable Insights**: Data-driven recommendations for pricing strategies to improve retention and profitability.

## Getting Started

### Prerequisites
- R (version ≥ 4.0)
- R packages: `dplyr`, `readxl`, `ggplot2`, `corrplot`, `pROC`, `broom`

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/predict-insurance-renewals.git
   cd predict-insurance-renewals
   ```
2. Install dependencies in R:
   ```r
   install.packages(c("dplyr", "readxl", "ggplot2", "corrplot", "pROC", "broom"))
   ```

## Project Structure
```
├── data/                   # Raw and processed data files
├── scripts/                # R scripts for each analysis stage
│   ├── 01_data_cleaning.R
│   ├── 02_exploratory_analysis.R
│   ├── 03_logistic_model.R
│   └── 04_price_elasticity.R
├── outputs/                # Figures and model outputs
└── README.md               # Project overview and instructions
```

## Usage
Run the scripts in sequence from an R console or RStudio:
```r
source("scripts/01_data_cleaning.R")
source("scripts/02_exploratory_analysis.R")
source("scripts/03_logistic_model.R")
source("scripts/04_price_elasticity.R")
```

## Modeling Details
- **Logistic Regression**: `glm(renewed ~ features, family = binomial)`
- **Elasticity Model**: `glm(renewed ~ price + pct_change_price, family = binomial)`

## Results & Insights
- Identified price, percent-change, age, and marital status as top renewal predictors.
- Quantified elasticity curves to inform discount thresholds and targeted retention campaigns.

## Contributing
Contributions are welcome! Please submit a pull request or open an issue to discuss improvements.

## License
This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
