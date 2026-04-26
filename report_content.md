# Statistical Analysis Report — Content for APA Template

---

## Title Page Fields

- **Title:** The Effect of Smoking Status on Medical Insurance Charges: A Statistical Analysis
- **Name:** Maurizio Pinto
- **Institution:** Woolf University
- **Course:** Data and Statistical Reasoning
- **Instructor:** [fill in from course]
- **Date:** [fill in submission date]

---

## Overview

This report presents a statistical analysis of 1,338 US medical insurance records to examine the factors that influence insurance costs. Using the Insurance dataset from Kaggle (Choi, 2018), I computed descriptive statistics, created visualizations, and performed a hypothesis test to determine whether smoking status has a statistically significant effect on insurance charges. The analysis finds that smokers incur substantially and significantly higher charges than non-smokers.

---

## Dataset Description

The dataset contains 1,338 records of individual insurance beneficiaries from the United States, with 7 columns: age (18–64 years), sex (male or female), bmi (body mass index, ranging from 15.96 to 53.13), children (number of dependents, 0–5), smoker (yes or no), region (northeast, northwest, southeast, southwest), and charges (annual medical insurance cost in USD, ranging from $1,122 to $63,770). The dataset has no missing values. The sample includes 676 males and 662 females, 274 smokers and 1,064 non-smokers, with a roughly balanced distribution across four US regions. The key variables examined in this analysis are charges as the primary outcome, smoker as the main grouping variable, and age and BMI as additional contextual factors (Choi, 2018).

---

## Methods

The analysis followed a structured approach, beginning with descriptive statistics to characterize the dataset. Summary statistics (mean, median, standard deviation, skewness) were computed for the numeric variables, and value counts were examined for categorical variables. These descriptive measures were chosen because they provide a complete picture of central tendency and spread, and the comparison of mean versus median helps identify skewness in the charges distribution. As Lusa et al. (2024) emphasize, thorough initial data analysis — including checking distributions and variable types — builds a solid foundation for any subsequent statistical testing.

Three visualizations were created to explore the data from different angles. Figure 1 uses kernel density estimation to compare the charges distribution between smokers and non-smokers, directly visualizing the group difference that the hypothesis test evaluates. Figure 2 uses box plots to examine whether BMI varies across regions, providing geographic context. Figure 3 uses a scatter plot to explore the relationship between age and charges, with smoking status as a color dimension, revealing potential interaction effects.

The hypothesis test chosen is Welch's independent samples t-test, which compares the mean charges of smokers and non-smokers. This test is appropriate because the outcome variable (charges) is continuous, the grouping variable (smoker) has two independent categories, and the test directly answers whether the observed difference in means is statistically significant. The standard Student's t-test assumes equal variances between groups, but Levene's test confirmed that the variances differ significantly between smokers (SD = $11,542) and non-smokers (SD = $5,994). Welch's t-test adjusts for this inequality by using separate variance estimates and modified degrees of freedom, making it the more appropriate choice (Ruxton, 2006). A significance level of α = 0.05 was used, and the test is two-tailed because no directional hypothesis was assumed in advance.

---

## Results

Descriptive statistics revealed that insurance charges are heavily right-skewed (skewness = 1.52), with a mean of $13,270 and a median of $9,382. This gap between mean and median indicates that a subset of policyholders incurs substantially higher costs, pulling the mean upward. Smokers (n = 274) had a mean charge of $32,050 (SD = $11,542), compared to $8,434 (SD = $5,994) for non-smokers (n = 1,064).

Figure 1 shows that the charges distribution for non-smokers peaks sharply below $10,000, while the smoker distribution is broader and shifted toward higher values, with a substantial portion exceeding $30,000. The two distributions have very little overlap, visually confirming a strong difference between the groups.

Figure 2 shows that BMI distributions are similar across the four US regions, with medians around 30. The southeast has slightly higher median BMI and more outliers, but the differences are modest.

Figure 3 reveals a positive relationship between age and charges for both groups. However, smokers consistently occupy a higher cost band at every age, and the gap between smokers and non-smokers appears to widen with increasing age.

The Welch's t-test produced a t-statistic of 32.75 and a p-value of 5.89 × 10⁻¹⁰³, which is far below the significance threshold of 0.05. The null hypothesis is rejected: there is a statistically significant difference in mean insurance charges between smokers and non-smokers.

---

## Interpretation for a Non-Technical Audience

In simple terms, this analysis asks: do smokers pay more for health insurance than non-smokers? The answer is clearly yes. On average, smokers in this dataset paid about $32,050 per year for medical insurance, while non-smokers paid about $8,434 — nearly four times less. The statistical test confirms that this difference is not due to random chance; the probability of seeing such a large gap by accident is effectively zero.

The data also shows that insurance costs tend to increase with age, which is expected, but smoking adds an extra cost premium on top of that age-related increase. This means that a 50-year-old smoker can expect to pay significantly more than a 50-year-old non-smoker, even though they are the same age.

The geographic analysis suggests that where someone lives does not strongly affect their insurance cost, at least in terms of BMI differences across regions. However, the dataset does not capture many other factors that could influence costs, such as pre-existing conditions, diet, or exercise habits.

---

## Limitations and Potential Bias

Several limitations should be acknowledged. First, this is an observational dataset, not a randomized experiment. While the analysis shows a strong association between smoking and higher charges, it cannot establish causation. Other factors correlated with smoking (such as overall health behavior, occupation, or socioeconomic status) may contribute to the observed cost difference.

Second, the dataset does not include potentially important variables such as pre-existing medical conditions, income, education level, or detailed health behaviors. These omitted variables could explain part of the variation in charges and introduce confounding bias.

Third, the smoker group (n = 274) is much smaller than the non-smoker group (n = 1,064), and the two groups have very different variance structures. While Welch's t-test accounts for unequal variances, the imbalance means that the non-smoker group dominates the overall descriptive statistics, potentially masking subgroup patterns.

Fourth, the dataset represents a single snapshot in time and does not track individuals longitudinally. As Lusa et al. (2024) note, cross-sectional analyses can miss temporal patterns and trends that would be visible in longitudinal data. Caution is warranted when generalizing these findings beyond this sample.

---

## References

Choi, M. (2018). Insurance dataset. Kaggle. https://www.kaggle.com/datasets/mirichoi0218/insurance

Lusa, L., Proust-Lima, C., Schmidt, C. O., Lee, K. J., le Cessie, S., Baillie, M., Lawrence, F., & Huebner, M. (2024). Initial data analysis for longitudinal studies to build a solid foundation for reproducible analysis. *PLOS ONE*, *19*(5), e0295726. https://doi.org/10.1371/journal.pone.0295726

Ruxton, G. D. (2006). The unequal variance t-test is an underused alternative to Student's t-test and the Mann-Whitney U test. *Behavioral Ecology*, *17*(4), 688–690. https://doi.org/10.1093/beheco/ark016
