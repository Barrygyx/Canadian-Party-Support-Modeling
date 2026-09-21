# Canadian Party Support Modeling

This project examines how age and province are associated with political party support in Canada using logistic regression and Census-based post-stratification.

The analysis combines individual-level responses from the 2021 Canadian Election Study with demographic population counts from the 2021 Canadian Census. Separate models are fitted for five political parties, and the predictions are then reweighted to better reflect the age and provincial composition of the Canadian population.

## Research Question

The project focuses on two main questions:

- How are age and province associated with support for different political parties?
- How do population-adjusted estimates differ from the raw survey results?

## Data

Two datasets are used:

- **Canadian Election Study (CES)** – individual survey responses including voting preference, age, and province
- **2021 Canadian Census** – population counts used for post-stratification

After cleaning and recoding, age was divided into 15 groups and province into 11 categories so that the survey and Census data could be aligned.

## Method

A separate logistic regression model was fitted for each of five political parties:

- Liberal
- Conservative
- NDP
- Bloc Québécois
- Green

Age group and province were used as predictors of party support.

The fitted probabilities were then adjusted using post-stratification. The population was divided into cells defined by combinations of age group and province, and model predictions were weighted using the corresponding Census population counts.

This allows the final estimates to reflect the demographic structure of the Canadian population rather than relying only on the composition of the survey sample.

## Results

The raw survey estimates and post-stratified estimates were:

| Party | Raw Survey | Post-Stratified |
| --- | ---: | ---: |
| Liberal | 27.1% | 27.0% |
| Conservative | 24.7% | 24.9% |
| NDP | 18.8% | 21.0% |
| Bloc Québécois | 9.0% | 6.9% |
| Green | 2.1% | 2.4% |

### Results Summary

Post-stratification changed the estimated support for each party by less than three percentage points, suggesting that the CES sample was already reasonably similar to the Census population in terms of the age and province variables used in the model.

The regression results also showed different age patterns across parties. The estimated age coefficients were positive for Liberal and Conservative support and negative for NDP and Green support.

Province had a particularly strong effect for Bloc Québécois support because its support was concentrated in Quebec. For most other parties, the provincial effects were less pronounced.

Overall, the post-stratification step mainly adjusted the magnitude of the estimates rather than substantially changing the patterns observed in the original survey data.

## Key Takeaways

This project demonstrates how survey data can be combined with population-level demographic information to produce more representative estimates.

It also provides practical experience with:

- Logistic regression for binary outcomes
- Survey data cleaning and recoding
- Census-based post-stratification
- Demographic weighting
- Comparing raw and population-adjusted estimates
